# WICWIU

(**WICWIU** 설명)

## Usage

- `command...` - 설명

- `command2...` - 설명2

---

!!! warning "Accessibility – not all color combinations work well"

    With __2__ (color schemes) __x 21__ (primary colors) __x 17__ (accent color)
    = __714__ combinations, it's impossible to ensure that all configurations
    provide a good user experience (e.g. _yellow on light background_). Make
    sure that the color combination of your choosing provides enough contrast
    and tweak CSS variables where necessary.

## Project layout

    makefile      # makefile
    src/
        example.cpp   # 설명
        example2.cpp  # 설명2

## 문서 

**WICWIU** 프로젝트에 참여하기 위해서 이해해야 하는 필요충분문서들 ㅎㅎ

```python
def sete():
    i = 0
    str = "string"
    pass
```

```python
import itertools
import numpy as np
from config import *
from time import time


def full(num, count):
    return [num] * count


def zeros(count):
    return full(0, count)


def ones(count):
    return full(1, count)


def minus(count):
    return full(-1, count)


class Pattern:
    @classmethod
    def divisions(cls, num, space=float('inf'), lim=float('inf'), depth=0, fill_space=False):
        for main_chunk in range(min(num, lim), 0, -1):
            rest_chunk = num - main_chunk
            if rest_chunk == 0:
                if fill_space and depth == 0:
                    yield [main_chunk] + zeros(space - 1)
                else:
                    yield [main_chunk]
                continue
            if depth + 2 > space:
                continue
            rchunk_divisions = cls.divisions(
                rest_chunk, space, lim=main_chunk, depth=depth+1)
            for rest_chunk_division in rchunk_divisions:
                if fill_space and depth == 0:
                    yield [main_chunk, *rest_chunk_division] + zeros(space - (1 + len(rest_chunk_division)))
                else:
                    yield [main_chunk, *rest_chunk_division]

    @classmethod
    def permutations_without_duplication(cls, iterable, l=0, r=None):
        r = len(iterable)-1 if r is None else r
        black_list = []
        for i in range(l, r+1):
            if (iterable[l] == iterable[i] and l != i) or\
               (iterable[i] in black_list):
                continue
            black_list.append(iterable[i])
            iterable[l], iterable[i] = iterable[i], iterable[l]
            if l+1 == r:
                yield tuple(iterable)
            else:
                for case in cls.permutations_without_duplication(iterable, l+1, r):
                    yield case
            iterable[l], iterable[i] = iterable[i], iterable[l]  # backtrack

    @classmethod
    def white_cell_patterns(cls, space, num):
        for v in cls.divisions(num, space, fill_space=True):
            for pattern in cls.permutations_without_duplication(v):
                yield pattern

    @classmethod
    def patterns_from_map(cls, arg):
        # arg[0] -> 'row' or 'col'
        # arg[1] -> index
        # arg[2] -> keys
        # arg[3] -> length
        start_time = time()
        result = cls.patterns(arg[2], arg[3])
        if sum(arg[2]) != 0:
            timedata = (time()-start_time, sum(arg[2]), len(arg[2]), len(arg[2])/sum(arg[2]))
        else:
            timedata = (time()-start_time, sum(arg[2]), len(arg[2]), 0)
        return arg[0], arg[1], result, timedata

    @classmethod
    def patterns(cls, key, length):
        S = len(key)    # number of keys
        B = sum(key)    # number of black cells
        W = length - B  # number of white cells
        VARIABLE_FACTOR = W - (S - 1)

        if not VARIABLE_FACTOR:
            pattern = []
            for i, black_cell in enumerate(key):
                pattern += ones(black_cell)
                if i != S - 1:
                    pattern.append(-1)
            return np.array([pattern], dtype=DTYPE)

        white_cell_patterns = cls.white_cell_patterns(S + 1, VARIABLE_FACTOR)
        pattern_set = None
        for white_cell_pattern in white_cell_patterns:
            pattern = []
            for i, white_cell in enumerate(white_cell_pattern):
                pattern += minus(white_cell)
                if i < S:
                    pattern += ones(key[i])
                    if i != S - 1:
                        pattern.append(-1)
            if pattern_set is None:
                pattern_set = np.array([pattern], dtype=DTYPE)
            else:
                pattern_set = np.append(pattern_set, np.array(
                    [pattern], dtype=DTYPE), axis=0)

        return pattern_set
```

```c
/*
	Copyright 2014-2020 Igor van den Hoven

	                    ivdhoven@gmail.com
*/

/*
	This program is free software: you can redistribute it and/or modify
	it under the terms of the GNU General Public License as published by
	the Free Software Foundation, either version 3 of the License, or
	(at your option) any later version.

	This program is distributed in the hope that it will be useful,
	but WITHOUT ANY WARRANTY; without even the implied warranty of
	MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
	GNU General Public License for more details.

	You should have received a copy of the GNU General Public License
	along with this program.  If not, see <http://www.gnu.org/licenses/>.
*/

/*
	Binary Search v1.4

	Compile using: gcc -O3 binary-search.c
*/

#include <stdlib.h>
#include <stdio.h>
#include <string.h>
#include <sys/time.h>
#include <time.h>
#include <math.h>
#include <stdbool.h>

int checks;


// This is the standard binary search from text books

int standard_binary_search(int *array, int array_size, int key)
{
	register int bot, mid, i;

	bot = 0;
	i = array_size - 1;

	while (bot < i)
	{
		mid = i - (i - bot) / 2;

		++checks;

		if (key < array[mid])
		{
			i = mid - 1;
		}
		else
		{
			bot = mid;
		}
	}

	++checks;

	if (key == array[i])
	{
		return i;
	}
	return -1;
}

// slightly faster than the standard binary search

int tailed_binary_search(int *array, int array_size, int key)
{
	register int i, mid, bot;

	bot = 0;
	i = array_size -1;
	mid = i / 2;

	while (mid)
	{
		++checks;

		if (key < array[i - mid])
		{
			i -= mid + 1;
		}
		else
		{
			bot = i - mid;
		}
		mid = (i - bot) / 2;
	}

	if (bot < i && ++checks && key < array[i])
	{
		--i;
	}

	++checks;

	if (key == array[i])
	{
		return i;
	}
	return -1;
}


// more key checks but simpler calculations

int boundless_binary_search(int *array, int array_size, int key)
{
	register int mid, i;

	++checks;

	if (key < array[0])
	{
		return -1;
	}

	mid = i = array_size - 1;

	while (mid > 3)
	{
		mid /= 2;

		++checks;

		if (key < array[i - mid])
		{
			i -= mid;
		}
	}

	while (++checks && key < array[i])
	{
		--i;
	}

	++checks;

	if (key == array[i])
	{
		return i;
	}
	return -1;
}

// slightly more key checks with simpler calculations

int inbound_binary_search(int *array, int array_size, int key)
{
	register int mid, i;

	mid = array_size / 2;

	++checks;

	if (key < array[mid])
	{
		i = 0;

		while (mid > 1)
		{
			mid /= 2;

			++checks;

			if (key > array[i + mid])
			{
				i += mid + 1;
			}
		}

		if (++checks && key > array[i])
		{
			++i;
		}
	}
	else
	{
		i = array_size - 1;

		while (mid > 1)
		{
			mid /= 2;

			++checks;

			if (key < array[i - mid])
			{
				i -= mid + 1;
			}
		}

		if (++checks && key < array[i])
		{
			--i;
		}
	}

	++checks;

	if (key == array[i])
	{
		return i;
	}
	return -1;
}

// more key checks but better performance on large arrays

int boundless_quaternary_search(int *array, int array_size, int key)
{
	register int mid, i;

	++checks;

	if (key < array[0])
	{
		return -1;
	}

	mid = i = array_size - 1;

	while (mid > 7)
	{
		mid /= 4;

		++checks;

		if (key < array[i - mid])
		{
			if (key < array[i - mid * 2])
			{
				if (key < array[i - mid * 3])
				{
					++checks;
					++checks;
					i -= mid * 3;
				}
				else
				{
					++checks;
					++checks;
					i -= mid * 2;
				}
			}
			else
			{
				++checks;
				i -= mid;
			}
		}
	}

	while (++checks && key < array[i])
	{
		--i;
	}

	++checks;

	if (key == array[i])
	{
		return i;
	}
	return -1;
}

// slightly more key checks and better performance on large arrays

int inbound_quaternary_search(int *array, int array_size, int key)
{
	register int mid, i;

	mid = array_size / 2;

	++checks;

	if (key < array[mid])
	{
		i = 0;

		while (mid > 7)
		{
			mid /= 4;

			++checks;

			if (key >= array[i + mid])
			{
				if (key >= array[i + mid * 2])
				{
					if (key >= array[i + mid * 3])
					{
						++checks;
						++checks;
						i += mid * 3;
					}
					else
					{
						++checks;
						++checks;
						i += mid * 2;
					}
				}
				else
				{
					++checks;
					i += mid;
				}
			}
		}
		while (++checks && key > array[i])
		{
			++i;
		}
	}
	else
	{
		i = array_size - 1;

		while (mid > 7)
		{
			mid /= 4;

			++checks;

			if (key < array[i - mid])
			{
				if (key < array[i - mid * 2])
				{
					if (key < array[i - mid * 3])
					{
						++checks; ++checks;
						i -= mid * 3;
					}
					else
					{
						++checks; ++checks;
						i -= mid * 2;
					}
				}
				else
				{
					++checks;
					i -= mid;
				}
			}
		}
		while (++checks && key < array[i])
		{
			--i;
		}
	}

	++checks;

	if (key == array[i])
	{
		return i;
	}
	return -1;
}



// requires an even distribution

int boundless_interpolated_search(int *array, int array_size, int key)
{
	register int mid, i, min, max;

	++checks;

	if (key < array[0])
	{
		return -1;
	}
	min = array[0];

	i = array_size - 1;

	++checks;

	if (key >= (max = array[i]))
	{
		return ++checks && key == max ? i : -1;
	}

	i *= (float) (key - min) / (max - min);

	if (++checks && key >= array[i])
	{
		max = array_size - 1;

		mid = 4;

		while (1)
		{
			if (i + mid > max)
			{
				mid = max - i;
				break;
			}

			++checks;

			if (key > array[i + mid])
			{
				i += mid;
			}
			else
			{
				break;
			}
			mid *= 2;
		}

		while (mid > 3)
		{
			mid /= 2;

			++checks;

			if (key > array[i + mid])
			{
				i += mid;
			}
		}
		while (++checks && key > array[i])
		{
			++i;
		}
	}
	else
	{
		mid = 4;

		while (1)
		{
			if (i - mid < 0)
			{
				mid = i;
				break;
			}

			++checks;

			if (key < array[i - mid])
			{
				i -= mid;
			}
			else
			{
				break;
			}
			mid *= 2;
		}

		while (mid > 3)
		{
			mid /= 2;

			if (++checks && key < array[i - mid])
			{
				i -= mid;
			}
		}
		while (++checks && key < array[i])
		{
			--i;
		}
	}

	if (++checks && key == array[i])
	{
		return i;
	}
	return -1;
}

long long utime()
{
	struct timeval now_time;

	gettimeofday(&now_time, NULL);

	return now_time.tv_sec * 1000000LL + now_time.tv_usec;
}

int *array;
int density, max, loop, top, rnd, runs;
long long start, end, best;
int *array;

void execute(int (*algo_func)(int *, int, int), const char * algo_name)
{
	int hit = 0, miss = 0;

	srand(rnd);

	checks = 0;
	best = 0;

	for (int run = runs ; run ; --run)
	{
		start = utime();

		for (int cnt = loop ; cnt ; --cnt)
		{
			if (algo_func(array, max, rand() % top) >= 0)
			{
				hit++;
			}	
			else
			{
				miss++;
			}
		}

		end = utime();

		if (best == 0 || end - start < best)
		{
			best = end - start;
		}
	}
	printf("| %30s | %10d | %10d | %10d | %10d | %10f |\n", algo_name, max, hit, miss, checks, best / 1000000.0);

}

#define run(algo) execute(&algo, #algo)

int main(int argc, char **argv)
{
	int cnt, val;

	max = 100000;
	loop = 10000;
	density = 100; // max * density should stay under 2 billion
	runs = 1000;

	if (argc > 1)
		max = atoi(argv[1]);

	if (argc > 2)
		loop = atoi(argv[2]);

	if (argc > 3)
		runs = atoi(argv[3]);

	if (argc > 4)
		density = atoi(argv[3]);

	array = malloc(max * sizeof(int));

	if ((long long) max * (long long) density > 2000000000)
	{
		density = 2;
	}

//	srand(time(NULL));
	srand(1);

	rnd = rand();

	for (cnt = 0, val = 0 ; cnt < max ; cnt++)
	{
		array[cnt] = (val += rand() % density + 1);
	}

	top = array[max - 1] + 2;

	printf("\n\nEven distribution with %d 32 bit integers\n\n", max);

	printf("| %30s | %10s | %10s | %10s | %10s | %10s |\n", "Name", "Items", "Hits", "Misses", "Checks", "Time");
	printf("| %30s | %10s | %10s | %10s | %10s | %10s |\n", "----------", "----------", "----------", "----------", "----------", "----------");

	// Trial run

	run(standard_binary_search);

	// Begin

	run(standard_binary_search);
	run(tailed_binary_search);
	run(boundless_binary_search);
	run(inbound_binary_search);
	run(boundless_quaternary_search);
	run(inbound_quaternary_search);
	run(boundless_interpolated_search);

	for (cnt = 0, val = 0 ; cnt < max / 8 ; cnt++)
	{
		array[cnt] = val++;
	}

	for ( ; cnt < max ; cnt++)
	{
		array[cnt] = (val += rand() % density + 1);
	}

	top = array[max - 1] + 2;

	printf("\n\nUneven distribution with %d 32 bit integers\n\n", max);
	printf("| %30s | %10s | %10s | %10s | %10s | %10s |\n", "Name", "Items", "Hits", "Misses", "Checks", "Time");
	printf("| %30s | %10s | %10s | %10s | %10s | %10s |\n", "----------", "----------", "----------", "----------", "----------", "----------");
	// Trial run

	run(standard_binary_search);

	// Begin
	run(boundless_interpolated_search);

	return 0;
}
```