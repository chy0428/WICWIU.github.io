우리는 분석을 통하여 데이터셋을 `Tensor`로 변환하는 방법을 이해했다.

**데이터셋을 `Tensor` 로 변환하는 방법이란 (1) 데이터셋을 적절한 방식으로 읽고 (2) 메모리에 저장한 다음 (3) `Tensor` 객체를 데이터셋 형상에 맞춰서 적절히 만들고 (4) 그냥 `Tensor[Index5D(i1, i2, i3, i4, i5)]` 라는 식으로 복사하면 끝이다.**

그러므로 **CasiaWebFace** 의 `.png` 데이터셋을 `Tensor` 로 변환하는 본격적인 코딩을 시작할 수 있다. 하지만 그에 앞서 `.png` 파일 포맷에 대한 가벼운 이해라도 필요하다.

# PNG file format

`.png` 파일의 포맷에 대한 정보는 [이곳](https://github.com/corkami/formats/blob/master/image/png.md)을 통하여 얻을 수 있었다.

## Structure

![](https://raw.githubusercontent.com/corkami/formats/master/image/PNGBasicStruct.svg)
<figcaption><i>PNG file Structure (https://github.com/corkami/formats/blob/master/image/png.md)</i></figcaption>

**PNG** 파일은 위와 같이 **Signature** 와 여러개의 **chunk** 들로 구성된다.

1. **Signature**: **PNG** 파일임을 구별할 수 있게 해주는 매직넘버로써 다음과 같은 `8` 바이트 데이터로 구성된다.

    `\x89PNG\x0d\x0a\x1a\x0a` 

2. **chunk**: [**length-type-data-checksum**] 와 같이 `4` 가지 데이터로 구성되는 데이터구조이다. 

    1. `length`: `>4u` 

        `4` 바이트 빅엔디안 `unsigned` 로 이루어진 데이터 길이 지정자이다. 이 길이는 `type-data-checksum` 의 길이가 아니라 오직 `data` 의 길이를 뜻한다. 

    2. `type`: `4c` 
    
        `4` 바이트 `char` 로 이루어진 타입 지정자이다. 타입은 `IHDR`, `IDAT`, `IEND` 등이 있다. `IHDR` 은 헤더 데이터를 뜻하고, `IDAT` 은 실제 이미지 데이터를 뜻하고, `IEND` 는 파일의 끝을 나타내는 데이터를 뜻한다.

    3. `data`: `[length]b`

        `length` 바이트만큼의 실제 이미지 데이터이다.

    4. `checksum(type+data)`: `4u`

        `4` 바이트 `unsigned` 로 이루어진 체크섬이다. 데이터가 훼손되지 않았는지 검증할 수 있게 해준다.

3. **Terminator**: 마지막으로 **PNG** 파일은 파일의 끝을 알리는 다음의 바이트 배열을 갖는다. 

    `00 00 00 00 .I .E .N .D AE 42 60 82`

## Example

![](https://raw.githubusercontent.com/corkami/formats/master/image/PNGRGB_dissected.png)
<figcaption><i>a dissected RGN png (https://github.com/corkami/formats/blob/master/image/png.md)</i></figcaption>

**PNG** 파일은 위와 같이 Signature 로 시작하여 Header, Data, Terminator 로 구성된다. 이것은 빨강, 초록, 파랑 픽셀만을 갖는 단순힌 **PNG** 파일을 분석한 것이다.

*참고 및 출처*: 

:   https://github.com/corkami/formats/blob/master/image/png.md

---

# CImg

이제 실제로 **PNG** 파일을 읽어서 메모리에 저장한 후 `Tensor` 로 변환해볼텐데 바이너리 파일을 읽고 저장하는 코드를 짜려면 [**PNG** 파일의 전체 스펙을 기술한 표준](http://www.libpng.org/pub/png/spec/1.2/png-1.2-pdg.html) 모두 이해한 다음 바이너리 레벨의 처리를 해주어야 하므로 상당히 시간 소모가 많이 된다. 심지어 바이너리 레벨의 처리는 취약점이 발생하기 매우 쉬워서 [**WICWIU**](https://github.com/WICWIU/WICWIU) 에 취약점이 생길 수도 있다. 

그러므로 **PNG** 파일을 읽을 수 있도록 이미 제작된 라이브러리를 사용하는 것이 낫다. `C++` 에서 **PNG** 파일을 읽을 수 있는 라이브러리는 많이 있지만 그 중에서 [`CImg`](http://cimg.eu) 를 사용하기로 했다. 그 이유는 다음과 같다.

1. `CImg` 는 `C++` 에서 **PNG** 이미지를 처리할 수 있도록 최적화된 라이브러리이다.

2. `CImg` 는 이미지를 처리할 수 있는 클래스 템플릿을 제공하여 다양한 픽셀 타입(`bool`, `char`, `int`, `float` 등)으로 이미지를 저장할 수 있다.

3. `CImg` 는 여러 이미지를 손쉽게 다룰 수 있는 기능을 제공한다.

4. `CImg` 는 **thread-safe** 하다.

5. `CImg` 는 가볍다. `CImg` 는 단지 하나의 헤더파일 `CImg.h` 로 구성된 라이브러리이다. `CImg` 에는 오직 `4` 가지 클래스만 정의되어 있다. `CImg` 는 다른 의존성 없이 순전히 **STL** 과 시스템 라이브러리만을 사용한다.

6. `CImg` 는 무료이고 오픈소스이다.

*참고 및 출처*: 

:   http://cimg.eu

## Installation

## Getting Started

## Loop

픽셀 버퍼 루프, 차원 루프 매크로를 제공한다.

*참고 및 출처*: 

:   http://cimg.eu/reference/group__cimg__loops.html

## 픽셀 저장 방식

`CImg` 는 생성될 때 이미지의 모든 픽셀값을 메모리에 한번에 저장한다. `CImg` 는 기본적으로 `4` 차원(`width`, `height`, `depth`, `dim`) 배열이다. 그리고 이 픽셀값들이 메모리에 `width * height * depth * dim` 의 크기의 선형 배열(`1` 차원 배열)로 저장된다.

그러니까 `CImg` 로 이미지 객체가 생성되면 `width * height * depth * dim * sizeof(T)` 바이트가 할당된다.

이렇게 픽셀들이 저장된 메모리의 주소값은 `CImg<T>::data()` 메소드가 반환한다. 이것을 `T*` 에 저장하면 된다. 

Now, the ordering of the pixel values in this buffer follows these rules : The values are not interleaved, and are ordered first along the X,Y,Z and V axis respectively (corresponding to the width,height,depth,dim dimensions), starting from the upper-left pixel to the bottom-right pixel of the instane image, with a classical scanline run.

So, a color image with dim=3 and depth=1, will be stored in memory as :R1R2R3R4R5R6......G1G2G3G4G5G6.......B1B2B3B4B5B6.... (i.e following a 'planar' structure)and not as R1G1B1R2G2B2R3G3B3... (interleaved channels), where R1 = img(0,0,0,0) is the first upper-left pixel of the red component of the image, R2 is img(1,0,0,0), G1 = img(0,0,0,1), G2 = img(1,0,0,1), B1 = img(0,0,0,2), and so on...Another example, a (1x5x1x1) CImg<T> (column vector A) will be stored as : A1A2A3A4A5 where A1 = img(0,0), A2 = img(0,1), ... , A5 = img(0,4).

As you see, it is very simple and intuitive : no interleaving, no padding, just simple. This is cool not only because it is simple, but this has in fact a number of interesting properties. For instance, a 2D color image is stored in memory exactly as a 3D scalar image having a depth=3, meaning that when you are dealing with 2D color images, you can write 'img(x,y,k)' instead of 'img(x,y,0,k)' to access the kth channel of the (x,y) pixel. More generally, if you have one dimension that is 1 in your image, you can just skip it in the call to the operator(). Similarly, values of a column vector stored as an image with width=depth=spectrum=1 can be accessed by 'img(y)' instead of 'img(0,y)'. This is very convenient.Another cool thing is that it allows you to work easily with 'shared' images. A shared image is a CImg<T> instance that shares its memory with another one (the 'base' image). Destroying a shared image does nothing in fact. Shared images is a convenient way of modifying only portions (consecutive in memory) of an image. For instance, if 'img' is a 2D color image, you can write :img.get_shared_channel(0).blur(2); img.get_shared_channels(1,2).mirror('x');which just blur the red channel of the image, and mirror the two others along the X-axis. This is possible since channels of an image are not interleaved but are stored as different consecutive planes in memory, so you see that constructing a shared image is possible (and trivial). 


*참고 및 출처*: 

:   http://cimg.eu/reference/group__cimg__storage.html