# Summary

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`namespace `[`cimg_library_suffixed`](#namespacecimg__library__suffixed) | Contains *all classes and functions* of the \CImg library.
`namespace `[`cimg_library_suffixed::cimg`](#namespacecimg__library__suffixed_1_1cimg) | Contains *low-level* functions and variables of the \CImg Library.
`struct `[`cimg_library_suffixed::CImg::_cimg_math_parser`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser) | 
`struct `[`cimg_library_suffixed::CImg::_functor2d_expr`](#structcimg__library__suffixed_1_1CImg_1_1__functor2d__expr) | 
`struct `[`cimg_library_suffixed::CImg::_functor2d_float`](#structcimg__library__suffixed_1_1CImg_1_1__functor2d__float) | 
`struct `[`cimg_library_suffixed::CImg::_functor2d_int`](#structcimg__library__suffixed_1_1CImg_1_1__functor2d__int) | 
`struct `[`cimg_library_suffixed::CImg::_functor3d_expr`](#structcimg__library__suffixed_1_1CImg_1_1__functor3d__expr) | 
`struct `[`cimg_library_suffixed::CImg::_functor3d_float`](#structcimg__library__suffixed_1_1CImg_1_1__functor3d__float) | 
`struct `[`cimg_library_suffixed::CImg::_functor3d_int`](#structcimg__library__suffixed_1_1CImg_1_1__functor3d__int) | 
`struct `[`cimg_library_suffixed::CImg::_functor4d_int`](#structcimg__library__suffixed_1_1CImg_1_1__functor4d__int) | 
`struct `[`cimg_library_suffixed::CImg::_functor4d_streamline2d_directed`](#structcimg__library__suffixed_1_1CImg_1_1__functor4d__streamline2d__directed) | 
`struct `[`cimg_library_suffixed::CImg::_functor4d_streamline2d_oriented`](#structcimg__library__suffixed_1_1CImg_1_1__functor4d__streamline2d__oriented) | 
`struct `[`cimg_library_suffixed::CImg::_functor4d_streamline3d_directed`](#structcimg__library__suffixed_1_1CImg_1_1__functor4d__streamline3d__directed) | 
`struct `[`cimg_library_suffixed::CImg::_functor4d_streamline3d_oriented`](#structcimg__library__suffixed_1_1CImg_1_1__functor4d__streamline3d__oriented) | 
`struct `[`cimg_library_suffixed::CImg::_functor4d_streamline_expr`](#structcimg__library__suffixed_1_1CImg_1_1__functor4d__streamline__expr) | 
`struct `[`cimg_library_suffixed::CImg::_functor_isoline3d`](#structcimg__library__suffixed_1_1CImg_1_1__functor__isoline3d) | 
`struct `[`cimg_library_suffixed::CImg::_functor_isosurface3d`](#structcimg__library__suffixed_1_1CImg_1_1__functor__isosurface3d) | 

# namespace `cimg_library_suffixed` {#namespacecimg__library__suffixed}

Contains *all classes and functions* of the \CImg library.

This namespace is defined to avoid functions and class names collisions that could happen with the inclusion of other C++ header files. Anyway, it should not happen often and you should reasonably start most of your \CImg-based programs with 
```cpp
#include "CImg.h"
using namespace cimg_library;
```
 to simplify the declaration of \CImg Library objects afterwards.

<h2> Summary </h2>

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`public  `[`_cimg_create_operator`](#namespacecimg__library__suffixed_1a6ed39c1394e29af517aedbf68ec05fd6)`(bool) const`            | 
`public template<>`  <br/>`inline `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< _cimg_Tfloat > `[`operator-`](#namespacecimg__library__suffixed_1afa92bc3a6441c4003ad7c058e3c75f1b)`(const char *const expression,const `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< T > & img)`            | 
`public template<>`  <br/>`inline `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< _cimg_Tfloat > `[`operator*`](#namespacecimg__library__suffixed_1a521900f5178315a7c1b186a83667306d)`(const char *const expression,const `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< T > & img)`            | 
`public template<>`  <br/>`inline `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< _cimg_Tfloat > `[`operator/`](#namespacecimg__library__suffixed_1af2bdc1f26a64adc01b8d8c61df639568)`(const char *const expression,const `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< T > & img)`            | 
`public template<>`  <br/>`inline `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< T > `[`operator&`](#namespacecimg__library__suffixed_1a67e038c792e6e3dac5da99a3335b54c3)`(const char *const expression,const `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< T > & img)`            | 
`public template<>`  <br/>`inline `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< T > `[`operator\|`](#namespacecimg__library__suffixed_1ae21cfd5e27421ddba3574b10ef087b19)`(const char *const expression,const `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< T > & img)`            | 
`public template<>`  <br/>`inline `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< T > `[`operator^`](#namespacecimg__library__suffixed_1aee149205a6148f93291406eb301e4710)`(const char *const expression,const `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< T > & img)`            | 
`public template<>`  <br/>`inline bool `[`operator==`](#namespacecimg__library__suffixed_1aab2a4105be9672849d2255c8732eadc6)`(const char *const expression,const `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< T > & img)`            | 
`public template<>`  <br/>`inline bool `[`operator!=`](#namespacecimg__library__suffixed_1a5ded9f4e593e6dd9f597b6fef66b8133)`(const char *const expression,const `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< T > & img)`            | 
`public template<>`  <br/>`inline `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< T > `[`transpose`](#namespacecimg__library__suffixed_1a48465f36a81f510ce3368f0e0200532e)`(const `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< T > & instance)`            | 
`public template<>`  <br/>`inline `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< _cimg_Tfloat > `[`invert`](#namespacecimg__library__suffixed_1a78492a52daecbec968b15f3c02f3fdde)`(const `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< T > & instance)`            | 
`public template<>`  <br/>`inline `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< _cimg_Tfloat > `[`pseudoinvert`](#namespacecimg__library__suffixed_1aa2cd51ec8b416d2ca4299253e618d343)`(const `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< T > & instance)`            | 
`struct `[`cimg_library_suffixed::CImg`](#structcimg__library__suffixed_1_1CImg) | Class representing an image (up to 4 dimensions wide), each pixel being of type `T`.
`struct `[`cimg_library_suffixed::CImgAbortException`](#structcimg__library__suffixed_1_1CImgAbortException) | 
`struct `[`cimg_library_suffixed::CImgArgumentException`](#structcimg__library__suffixed_1_1CImgArgumentException) | 
`struct `[`cimg_library_suffixed::CImgDisplayException`](#structcimg__library__suffixed_1_1CImgDisplayException) | 
`struct `[`cimg_library_suffixed::CImgException`](#structcimg__library__suffixed_1_1CImgException) | Instances of `[CImgException](#structcimg__library__suffixed_1_1CImgException)` are thrown when errors are encountered in a \CImg function call.
`struct `[`cimg_library_suffixed::CImgInstanceException`](#structcimg__library__suffixed_1_1CImgInstanceException) | 
`struct `[`cimg_library_suffixed::CImgIOException`](#structcimg__library__suffixed_1_1CImgIOException) | 
`struct `[`cimg_library_suffixed::CImgList`](#structcimg__library__suffixed_1_1CImgList) | Represent a list of images CImg<T>.
`struct `[`cimg_library_suffixed::CImgWarningException`](#structcimg__library__suffixed_1_1CImgWarningException) | 

<h2> Members </h2>

#### `public  `[`_cimg_create_operator`](#namespacecimg__library__suffixed_1a6ed39c1394e29af517aedbf68ec05fd6)`(bool) const` {#namespacecimg__library__suffixed_1a6ed39c1394e29af517aedbf68ec05fd6}

#### `public template<>`  <br/>`inline `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< _cimg_Tfloat > `[`operator-`](#namespacecimg__library__suffixed_1afa92bc3a6441c4003ad7c058e3c75f1b)`(const char *const expression,const `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< T > & img)` {#namespacecimg__library__suffixed_1afa92bc3a6441c4003ad7c058e3c75f1b}

#### `public template<>`  <br/>`inline `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< _cimg_Tfloat > `[`operator*`](#namespacecimg__library__suffixed_1a521900f5178315a7c1b186a83667306d)`(const char *const expression,const `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< T > & img)` {#namespacecimg__library__suffixed_1a521900f5178315a7c1b186a83667306d}

#### `public template<>`  <br/>`inline `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< _cimg_Tfloat > `[`operator/`](#namespacecimg__library__suffixed_1af2bdc1f26a64adc01b8d8c61df639568)`(const char *const expression,const `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< T > & img)` {#namespacecimg__library__suffixed_1af2bdc1f26a64adc01b8d8c61df639568}

#### `public template<>`  <br/>`inline `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< T > `[`operator&`](#namespacecimg__library__suffixed_1a67e038c792e6e3dac5da99a3335b54c3)`(const char *const expression,const `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< T > & img)` {#namespacecimg__library__suffixed_1a67e038c792e6e3dac5da99a3335b54c3}

#### `public template<>`  <br/>`inline `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< T > `[`operator|`](#namespacecimg__library__suffixed_1ae21cfd5e27421ddba3574b10ef087b19)`(const char *const expression,const `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< T > & img)` {#namespacecimg__library__suffixed_1ae21cfd5e27421ddba3574b10ef087b19}

#### `public template<>`  <br/>`inline `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< T > `[`operator^`](#namespacecimg__library__suffixed_1aee149205a6148f93291406eb301e4710)`(const char *const expression,const `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< T > & img)` {#namespacecimg__library__suffixed_1aee149205a6148f93291406eb301e4710}

#### `public template<>`  <br/>`inline bool `[`operator==`](#namespacecimg__library__suffixed_1aab2a4105be9672849d2255c8732eadc6)`(const char *const expression,const `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< T > & img)` {#namespacecimg__library__suffixed_1aab2a4105be9672849d2255c8732eadc6}

#### `public template<>`  <br/>`inline bool `[`operator!=`](#namespacecimg__library__suffixed_1a5ded9f4e593e6dd9f597b6fef66b8133)`(const char *const expression,const `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< T > & img)` {#namespacecimg__library__suffixed_1a5ded9f4e593e6dd9f597b6fef66b8133}

#### `public template<>`  <br/>`inline `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< T > `[`transpose`](#namespacecimg__library__suffixed_1a48465f36a81f510ce3368f0e0200532e)`(const `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< T > & instance)` {#namespacecimg__library__suffixed_1a48465f36a81f510ce3368f0e0200532e}

#### `public template<>`  <br/>`inline `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< _cimg_Tfloat > `[`invert`](#namespacecimg__library__suffixed_1a78492a52daecbec968b15f3c02f3fdde)`(const `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< T > & instance)` {#namespacecimg__library__suffixed_1a78492a52daecbec968b15f3c02f3fdde}

#### `public template<>`  <br/>`inline `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< _cimg_Tfloat > `[`pseudoinvert`](#namespacecimg__library__suffixed_1aa2cd51ec8b416d2ca4299253e618d343)`(const `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< T > & instance)` {#namespacecimg__library__suffixed_1aa2cd51ec8b416d2ca4299253e618d343}

# struct `cimg_library_suffixed::CImg` {#structcimg__library__suffixed_1_1CImg}

Class representing an image (up to 4 dimensions wide), each pixel being of type `T`.

This is the main class of the CImg Library. It declares and constructs an image, allows access to its pixel values, and is able to perform various image operations.

Image representation

A CImg image is defined as an instance of the container `CImg<T>`, which contains a regular grid of pixels, each pixel value being of type `T`. The image grid can have up to 4 dimensions: width, height, depth and number of channels. Usually, the three first dimensions are used to describe spatial coordinates `(x,y,z)`, while the number of channels is rather used as a vector-valued dimension (it may describe the R,G,B color channels for instance). If you need a fifth dimension, you can use image lists `CImgList<T>` rather than simple images `CImg<T>`.

Thus, the `CImg<T>` class is able to represent volumetric images of vector-valued pixels, as well as images with less dimensions (1D scalar signal, 2D color images, ...). Most member functions of the class [CImg](#structcimg__library__suffixed_1_1CImg)<`T>` are designed to handle this maximum case of (3+1) dimensions.

Concerning the pixel value type `T:` fully supported template types are the basic C++ types: `unsigned char, char, short, unsigned int, int, unsigned long, long, float, double, ... `. Typically, fast image display can be done using `CImg<unsigned char>` images, while complex image processing algorithms may be rather coded using `CImg<float>` or `CImg<double>` images that have floating-point pixel values. The default value for the template T is `float`. Using your own template types may be possible. However, you will certainly have to define the complete set of arithmetic and logical operators for your class.

Image structure

The `CImg<T>` structure contains *six* fields:

* `_width` defines the number of *columns* of the image (size along the X-axis).

* `_height` defines the number of *rows* of the image (size along the Y-axis).

* `_depth` defines the number of *slices* of the image (size along the Z-axis).

* `_spectrum` defines the number of *channels* of the image (size along the C-axis).

* `_data` defines a *pointer* to the *pixel**data* (of type `T`).

* `_is_shared` is a boolean that tells if the memory buffer `data` is shared with another image.

You can access these fields publicly although it is recommended to use the dedicated functions [width()](#structcimg__library__suffixed_1_1CImg_1a2d7b769d447c0451a2f43c77e997beff), [height()](#structcimg__library__suffixed_1_1CImg_1a49834fd555c4a8362100bc628f1b03bb), [depth()](#structcimg__library__suffixed_1_1CImg_1aa708d2050f866a341896aca528615d2d), [spectrum()](#structcimg__library__suffixed_1_1CImg_1a03cdb8e4b45371862c65c3b5be7b697e) and ptr() to do so. Image dimensions are not limited to a specific range (as long as you got enough available memory). A value of *1* usually means that the corresponding dimension is *flat*. If one of the dimensions is *0*, or if the data pointer is null, the image is considered as *empty*. Empty images should not contain any pixel data and thus, will not be processed by [CImg](#structcimg__library__suffixed_1_1CImg) member functions (a [CImgInstanceException](#structcimg__library__suffixed_1_1CImgInstanceException) will be thrown instead). Pixel data are stored in memory, in a non interlaced mode (See cimg_storage).

Image declaration and construction

Declaring an image can be done by using one of the several available constructors. Here is a list of the most used:

* Construct images from arbitrary dimensions:

* `CImg<char> img;` declares an empty image.

* `CImg<unsigned char> img(128,128);` declares a 128x128 greyscale image with `unsigned``char` pixel values.

* `CImg<double> img(3,3);` declares a 3x3 matrix with `double` coefficients.

* `CImg<unsigned char> img(256,256,1,3);` declares a 256x256x1x3 (color) image (colors are stored as an image with three channels).

* `CImg<double> img(128,128,128);` declares a 128x128x128 volumetric and greyscale image (with `double` pixel values).

* `CImg<> img(128,128,128,3);` declares a 128x128x128 volumetric color image (with `float` pixels, which is the default value of the template parameter `T`).

* **Note:** images pixels are **not automatically initialized to 0**. You may use the function `[fill()](#structcimg__library__suffixed_1_1CImg_1ab7ab19191c8b913121d5c99a0e5806db)` to do it, or use the specific constructor taking 5 parameters like this: `CImg<> img(128,128,128,3,0);` declares a 128x128x128 volumetric color image with all pixel values to 0.

* Construct images from filenames:

* `CImg<unsigned char> img("image.jpg");` reads a JPEG color image from the file "image.jpg".

* `CImg<float> img("analyze.hdr");` reads a volumetric image (ANALYZE7.5 format) from the file "analyze.hdr".

* **Note:** You need to install [ImageMagick](http://www.imagemagick.org) to be able to read common compressed image formats (JPG,PNG, ...) (See cimg_files_io).

* Construct images from C-style arrays:

* `CImg<int> img(data_buffer,256,256);` constructs a 256x256 greyscale image from a `int*` buffer `data_buffer` (of size 256x256=65536).

* `CImg<unsigned char> img(data_buffer,256,256,1,3);` constructs a 256x256 color image from a `unsigned``char*` buffer `data_buffer` (where R,G,B channels follow each others).

The complete list of constructors can be found [here](#constructors).

Most useful functions

The `CImg<T>` class contains a lot of functions that operates on images. Some of the most useful are:

* [operator()()](#structcimg__library__suffixed_1_1CImg_1afdb84f77b8c310ea9bf9c430f66cc70b): Read or write pixel values.

* [display()](#structcimg__library__suffixed_1_1CImg_1a33594316b522954b5388986c9b15a52a): displays the image in a new window.

<h2> Summary </h2>

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`public unsigned int `[`_width`](#structcimg__library__suffixed_1_1CImg_1a0fb52e741da8f39570fefedebf5a970b) | 
`public unsigned int `[`_height`](#structcimg__library__suffixed_1_1CImg_1a2c815c82996d0bb78c9f64b766498218) | 
`public unsigned int `[`_depth`](#structcimg__library__suffixed_1_1CImg_1a5661a2492640620e7b4dff12ed1e99b6) | 
`public unsigned int `[`_spectrum`](#structcimg__library__suffixed_1_1CImg_1ab8dbc37ac933ad805b182a8bb0483d7c) | 
`public bool `[`_is_shared`](#structcimg__library__suffixed_1_1CImg_1a8a1879dc877e12b26a13544fb1b6355d) | 
`public T * `[`_data`](#structcimg__library__suffixed_1_1CImg_1ae8b850a56159b640cc21cbf01430f119) | 
`typedef `[`iterator`](#structcimg__library__suffixed_1_1CImg_1a14869a2d3849994eb07f80d2e2c36bbd) | Simple iterator type, to loop through each pixel value of an image instance.
`typedef `[`const_iterator`](#structcimg__library__suffixed_1_1CImg_1a0539e36c0285d3e4647e0ed1919e947e) | Simple const iterator type, to loop through each pixel value of a `const` image instance.
`typedef `[`value_type`](#structcimg__library__suffixed_1_1CImg_1a9a18781e1d4ca73670e52bc4a56ec3d2) | Pixel value type.
`typedef `[`Tbool`](#structcimg__library__suffixed_1_1CImg_1af9120a3f036ea183c84a692f34b3d8f5) | 
`typedef `[`Tuchar`](#structcimg__library__suffixed_1_1CImg_1a279d593df513628024e6c66c168d03d4) | 
`typedef `[`Tchar`](#structcimg__library__suffixed_1_1CImg_1a9755ee74a99b05da9c01085d18a410ae) | 
`typedef `[`Tushort`](#structcimg__library__suffixed_1_1CImg_1aebd60846e12e0613ff972c851bb964c7) | 
`typedef `[`Tshort`](#structcimg__library__suffixed_1_1CImg_1a5db3c76a23a2824a3687f4fd3b6bcfc2) | 
`typedef `[`Tuint`](#structcimg__library__suffixed_1_1CImg_1a990b00a208c1579623b5c06e6ee7b732) | 
`typedef `[`Tint`](#structcimg__library__suffixed_1_1CImg_1ae0adda998c9394adac6c918d131baf68) | 
`typedef `[`Tulong`](#structcimg__library__suffixed_1_1CImg_1a709b31ef3f2a6d17e0fd070eb3d52099) | 
`typedef `[`Tlong`](#structcimg__library__suffixed_1_1CImg_1a578f2935a8c0086600d516780c675412) | 
`typedef `[`Tfloat`](#structcimg__library__suffixed_1_1CImg_1ac99a1d2b7841e864c0b81a77c15d6ff5) | 
`typedef `[`Tdouble`](#structcimg__library__suffixed_1_1CImg_1af531817a5d8fe73ce93ff04af27dbdd1) | 
`typedef `[`boolT`](#structcimg__library__suffixed_1_1CImg_1af9f813311fc2eecb3ccc7195625dd34f) | 
`typedef `[`ucharT`](#structcimg__library__suffixed_1_1CImg_1aec3cc8a101f4fa24560c89f126c71497) | 
`typedef `[`charT`](#structcimg__library__suffixed_1_1CImg_1a7ee8e94692181ac2d028ead0c56b4422) | 
`typedef `[`ushortT`](#structcimg__library__suffixed_1_1CImg_1ac47f9489bb1ef1bd62600a253a853ae8) | 
`typedef `[`shortT`](#structcimg__library__suffixed_1_1CImg_1ab2ba5a4200fad613c5c2634fa1ad05ba) | 
`typedef `[`uintT`](#structcimg__library__suffixed_1_1CImg_1abe0ddc1a5d76635ffe95ebf1300edd0b) | 
`typedef `[`intT`](#structcimg__library__suffixed_1_1CImg_1a970fe290b5a8e6b64cb60a0c6cc1edb9) | 
`typedef `[`ulongT`](#structcimg__library__suffixed_1_1CImg_1a692fbf053375484684d9fe0cfea2cab9) | 
`typedef `[`longT`](#structcimg__library__suffixed_1_1CImg_1a5ed2225864a1d11490ee02fdf028da3c) | 
`typedef `[`uint64T`](#structcimg__library__suffixed_1_1CImg_1af2701f401af7e9480d00f01e0c85c4d9) | 
`typedef `[`int64T`](#structcimg__library__suffixed_1_1CImg_1a0ea8b2546e48e22e75a7fb72aedc69ed) | 
`typedef `[`floatT`](#structcimg__library__suffixed_1_1CImg_1a50cb2b2946ce858006d9a5ca0ca7a1c6) | 
`typedef `[`doubleT`](#structcimg__library__suffixed_1_1CImg_1aa29e255f9578a69500205c5064113006) | 

<h2> Members </h2>

#### `public unsigned int `[`_width`](#structcimg__library__suffixed_1_1CImg_1a0fb52e741da8f39570fefedebf5a970b) {#structcimg__library__suffixed_1_1CImg_1a0fb52e741da8f39570fefedebf5a970b}

#### `public unsigned int `[`_height`](#structcimg__library__suffixed_1_1CImg_1a2c815c82996d0bb78c9f64b766498218) {#structcimg__library__suffixed_1_1CImg_1a2c815c82996d0bb78c9f64b766498218}

#### `public unsigned int `[`_depth`](#structcimg__library__suffixed_1_1CImg_1a5661a2492640620e7b4dff12ed1e99b6) {#structcimg__library__suffixed_1_1CImg_1a5661a2492640620e7b4dff12ed1e99b6}

#### `public unsigned int `[`_spectrum`](#structcimg__library__suffixed_1_1CImg_1ab8dbc37ac933ad805b182a8bb0483d7c) {#structcimg__library__suffixed_1_1CImg_1ab8dbc37ac933ad805b182a8bb0483d7c}

#### `public bool `[`_is_shared`](#structcimg__library__suffixed_1_1CImg_1a8a1879dc877e12b26a13544fb1b6355d) {#structcimg__library__suffixed_1_1CImg_1a8a1879dc877e12b26a13544fb1b6355d}

#### `public T * `[`_data`](#structcimg__library__suffixed_1_1CImg_1ae8b850a56159b640cc21cbf01430f119) {#structcimg__library__suffixed_1_1CImg_1ae8b850a56159b640cc21cbf01430f119}

#### `typedef `[`iterator`](#structcimg__library__suffixed_1_1CImg_1a14869a2d3849994eb07f80d2e2c36bbd) {#structcimg__library__suffixed_1_1CImg_1a14869a2d3849994eb07f80d2e2c36bbd}

Simple iterator type, to loop through each pixel value of an image instance.

* The `[CImg<T>::iterator](#structcimg__library__suffixed_1_1CImg_1a14869a2d3849994eb07f80d2e2c36bbd)` type is defined to be a `T*`.

* You will seldom have to use iterators in CImg, most classical operations being achieved (often in a faster way) using methods of `CImg<T>`. 

Example
```cpp
CImg<float> img("reference.jpg");                                         // Load image from file
// Set all pixels to '0', with a CImg iterator.
for (CImg<float>::iterator it = img.begin(), it<img.end(); ++it) *it = 0;
img.fill(0);                                                              // Do the same with a built-in method
```

#### `typedef `[`const_iterator`](#structcimg__library__suffixed_1_1CImg_1a0539e36c0285d3e4647e0ed1919e947e) {#structcimg__library__suffixed_1_1CImg_1a0539e36c0285d3e4647e0ed1919e947e}

Simple const iterator type, to loop through each pixel value of a `const` image instance.

* The `[CImg<T>::const_iterator](#structcimg__library__suffixed_1_1CImg_1a0539e36c0285d3e4647e0ed1919e947e)` type is defined to be a `const``T*`.

* You will seldom have to use iterators in CImg, most classical operations being achieved (often in a faster way) using methods of `CImg<T>`. 

Example
```cpp
const CImg<float> img("reference.jpg");                                    // Load image from file
float sum = 0;
// Compute sum of all pixel values, with a CImg iterator.
for (CImg<float>::iterator it = img.begin(), it<img.end(); ++it) sum+=*it;
const float sum2 = img.sum();                                              // Do the same with a built-in method
```

#### `typedef `[`value_type`](#structcimg__library__suffixed_1_1CImg_1a9a18781e1d4ca73670e52bc4a56ec3d2) {#structcimg__library__suffixed_1_1CImg_1a9a18781e1d4ca73670e52bc4a56ec3d2}

Pixel value type.

Refer to the type of the pixel values of an image instance. 

* The `[CImg<T>::value_type](#structcimg__library__suffixed_1_1CImg_1a9a18781e1d4ca73670e52bc4a56ec3d2)` type of a `CImg<T>` is defined to be a `T`.

* `[CImg<T>::value_type](#structcimg__library__suffixed_1_1CImg_1a9a18781e1d4ca73670e52bc4a56ec3d2)` is actually not used in CImg methods. It has been mainly defined for compatibility with STL naming conventions.

#### `typedef `[`Tbool`](#structcimg__library__suffixed_1_1CImg_1af9120a3f036ea183c84a692f34b3d8f5) {#structcimg__library__suffixed_1_1CImg_1af9120a3f036ea183c84a692f34b3d8f5}

#### `typedef `[`Tuchar`](#structcimg__library__suffixed_1_1CImg_1a279d593df513628024e6c66c168d03d4) {#structcimg__library__suffixed_1_1CImg_1a279d593df513628024e6c66c168d03d4}

#### `typedef `[`Tchar`](#structcimg__library__suffixed_1_1CImg_1a9755ee74a99b05da9c01085d18a410ae) {#structcimg__library__suffixed_1_1CImg_1a9755ee74a99b05da9c01085d18a410ae}

#### `typedef `[`Tushort`](#structcimg__library__suffixed_1_1CImg_1aebd60846e12e0613ff972c851bb964c7) {#structcimg__library__suffixed_1_1CImg_1aebd60846e12e0613ff972c851bb964c7}

#### `typedef `[`Tshort`](#structcimg__library__suffixed_1_1CImg_1a5db3c76a23a2824a3687f4fd3b6bcfc2) {#structcimg__library__suffixed_1_1CImg_1a5db3c76a23a2824a3687f4fd3b6bcfc2}

#### `typedef `[`Tuint`](#structcimg__library__suffixed_1_1CImg_1a990b00a208c1579623b5c06e6ee7b732) {#structcimg__library__suffixed_1_1CImg_1a990b00a208c1579623b5c06e6ee7b732}

#### `typedef `[`Tint`](#structcimg__library__suffixed_1_1CImg_1ae0adda998c9394adac6c918d131baf68) {#structcimg__library__suffixed_1_1CImg_1ae0adda998c9394adac6c918d131baf68}

#### `typedef `[`Tulong`](#structcimg__library__suffixed_1_1CImg_1a709b31ef3f2a6d17e0fd070eb3d52099) {#structcimg__library__suffixed_1_1CImg_1a709b31ef3f2a6d17e0fd070eb3d52099}

#### `typedef `[`Tlong`](#structcimg__library__suffixed_1_1CImg_1a578f2935a8c0086600d516780c675412) {#structcimg__library__suffixed_1_1CImg_1a578f2935a8c0086600d516780c675412}

#### `typedef `[`Tfloat`](#structcimg__library__suffixed_1_1CImg_1ac99a1d2b7841e864c0b81a77c15d6ff5) {#structcimg__library__suffixed_1_1CImg_1ac99a1d2b7841e864c0b81a77c15d6ff5}

#### `typedef `[`Tdouble`](#structcimg__library__suffixed_1_1CImg_1af531817a5d8fe73ce93ff04af27dbdd1) {#structcimg__library__suffixed_1_1CImg_1af531817a5d8fe73ce93ff04af27dbdd1}

#### `typedef `[`boolT`](#structcimg__library__suffixed_1_1CImg_1af9f813311fc2eecb3ccc7195625dd34f) {#structcimg__library__suffixed_1_1CImg_1af9f813311fc2eecb3ccc7195625dd34f}

#### `typedef `[`ucharT`](#structcimg__library__suffixed_1_1CImg_1aec3cc8a101f4fa24560c89f126c71497) {#structcimg__library__suffixed_1_1CImg_1aec3cc8a101f4fa24560c89f126c71497}

#### `typedef `[`charT`](#structcimg__library__suffixed_1_1CImg_1a7ee8e94692181ac2d028ead0c56b4422) {#structcimg__library__suffixed_1_1CImg_1a7ee8e94692181ac2d028ead0c56b4422}

#### `typedef `[`ushortT`](#structcimg__library__suffixed_1_1CImg_1ac47f9489bb1ef1bd62600a253a853ae8) {#structcimg__library__suffixed_1_1CImg_1ac47f9489bb1ef1bd62600a253a853ae8}

#### `typedef `[`shortT`](#structcimg__library__suffixed_1_1CImg_1ab2ba5a4200fad613c5c2634fa1ad05ba) {#structcimg__library__suffixed_1_1CImg_1ab2ba5a4200fad613c5c2634fa1ad05ba}

#### `typedef `[`uintT`](#structcimg__library__suffixed_1_1CImg_1abe0ddc1a5d76635ffe95ebf1300edd0b) {#structcimg__library__suffixed_1_1CImg_1abe0ddc1a5d76635ffe95ebf1300edd0b}

#### `typedef `[`intT`](#structcimg__library__suffixed_1_1CImg_1a970fe290b5a8e6b64cb60a0c6cc1edb9) {#structcimg__library__suffixed_1_1CImg_1a970fe290b5a8e6b64cb60a0c6cc1edb9}

#### `typedef `[`ulongT`](#structcimg__library__suffixed_1_1CImg_1a692fbf053375484684d9fe0cfea2cab9) {#structcimg__library__suffixed_1_1CImg_1a692fbf053375484684d9fe0cfea2cab9}

#### `typedef `[`longT`](#structcimg__library__suffixed_1_1CImg_1a5ed2225864a1d11490ee02fdf028da3c) {#structcimg__library__suffixed_1_1CImg_1a5ed2225864a1d11490ee02fdf028da3c}

#### `typedef `[`uint64T`](#structcimg__library__suffixed_1_1CImg_1af2701f401af7e9480d00f01e0c85c4d9) {#structcimg__library__suffixed_1_1CImg_1af2701f401af7e9480d00f01e0c85c4d9}

#### `typedef `[`int64T`](#structcimg__library__suffixed_1_1CImg_1a0ea8b2546e48e22e75a7fb72aedc69ed) {#structcimg__library__suffixed_1_1CImg_1a0ea8b2546e48e22e75a7fb72aedc69ed}

#### `typedef `[`floatT`](#structcimg__library__suffixed_1_1CImg_1a50cb2b2946ce858006d9a5ca0ca7a1c6) {#structcimg__library__suffixed_1_1CImg_1a50cb2b2946ce858006d9a5ca0ca7a1c6}

#### `typedef `[`doubleT`](#structcimg__library__suffixed_1_1CImg_1aa29e255f9578a69500205c5064113006) {#structcimg__library__suffixed_1_1CImg_1aa29e255f9578a69500205c5064113006}

# struct `cimg_library_suffixed::CImgAbortException` {#structcimg__library__suffixed_1_1CImgAbortException}

```
struct cimg_library_suffixed::CImgAbortException
  : public exception
```  

<h2> Summary </h2>

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`public char * `[`_message`](#structcimg__library__suffixed_1_1CImgAbortException_1a643797a017b6fa95e29c494eca5089a3) | 
`public inline  `[`CImgAbortException`](#structcimg__library__suffixed_1_1CImgAbortException_1a867e352a40c122d3cf4b4ce96ad9944a)`()` | 
`public inline  `[`CImgAbortException`](#structcimg__library__suffixed_1_1CImgAbortException_1adf8705e3e9e3661bcc0dcfe866cbee38)`(const char *const format,...)` | 
`public inline  `[`CImgAbortException`](#structcimg__library__suffixed_1_1CImgAbortException_1aa8334f5c924b193a348785764bc1e0ec)`(const `[`CImgAbortException`](#structcimg__library__suffixed_1_1CImgAbortException)` & e)` | 
`public inline  `[`~CImgAbortException`](#structcimg__library__suffixed_1_1CImgAbortException_1ab84d17c4d6fb1ee8b255238b107c1f43)`()` | 
`public inline `[`CImgAbortException`](#structcimg__library__suffixed_1_1CImgAbortException)` & `[`operator=`](#structcimg__library__suffixed_1_1CImgAbortException_1ac2c260f782c687b4edd9517666186e35)`(const `[`CImgAbortException`](#structcimg__library__suffixed_1_1CImgAbortException)` & e)` | 
`public inline const char * `[`what`](#structcimg__library__suffixed_1_1CImgAbortException_1af7cb17b05e7948bfdfb391f114a581f8)`() const` | Return a C-string containing the error message associated to the thrown exception.

<h2> Members </h2>

#### `public char * `[`_message`](#structcimg__library__suffixed_1_1CImgAbortException_1a643797a017b6fa95e29c494eca5089a3) {#structcimg__library__suffixed_1_1CImgAbortException_1a643797a017b6fa95e29c494eca5089a3}

#### `public inline  `[`CImgAbortException`](#structcimg__library__suffixed_1_1CImgAbortException_1a867e352a40c122d3cf4b4ce96ad9944a)`()` {#structcimg__library__suffixed_1_1CImgAbortException_1a867e352a40c122d3cf4b4ce96ad9944a}

#### `public inline  `[`CImgAbortException`](#structcimg__library__suffixed_1_1CImgAbortException_1adf8705e3e9e3661bcc0dcfe866cbee38)`(const char *const format,...)` {#structcimg__library__suffixed_1_1CImgAbortException_1adf8705e3e9e3661bcc0dcfe866cbee38}

#### `public inline  `[`CImgAbortException`](#structcimg__library__suffixed_1_1CImgAbortException_1aa8334f5c924b193a348785764bc1e0ec)`(const `[`CImgAbortException`](#structcimg__library__suffixed_1_1CImgAbortException)` & e)` {#structcimg__library__suffixed_1_1CImgAbortException_1aa8334f5c924b193a348785764bc1e0ec}

#### `public inline  `[`~CImgAbortException`](#structcimg__library__suffixed_1_1CImgAbortException_1ab84d17c4d6fb1ee8b255238b107c1f43)`()` {#structcimg__library__suffixed_1_1CImgAbortException_1ab84d17c4d6fb1ee8b255238b107c1f43}

#### `public inline `[`CImgAbortException`](#structcimg__library__suffixed_1_1CImgAbortException)` & `[`operator=`](#structcimg__library__suffixed_1_1CImgAbortException_1ac2c260f782c687b4edd9517666186e35)`(const `[`CImgAbortException`](#structcimg__library__suffixed_1_1CImgAbortException)` & e)` {#structcimg__library__suffixed_1_1CImgAbortException_1ac2c260f782c687b4edd9517666186e35}

#### `public inline const char * `[`what`](#structcimg__library__suffixed_1_1CImgAbortException_1af7cb17b05e7948bfdfb391f114a581f8)`() const` {#structcimg__library__suffixed_1_1CImgAbortException_1af7cb17b05e7948bfdfb391f114a581f8}

Return a C-string containing the error message associated to the thrown exception.

# struct `cimg_library_suffixed::CImgArgumentException` {#structcimg__library__suffixed_1_1CImgArgumentException}

```
struct cimg_library_suffixed::CImgArgumentException
  : public cimg_library_suffixed::CImgException
```  

<h2> Summary </h2>

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`public inline  `[`CImgArgumentException`](#structcimg__library__suffixed_1_1CImgArgumentException_1aa9078e8f95f0a437aac753b505a79255)`(const char *const format,...)` | 

<h2> Members </h2>

#### `public inline  `[`CImgArgumentException`](#structcimg__library__suffixed_1_1CImgArgumentException_1aa9078e8f95f0a437aac753b505a79255)`(const char *const format,...)` {#structcimg__library__suffixed_1_1CImgArgumentException_1aa9078e8f95f0a437aac753b505a79255}

# struct `cimg_library_suffixed::CImgDisplayException` {#structcimg__library__suffixed_1_1CImgDisplayException}

```
struct cimg_library_suffixed::CImgDisplayException
  : public cimg_library_suffixed::CImgException
```  

<h2> Summary </h2>

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`public inline  `[`CImgDisplayException`](#structcimg__library__suffixed_1_1CImgDisplayException_1aafc67056995f77844b87464aee4a0c81)`(const char *const format,...)` | 

<h2> Members </h2>

#### `public inline  `[`CImgDisplayException`](#structcimg__library__suffixed_1_1CImgDisplayException_1aafc67056995f77844b87464aee4a0c81)`(const char *const format,...)` {#structcimg__library__suffixed_1_1CImgDisplayException_1aafc67056995f77844b87464aee4a0c81}

# struct `cimg_library_suffixed::CImgException` {#structcimg__library__suffixed_1_1CImgException}

```
struct cimg_library_suffixed::CImgException
  : public exception
```  

Instances of `[CImgException](#structcimg__library__suffixed_1_1CImgException)` are thrown when errors are encountered in a \CImg function call.

Overview

[CImgException](#structcimg__library__suffixed_1_1CImgException) is the base class of all exceptions thrown by \CImg (except **[CImgAbortException](#structcimg__library__suffixed_1_1CImgAbortException)**). [CImgException](#structcimg__library__suffixed_1_1CImgException) is never thrown itself. Derived classes that specify the type of errord are thrown instead. These classes can be:

* **[CImgAbortException](#structcimg__library__suffixed_1_1CImgAbortException):** Thrown when a computationally-intensive function is aborted by an external signal. This is the only `non-derived` exception class.

* **[CImgArgumentException](#structcimg__library__suffixed_1_1CImgArgumentException):** Thrown when one argument of a called \CImg function is invalid. This is probably one of the most thrown exception by \CImg. For instance, the following example throws a `[CImgArgumentException](#structcimg__library__suffixed_1_1CImgArgumentException):`
```cpp
CImg<float> img(100,100,1,3); // Define a 100x100 color image with float-valued pixels
img.mirror('e');              // Try to mirror image along the (non-existing) 'e'-axis
```

* **[CImgDisplayException](#structcimg__library__suffixed_1_1CImgDisplayException):** Thrown when something went wrong during the display of images in CImgDisplay instances.

* **[CImgInstanceException](#structcimg__library__suffixed_1_1CImgInstanceException):** Thrown when an instance associated to a called \CImg method does not fit the function requirements. For instance, the following example throws a `[CImgInstanceException](#structcimg__library__suffixed_1_1CImgInstanceException):`
```cpp
const CImg<float> img;           // Define an empty image
const float value = img.at(0);   // Try to read first pixel value (does not exist)
```

* **[CImgIOException](#structcimg__library__suffixed_1_1CImgIOException):** Thrown when an error occurred when trying to load or save image files. This happens when trying to read files that do not exist or with invalid formats. For instance, the following example throws a `[CImgIOException](#structcimg__library__suffixed_1_1CImgIOException):`
```cpp
const CImg<float> img("missing_file.jpg");  // Try to load a file that does not exist
```

* **[CImgWarningException](#structcimg__library__suffixed_1_1CImgWarningException):** Thrown only if configuration macro `cimg_strict_warnings` is set, and when a \CImg function has to display a warning message (see [cimg::warn()](#namespacecimg__library__suffixed_1_1cimg_1acfd3624d72ed7f79c82ec45646c685e7)).

It is not recommended to throw [CImgException](#structcimg__library__suffixed_1_1CImgException) instances by yourself, since they are expected to be thrown only by \CImg. When an error occurs in a library function call, \CImg may display error messages on the screen or on the standard output, depending on the current \CImg exception mode. The \CImg exception mode can be get and set by functions cimg::exception_mode() and [cimg::exception_mode(unsigned int)](#namespacecimg__library__suffixed_1_1cimg_1aeafab144366eddd11360f32f468fa4af).

Exceptions handling

In all cases, when an error occurs in \CImg, an instance of the corresponding exception class is thrown. This may lead the program to break (this is the default behavior), but you can bypass this behavior by handling the exceptions by yourself, using a usual `try { ... } catch () { ... }` bloc, as in the following example: 
```cpp
#define "CImg.h"
using namespace cimg_library;
int main() {
  cimg::exception_mode(0);                                    // Enable quiet exception mode
  try {
    ...                                                       // Here, do what you want to stress CImg
  } catch (CImgException& e) {                                // You succeeded: something went wrong!
    std::fprintf(stderr,"CImg Library Error: %s",e.what());   // Display your custom error message
    ...                                                       // Do what you want now to save the ship!
    }
  }
```

<h2> Summary </h2>

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`public char * `[`_message`](#structcimg__library__suffixed_1_1CImgException_1a2d0626fd8caeca943cacb751fe1ea127) | 
`public inline  `[`CImgException`](#structcimg__library__suffixed_1_1CImgException_1a1931cba265f653b52806c4361f3cecfc)`()` | 
`public inline  `[`CImgException`](#structcimg__library__suffixed_1_1CImgException_1aeb349b6446eb9bd5ca8a6c0106e69c34)`(const char *const format,...)` | 
`public inline  `[`CImgException`](#structcimg__library__suffixed_1_1CImgException_1ac8463f57e62e505d097d73008f922206)`(const `[`CImgException`](#structcimg__library__suffixed_1_1CImgException)` & e)` | 
`public inline  `[`~CImgException`](#structcimg__library__suffixed_1_1CImgException_1af2c1c1826a82f38d74dacf72c9db6c82)`()` | 
`public inline `[`CImgException`](#structcimg__library__suffixed_1_1CImgException)` & `[`operator=`](#structcimg__library__suffixed_1_1CImgException_1aefe4482f16f1b615abe8b9407ec54a01)`(const `[`CImgException`](#structcimg__library__suffixed_1_1CImgException)` & e)` | 
`public inline const char * `[`what`](#structcimg__library__suffixed_1_1CImgException_1a7ce3499518ace836d2b11ebafb078714)`() const` | Return a C-string containing the error message associated to the thrown exception.

<h2> Members </h2>

#### `public char * `[`_message`](#structcimg__library__suffixed_1_1CImgException_1a2d0626fd8caeca943cacb751fe1ea127) {#structcimg__library__suffixed_1_1CImgException_1a2d0626fd8caeca943cacb751fe1ea127}

#### `public inline  `[`CImgException`](#structcimg__library__suffixed_1_1CImgException_1a1931cba265f653b52806c4361f3cecfc)`()` {#structcimg__library__suffixed_1_1CImgException_1a1931cba265f653b52806c4361f3cecfc}

#### `public inline  `[`CImgException`](#structcimg__library__suffixed_1_1CImgException_1aeb349b6446eb9bd5ca8a6c0106e69c34)`(const char *const format,...)` {#structcimg__library__suffixed_1_1CImgException_1aeb349b6446eb9bd5ca8a6c0106e69c34}

#### `public inline  `[`CImgException`](#structcimg__library__suffixed_1_1CImgException_1ac8463f57e62e505d097d73008f922206)`(const `[`CImgException`](#structcimg__library__suffixed_1_1CImgException)` & e)` {#structcimg__library__suffixed_1_1CImgException_1ac8463f57e62e505d097d73008f922206}

#### `public inline  `[`~CImgException`](#structcimg__library__suffixed_1_1CImgException_1af2c1c1826a82f38d74dacf72c9db6c82)`()` {#structcimg__library__suffixed_1_1CImgException_1af2c1c1826a82f38d74dacf72c9db6c82}

#### `public inline `[`CImgException`](#structcimg__library__suffixed_1_1CImgException)` & `[`operator=`](#structcimg__library__suffixed_1_1CImgException_1aefe4482f16f1b615abe8b9407ec54a01)`(const `[`CImgException`](#structcimg__library__suffixed_1_1CImgException)` & e)` {#structcimg__library__suffixed_1_1CImgException_1aefe4482f16f1b615abe8b9407ec54a01}

#### `public inline const char * `[`what`](#structcimg__library__suffixed_1_1CImgException_1a7ce3499518ace836d2b11ebafb078714)`() const` {#structcimg__library__suffixed_1_1CImgException_1a7ce3499518ace836d2b11ebafb078714}

Return a C-string containing the error message associated to the thrown exception.

# struct `cimg_library_suffixed::CImgInstanceException` {#structcimg__library__suffixed_1_1CImgInstanceException}

```
struct cimg_library_suffixed::CImgInstanceException
  : public cimg_library_suffixed::CImgException
```  

<h2> Summary </h2>

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`public inline  `[`CImgInstanceException`](#structcimg__library__suffixed_1_1CImgInstanceException_1a2fdde8bb00abef3ce8522891813a9669)`(const char *const format,...)` | 

<h2> Members </h2>

#### `public inline  `[`CImgInstanceException`](#structcimg__library__suffixed_1_1CImgInstanceException_1a2fdde8bb00abef3ce8522891813a9669)`(const char *const format,...)` {#structcimg__library__suffixed_1_1CImgInstanceException_1a2fdde8bb00abef3ce8522891813a9669}

# struct `cimg_library_suffixed::CImgIOException` {#structcimg__library__suffixed_1_1CImgIOException}

```
struct cimg_library_suffixed::CImgIOException
  : public cimg_library_suffixed::CImgException
```  

<h2> Summary </h2>

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`public inline  `[`CImgIOException`](#structcimg__library__suffixed_1_1CImgIOException_1a19c7321d0ecaaffe9a03cdfe88e415d3)`(const char *const format,...)` | 

<h2> Members </h2>

#### `public inline  `[`CImgIOException`](#structcimg__library__suffixed_1_1CImgIOException_1a19c7321d0ecaaffe9a03cdfe88e415d3)`(const char *const format,...)` {#structcimg__library__suffixed_1_1CImgIOException_1a19c7321d0ecaaffe9a03cdfe88e415d3}

# struct `cimg_library_suffixed::CImgList` {#structcimg__library__suffixed_1_1CImgList}

Represent a list of images CImg<T>.

<h2> Summary </h2>

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`public unsigned int `[`_width`](#structcimg__library__suffixed_1_1CImgList_1a6f9bc43113f7f386e9b1396b2889c5d3) | 
`public unsigned int `[`_allocated_width`](#structcimg__library__suffixed_1_1CImgList_1ac8e0786da3407973bc1284b7195c6d55) | 
`public `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< T > * `[`_data`](#structcimg__library__suffixed_1_1CImgList_1a9ef8a2d3cfb63e192fe80dd8ba6690f1) | 
`typedef `[`iterator`](#structcimg__library__suffixed_1_1CImgList_1a9d3e27da63f536e04fc7249f8e13dba0) | Simple iterator type, to loop through each image of a list.
`typedef `[`const_iterator`](#structcimg__library__suffixed_1_1CImgList_1aabe27c2b223cefcbdf081b4a7220a12c) | Simple const iterator type, to loop through each image of a `const` list instance.
`typedef `[`value_type`](#structcimg__library__suffixed_1_1CImgList_1a41c952483793b049e58c27e11d0dd955) | Pixel value type.
`typedef `[`Tbool`](#structcimg__library__suffixed_1_1CImgList_1adbc918d6001bebb2c58c29fd7a02e6dc) | 
`typedef `[`Tuchar`](#structcimg__library__suffixed_1_1CImgList_1ae0e7fd20ee83fc3894adf49228c4efc2) | 
`typedef `[`Tchar`](#structcimg__library__suffixed_1_1CImgList_1a698ba0821e5fdf35b768987e77816e06) | 
`typedef `[`Tushort`](#structcimg__library__suffixed_1_1CImgList_1aefc9a2fe749ea170f37daee8f648ef67) | 
`typedef `[`Tshort`](#structcimg__library__suffixed_1_1CImgList_1a4787438e887574d76655f91532dfc555) | 
`typedef `[`Tuint`](#structcimg__library__suffixed_1_1CImgList_1a8544fe0471528d6ee475803ee2a36030) | 
`typedef `[`Tint`](#structcimg__library__suffixed_1_1CImgList_1a9447dbcd1c144ec5160be27c57572917) | 
`typedef `[`Tulong`](#structcimg__library__suffixed_1_1CImgList_1aa1c4ef2b4d20cb5998a1acf8cba2da7c) | 
`typedef `[`Tlong`](#structcimg__library__suffixed_1_1CImgList_1a8523f4336fc22d88ea88aca981e249b8) | 
`typedef `[`Tfloat`](#structcimg__library__suffixed_1_1CImgList_1a56ac847894baf3d10a1be80588a472e1) | 
`typedef `[`Tdouble`](#structcimg__library__suffixed_1_1CImgList_1a7874415813d2e7ad9a9297a4e0c01754) | 
`typedef `[`boolT`](#structcimg__library__suffixed_1_1CImgList_1a7093deeaa6a2ae97a4cad25d2390f758) | 
`typedef `[`ucharT`](#structcimg__library__suffixed_1_1CImgList_1a06143e363521f0726eff9415a3b5dfea) | 
`typedef `[`charT`](#structcimg__library__suffixed_1_1CImgList_1a29bbd635ce69d6aee355779b18a6af13) | 
`typedef `[`ushortT`](#structcimg__library__suffixed_1_1CImgList_1a774c75c437b7f29c9add3547f7671c3c) | 
`typedef `[`shortT`](#structcimg__library__suffixed_1_1CImgList_1ac6ec88195533b60a3e4f83514a8dfceb) | 
`typedef `[`uintT`](#structcimg__library__suffixed_1_1CImgList_1a005e0d214bd6413939703b430dc7a31e) | 
`typedef `[`intT`](#structcimg__library__suffixed_1_1CImgList_1adac27d2335329f6cc29fbe5ca1cef164) | 
`typedef `[`ulongT`](#structcimg__library__suffixed_1_1CImgList_1a033f2499c9784b95a95047e11d715776) | 
`typedef `[`longT`](#structcimg__library__suffixed_1_1CImgList_1acbda05b513f31a43d3bd7ac64b722e8c) | 
`typedef `[`uint64T`](#structcimg__library__suffixed_1_1CImgList_1a3a12146f7afb9144e2ed3cf3f0c4c1e6) | 
`typedef `[`int64T`](#structcimg__library__suffixed_1_1CImgList_1a20df7f7a3e03ff9d2f25a6537fa95de6) | 
`typedef `[`floatT`](#structcimg__library__suffixed_1_1CImgList_1ad45ff176cc23643fb0fcf3f4ab00e9cc) | 
`typedef `[`doubleT`](#structcimg__library__suffixed_1_1CImgList_1a307bd3b95847502b40d0aca77ec5783f) | 

<h2> Members </h2>

#### `public unsigned int `[`_width`](#structcimg__library__suffixed_1_1CImgList_1a6f9bc43113f7f386e9b1396b2889c5d3) {#structcimg__library__suffixed_1_1CImgList_1a6f9bc43113f7f386e9b1396b2889c5d3}

#### `public unsigned int `[`_allocated_width`](#structcimg__library__suffixed_1_1CImgList_1ac8e0786da3407973bc1284b7195c6d55) {#structcimg__library__suffixed_1_1CImgList_1ac8e0786da3407973bc1284b7195c6d55}

#### `public `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< T > * `[`_data`](#structcimg__library__suffixed_1_1CImgList_1a9ef8a2d3cfb63e192fe80dd8ba6690f1) {#structcimg__library__suffixed_1_1CImgList_1a9ef8a2d3cfb63e192fe80dd8ba6690f1}

#### `typedef `[`iterator`](#structcimg__library__suffixed_1_1CImgList_1a9d3e27da63f536e04fc7249f8e13dba0) {#structcimg__library__suffixed_1_1CImgList_1a9d3e27da63f536e04fc7249f8e13dba0}

Simple iterator type, to loop through each image of a list.

* The `[CImgList<T>::iterator](#structcimg__library__suffixed_1_1CImgList_1a9d3e27da63f536e04fc7249f8e13dba0)` type is defined as a `CImg<T>*`.

* You may use it like this: 
```cpp
CImgList<> list;   // Assuming this image list is not empty
for (CImgList<>::iterator it = list.begin(); it<list.end(); ++it) (*it).mirror('x');
```

* Using the loop macro `cimglist_for` is another (more concise) alternative: 
```cpp
cimglist_for(list,l) list[l].mirror('x');
```

#### `typedef `[`const_iterator`](#structcimg__library__suffixed_1_1CImgList_1aabe27c2b223cefcbdf081b4a7220a12c) {#structcimg__library__suffixed_1_1CImgList_1aabe27c2b223cefcbdf081b4a7220a12c}

Simple const iterator type, to loop through each image of a `const` list instance.

* The `[CImgList<T>::const_iterator](#structcimg__library__suffixed_1_1CImgList_1aabe27c2b223cefcbdf081b4a7220a12c)` type is defined to be a `const CImg<T>*`.

* Similar to [CImgList<T>::iterator](#structcimg__library__suffixed_1_1CImgList_1a9d3e27da63f536e04fc7249f8e13dba0), but for constant list instances.

#### `typedef `[`value_type`](#structcimg__library__suffixed_1_1CImgList_1a41c952483793b049e58c27e11d0dd955) {#structcimg__library__suffixed_1_1CImgList_1a41c952483793b049e58c27e11d0dd955}

Pixel value type.

Refer to the pixels value type of the images in the list. 

* The `[CImgList<T>::value_type](#structcimg__library__suffixed_1_1CImgList_1a41c952483793b049e58c27e11d0dd955)` type of a `CImgList<T>` is defined to be a `T`. It is then similar to [CImg<T>::value_type](#structcimg__library__suffixed_1_1CImg_1a9a18781e1d4ca73670e52bc4a56ec3d2).

* `[CImgList<T>::value_type](#structcimg__library__suffixed_1_1CImgList_1a41c952483793b049e58c27e11d0dd955)` is actually not used in CImg methods. It has been mainly defined for compatibility with STL naming conventions.

#### `typedef `[`Tbool`](#structcimg__library__suffixed_1_1CImgList_1adbc918d6001bebb2c58c29fd7a02e6dc) {#structcimg__library__suffixed_1_1CImgList_1adbc918d6001bebb2c58c29fd7a02e6dc}

#### `typedef `[`Tuchar`](#structcimg__library__suffixed_1_1CImgList_1ae0e7fd20ee83fc3894adf49228c4efc2) {#structcimg__library__suffixed_1_1CImgList_1ae0e7fd20ee83fc3894adf49228c4efc2}

#### `typedef `[`Tchar`](#structcimg__library__suffixed_1_1CImgList_1a698ba0821e5fdf35b768987e77816e06) {#structcimg__library__suffixed_1_1CImgList_1a698ba0821e5fdf35b768987e77816e06}

#### `typedef `[`Tushort`](#structcimg__library__suffixed_1_1CImgList_1aefc9a2fe749ea170f37daee8f648ef67) {#structcimg__library__suffixed_1_1CImgList_1aefc9a2fe749ea170f37daee8f648ef67}

#### `typedef `[`Tshort`](#structcimg__library__suffixed_1_1CImgList_1a4787438e887574d76655f91532dfc555) {#structcimg__library__suffixed_1_1CImgList_1a4787438e887574d76655f91532dfc555}

#### `typedef `[`Tuint`](#structcimg__library__suffixed_1_1CImgList_1a8544fe0471528d6ee475803ee2a36030) {#structcimg__library__suffixed_1_1CImgList_1a8544fe0471528d6ee475803ee2a36030}

#### `typedef `[`Tint`](#structcimg__library__suffixed_1_1CImgList_1a9447dbcd1c144ec5160be27c57572917) {#structcimg__library__suffixed_1_1CImgList_1a9447dbcd1c144ec5160be27c57572917}

#### `typedef `[`Tulong`](#structcimg__library__suffixed_1_1CImgList_1aa1c4ef2b4d20cb5998a1acf8cba2da7c) {#structcimg__library__suffixed_1_1CImgList_1aa1c4ef2b4d20cb5998a1acf8cba2da7c}

#### `typedef `[`Tlong`](#structcimg__library__suffixed_1_1CImgList_1a8523f4336fc22d88ea88aca981e249b8) {#structcimg__library__suffixed_1_1CImgList_1a8523f4336fc22d88ea88aca981e249b8}

#### `typedef `[`Tfloat`](#structcimg__library__suffixed_1_1CImgList_1a56ac847894baf3d10a1be80588a472e1) {#structcimg__library__suffixed_1_1CImgList_1a56ac847894baf3d10a1be80588a472e1}

#### `typedef `[`Tdouble`](#structcimg__library__suffixed_1_1CImgList_1a7874415813d2e7ad9a9297a4e0c01754) {#structcimg__library__suffixed_1_1CImgList_1a7874415813d2e7ad9a9297a4e0c01754}

#### `typedef `[`boolT`](#structcimg__library__suffixed_1_1CImgList_1a7093deeaa6a2ae97a4cad25d2390f758) {#structcimg__library__suffixed_1_1CImgList_1a7093deeaa6a2ae97a4cad25d2390f758}

#### `typedef `[`ucharT`](#structcimg__library__suffixed_1_1CImgList_1a06143e363521f0726eff9415a3b5dfea) {#structcimg__library__suffixed_1_1CImgList_1a06143e363521f0726eff9415a3b5dfea}

#### `typedef `[`charT`](#structcimg__library__suffixed_1_1CImgList_1a29bbd635ce69d6aee355779b18a6af13) {#structcimg__library__suffixed_1_1CImgList_1a29bbd635ce69d6aee355779b18a6af13}

#### `typedef `[`ushortT`](#structcimg__library__suffixed_1_1CImgList_1a774c75c437b7f29c9add3547f7671c3c) {#structcimg__library__suffixed_1_1CImgList_1a774c75c437b7f29c9add3547f7671c3c}

#### `typedef `[`shortT`](#structcimg__library__suffixed_1_1CImgList_1ac6ec88195533b60a3e4f83514a8dfceb) {#structcimg__library__suffixed_1_1CImgList_1ac6ec88195533b60a3e4f83514a8dfceb}

#### `typedef `[`uintT`](#structcimg__library__suffixed_1_1CImgList_1a005e0d214bd6413939703b430dc7a31e) {#structcimg__library__suffixed_1_1CImgList_1a005e0d214bd6413939703b430dc7a31e}

#### `typedef `[`intT`](#structcimg__library__suffixed_1_1CImgList_1adac27d2335329f6cc29fbe5ca1cef164) {#structcimg__library__suffixed_1_1CImgList_1adac27d2335329f6cc29fbe5ca1cef164}

#### `typedef `[`ulongT`](#structcimg__library__suffixed_1_1CImgList_1a033f2499c9784b95a95047e11d715776) {#structcimg__library__suffixed_1_1CImgList_1a033f2499c9784b95a95047e11d715776}

#### `typedef `[`longT`](#structcimg__library__suffixed_1_1CImgList_1acbda05b513f31a43d3bd7ac64b722e8c) {#structcimg__library__suffixed_1_1CImgList_1acbda05b513f31a43d3bd7ac64b722e8c}

#### `typedef `[`uint64T`](#structcimg__library__suffixed_1_1CImgList_1a3a12146f7afb9144e2ed3cf3f0c4c1e6) {#structcimg__library__suffixed_1_1CImgList_1a3a12146f7afb9144e2ed3cf3f0c4c1e6}

#### `typedef `[`int64T`](#structcimg__library__suffixed_1_1CImgList_1a20df7f7a3e03ff9d2f25a6537fa95de6) {#structcimg__library__suffixed_1_1CImgList_1a20df7f7a3e03ff9d2f25a6537fa95de6}

#### `typedef `[`floatT`](#structcimg__library__suffixed_1_1CImgList_1ad45ff176cc23643fb0fcf3f4ab00e9cc) {#structcimg__library__suffixed_1_1CImgList_1ad45ff176cc23643fb0fcf3f4ab00e9cc}

#### `typedef `[`doubleT`](#structcimg__library__suffixed_1_1CImgList_1a307bd3b95847502b40d0aca77ec5783f) {#structcimg__library__suffixed_1_1CImgList_1a307bd3b95847502b40d0aca77ec5783f}

# struct `cimg_library_suffixed::CImgWarningException` {#structcimg__library__suffixed_1_1CImgWarningException}

```
struct cimg_library_suffixed::CImgWarningException
  : public cimg_library_suffixed::CImgException
```  

<h2> Summary </h2>

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`public inline  `[`CImgWarningException`](#structcimg__library__suffixed_1_1CImgWarningException_1a8e14e33d236b90bfc20fa39a35bf13e4)`(const char *const format,...)` | 

<h2> Members </h2>

#### `public inline  `[`CImgWarningException`](#structcimg__library__suffixed_1_1CImgWarningException_1a8e14e33d236b90bfc20fa39a35bf13e4)`(const char *const format,...)` {#structcimg__library__suffixed_1_1CImgWarningException_1a8e14e33d236b90bfc20fa39a35bf13e4}

# namespace `cimg_library_suffixed::cimg` {#namespacecimg__library__suffixed_1_1cimg}

Contains *low-level* functions and variables of the \CImg Library.

Most of the functions and variables within this namespace are used by the \CImg library for low-level operations. You may use them to access specific const values or environment variables internally used by \CImg. Never write `using namespace cimg_library::cimg;` in your source code. Lot of functions in the `cimg:: namespace` have the same names as standard C functions that may be defined in the global namespace `::`.

<h2> Summary </h2>

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`public inline std::FILE * `[`output`](#namespacecimg__library__suffixed_1_1cimg_1ada686776cc71803df391eea79cd1b3e5)`(std::FILE * file)`            | Get/set default output stream for the \CImg library messages.
`public inline void `[`info`](#namespacecimg__library__suffixed_1_1cimg_1a79b7a247520612001a04d8ef1c2991dc)`()`            | Print information about \CImg environment variables.
`public template<>`  <br/>`inline void `[`unused`](#namespacecimg__library__suffixed_1_1cimg_1a79aef0cbcf66ceb71c2b74cb66b4deb2)`(const T &,...)`            | Avoid warning messages due to unused parameters. Do nothing actually.
`public inline int `[`mutex`](#namespacecimg__library__suffixed_1_1cimg_1a9e739e4b4ac058abfba069466617b914)`(const unsigned int n,const int lock_mode)`            | 
`public inline unsigned int & `[`exception_mode`](#namespacecimg__library__suffixed_1_1cimg_1a9414cac8b0ab20669320c37878fe54cc)`(const unsigned int value,const bool is_set)`            | 
`public inline FILE * `[`_stdin`](#namespacecimg__library__suffixed_1_1cimg_1a01a3b743897290604513ea6d847c9886)`(const bool throw_exception)`            | 
`public inline FILE * `[`_stdout`](#namespacecimg__library__suffixed_1_1cimg_1a493220746e5df3466568bd7862825008)`(const bool throw_exception)`            | 
`public inline FILE * `[`_stderr`](#namespacecimg__library__suffixed_1_1cimg_1aab8db7528c32a8fd3a3dc471e662782e)`(const bool throw_exception)`            | 
`public inline unsigned int & `[`exception_mode`](#namespacecimg__library__suffixed_1_1cimg_1aeafab144366eddd11360f32f468fa4af)`(const unsigned int mode)`            | Set current \CImg exception mode.
`public inline unsigned int & `[`exception_mode`](#namespacecimg__library__suffixed_1_1cimg_1a3ee303866379f1c38eb4807afb3c946a)`()`            | Return current \CImg exception mode.
`public inline unsigned int `[`openmp_mode`](#namespacecimg__library__suffixed_1_1cimg_1a06322e0d3fc278be42e1b3ca3dc3c3d4)`(const unsigned int value,const bool is_set)`            | 
`public inline unsigned int `[`openmp_mode`](#namespacecimg__library__suffixed_1_1cimg_1a11975ce0856ede8abd5789e37d82de56)`(const unsigned int mode)`            | Set current \CImg openmp mode.
`public inline unsigned int `[`openmp_mode`](#namespacecimg__library__suffixed_1_1cimg_1add0bfd01ecfbfdd24cccf9d2d5640d92)`()`            | Return current \CImg openmp mode.
`public inline int `[`dialog`](#namespacecimg__library__suffixed_1_1cimg_1a89ad6cacc2ade7f8077d34fc6f455dc3)`(const char *const title,const char *const msg,const char *const button1_label,const char *const button2_label,const char *const button3_label,const char *const button4_label,const char *const button5_label,const char *const button6_label,const bool centering)`            | Display a simple dialog box, and wait for the user's response \specialization.
`public inline double `[`eval`](#namespacecimg__library__suffixed_1_1cimg_1a4574a27654d00ba42a108368fa9d7e64)`(const char *const expression,const double x,const double y,const double z,const double c)`            | Evaluate math expression.
`public inline `[`Mutex_static`](#structcimg__library__suffixed_1_1cimg_1_1Mutex__static)` & `[`Mutex_attr`](#namespacecimg__library__suffixed_1_1cimg_1a0e04fc458732d8608e2739ba724757af)`()`            | 
`public inline unsigned int `[`nb_cpus`](#namespacecimg__library__suffixed_1_1cimg_1ad359a27ccc2eea27d3a6f1073b2a2ad7)`()`            | 
`public inline void `[`warn`](#namespacecimg__library__suffixed_1_1cimg_1acfd3624d72ed7f79c82ec45646c685e7)`(const char *const format,...)`            | Display a warning message on the default output stream.
`public inline int `[`system`](#namespacecimg__library__suffixed_1_1cimg_1a5ddfa532b09b12973f543977f1f688da)`(const char *const command,const char *const module_name,const bool is_verbose)`            | #### Parameters
`public template<>`  <br/>`inline T & `[`temporary`](#namespacecimg__library__suffixed_1_1cimg_1af931f5a4ed9addcbb7a7d27abd7670e5)`(const T &)`            | Return a reference to a temporary variable of type T.
`public template<>`  <br/>`inline void `[`swap`](#namespacecimg__library__suffixed_1_1cimg_1a337eb7828c4ba8532f16e55d0c1468d6)`(T & a,T & b)`            | Exchange values of variables `a` and `b`.
`public template<>`  <br/>`inline void `[`swap`](#namespacecimg__library__suffixed_1_1cimg_1aa4d77ad5aa3b88a07257c583a1b5d475)`(T1 & a1,T1 & b1,T2 & a2,T2 & b2)`            | Exchange values of variables (`a1`,`a2`) and (`b1`,`b2`).
`public template<>`  <br/>`inline void `[`swap`](#namespacecimg__library__suffixed_1_1cimg_1a8e3fcd4b409a2dbd6e61492e2314ed54)`(T1 & a1,T1 & b1,T2 & a2,T2 & b2,T3 & a3,T3 & b3)`            | Exchange values of variables (`a1`,`a2`,`a3`) and (`b1`,`b2`,`b3`).
`public template<>`  <br/>`inline void `[`swap`](#namespacecimg__library__suffixed_1_1cimg_1af4d154f5618084396d21cad69ad479d9)`(T1 & a1,T1 & b1,T2 & a2,T2 & b2,T3 & a3,T3 & b3,T4 & a4,T4 & b4)`            | Exchange values of variables (`a1`,`a2`,...,`a4`) and (`b1`,`b2`,...,`b4`).
`public template<>`  <br/>`inline void `[`swap`](#namespacecimg__library__suffixed_1_1cimg_1a33b9455bf35220ad528091a83ac68707)`(T1 & a1,T1 & b1,T2 & a2,T2 & b2,T3 & a3,T3 & b3,T4 & a4,T4 & b4,T5 & a5,T5 & b5)`            | Exchange values of variables (`a1`,`a2`,...,`a5`) and (`b1`,`b2`,...,`b5`).
`public template<>`  <br/>`inline void `[`swap`](#namespacecimg__library__suffixed_1_1cimg_1a36c2243bde47df38d2d29c32a044e531)`(T1 & a1,T1 & b1,T2 & a2,T2 & b2,T3 & a3,T3 & b3,T4 & a4,T4 & b4,T5 & a5,T5 & b5,T6 & a6,T6 & b6)`            | Exchange values of variables (`a1`,`a2`,...,`a6`) and (`b1`,`b2`,...,`b6`).
`public template<>`  <br/>`inline void `[`swap`](#namespacecimg__library__suffixed_1_1cimg_1aca980117982a98452e2106fda638def1)`(T1 & a1,T1 & b1,T2 & a2,T2 & b2,T3 & a3,T3 & b3,T4 & a4,T4 & b4,T5 & a5,T5 & b5,T6 & a6,T6 & b6,T7 & a7,T7 & b7)`            | Exchange values of variables (`a1`,`a2`,...,`a7`) and (`b1`,`b2`,...,`b7`).
`public template<>`  <br/>`inline void `[`swap`](#namespacecimg__library__suffixed_1_1cimg_1a2f261b2759f7ba63c4bc84267d5a20c8)`(T1 & a1,T1 & b1,T2 & a2,T2 & b2,T3 & a3,T3 & b3,T4 & a4,T4 & b4,T5 & a5,T5 & b5,T6 & a6,T6 & b6,T7 & a7,T7 & b7,T8 & a8,T8 & b8)`            | Exchange values of variables (`a1`,`a2`,...,`a8`) and (`b1`,`b2`,...,`b8`).
`public inline bool `[`endianness`](#namespacecimg__library__suffixed_1_1cimg_1afd898f29e094a625d15928ed19a6b69d)`()`            | Return the endianness of the current architecture.
`public template<>`  <br/>`inline void `[`invert_endianness`](#namespacecimg__library__suffixed_1_1cimg_1a1f8e231e39844ce1685d2fa80edd852d)`(T *const buffer,const cimg_ulong size)`            | Reverse endianness of all elements in a memory buffer.
`public template<>`  <br/>`inline T & `[`invert_endianness`](#namespacecimg__library__suffixed_1_1cimg_1aaa2e6e8ccab85cc7fc7b9f02060965a2)`(T & a)`            | Reverse endianness of a single variable.
`public inline unsigned int `[`float2uint`](#namespacecimg__library__suffixed_1_1cimg_1abeb336981cf553b3244c800b781e313d)`(const float f)`            | 
`public inline float `[`uint2float`](#namespacecimg__library__suffixed_1_1cimg_1a6293f332d662f83e39a5a388b5abd222)`(const unsigned int u)`            | 
`public inline cimg_uint64 `[`time`](#namespacecimg__library__suffixed_1_1cimg_1a67e7c7cbeb79de5fc2f6a21afb06d413)`()`            | Return the value of a system timer, with a millisecond precision.
`public inline cimg_uint64 `[`tictoc`](#namespacecimg__library__suffixed_1_1cimg_1a6f96cd4f49d44a2224d3e87b0efdf633)`(const bool is_tic)`            | 
`public inline cimg_uint64 `[`tic`](#namespacecimg__library__suffixed_1_1cimg_1a0455de0827cac0a81e421ef873a95acc)`()`            | Start tic/toc timer for time measurement between code instructions.
`public inline cimg_uint64 `[`toc`](#namespacecimg__library__suffixed_1_1cimg_1a97115cec272070446ec968fb2c59c2fe)`()`            | End tic/toc timer and displays elapsed time from last call to [tic()](#namespacecimg__library__suffixed_1_1cimg_1a0455de0827cac0a81e421ef873a95acc).
`public inline void `[`sleep`](#namespacecimg__library__suffixed_1_1cimg_1aa2bf8fb0d97c122cbc52e1f2e167e8a6)`(const unsigned int milliseconds)`            | Sleep for a given numbers of milliseconds.
`public inline unsigned int `[`wait`](#namespacecimg__library__suffixed_1_1cimg_1a5f13deafde0dfee1c1350674f2ddb1df)`(const unsigned int milliseconds,cimg_uint64 *const p_timer)`            | 
`public inline unsigned int `[`wait`](#namespacecimg__library__suffixed_1_1cimg_1a88541ea6dcaca1badfeee4367abbd687)`(const unsigned int milliseconds)`            | Wait for a given number of milliseconds since the last call to wait().
`public inline cimg_uint64 & `[`rng`](#namespacecimg__library__suffixed_1_1cimg_1a236af06ba834ec94eb49bda7a60a854f)`()`            | 
`public inline unsigned int `[`_rand`](#namespacecimg__library__suffixed_1_1cimg_1a89b0e50db97e9a872e1bed2cb02fc3c0)`(cimg_uint64 *const p_rng)`            | 
`public inline unsigned int `[`_rand`](#namespacecimg__library__suffixed_1_1cimg_1ac83dc4391189607ffb3b175f3d627485)`()`            | 
`public inline void `[`srand`](#namespacecimg__library__suffixed_1_1cimg_1a015732105aafd2d82000eb8ab20fb826)`(cimg_uint64 *const p_rng)`            | 
`public inline void `[`srand`](#namespacecimg__library__suffixed_1_1cimg_1a96eab94d07b195c5773617bad4f10936)`()`            | 
`public inline void `[`srand`](#namespacecimg__library__suffixed_1_1cimg_1af0edbf83957282cd6a5da53a5e60e028)`(const cimg_uint64 seed)`            | 
`public inline double `[`rand`](#namespacecimg__library__suffixed_1_1cimg_1a9ec6c3ef7942ced482047db3e351c9eb)`(const double val_min,const double val_max,cimg_uint64 *const p_rng)`            | 
`public inline double `[`rand`](#namespacecimg__library__suffixed_1_1cimg_1ab7c09300be61c8a3361c379069100252)`(const double val_min,const double val_max)`            | 
`public inline double `[`rand`](#namespacecimg__library__suffixed_1_1cimg_1a0bfdfa57a9210107cfd0bce50083202d)`(const double val_max,cimg_uint64 *const p_rng)`            | 
`public inline double `[`rand`](#namespacecimg__library__suffixed_1_1cimg_1af5cd3397f819c13ccb17e05a7db736b1)`(const double val_max)`            | 
`public inline double `[`grand`](#namespacecimg__library__suffixed_1_1cimg_1acc4e8695bc96e4629c633368db7ed8b7)`(cimg_uint64 *const p_rng)`            | 
`public inline double `[`grand`](#namespacecimg__library__suffixed_1_1cimg_1aa12c572ad67f655e27f7b8e3e76dafa5)`()`            | 
`public inline unsigned int `[`prand`](#namespacecimg__library__suffixed_1_1cimg_1a6bd76bd6c22a253a7c76927fba792333)`(const double z,cimg_uint64 *const p_rng)`            | 
`public inline unsigned int `[`prand`](#namespacecimg__library__suffixed_1_1cimg_1a2a18bbfb6a496d8d5a02943be8eaa936)`(const double z)`            | 
`public template<>`  <br/>`inline T `[`cut`](#namespacecimg__library__suffixed_1_1cimg_1a60c895ccdb84e7ccdd884ff61bab29f0)`(const T & val,const t & val_min,const t & val_max)`            | Cut (i.e. clamp) value in specified interval.
`public template<>`  <br/>`inline T `[`rol`](#namespacecimg__library__suffixed_1_1cimg_1a1ead565c35064488c8a56fce858da674)`(const T & a,const unsigned int n)`            | Bitwise-rotate value on the left.
`public inline float `[`rol`](#namespacecimg__library__suffixed_1_1cimg_1afb7d512cc0b5473301a060131bd415af)`(const float a,const unsigned int n)`            | 
`public inline double `[`rol`](#namespacecimg__library__suffixed_1_1cimg_1a4263e5084b1303cc58b50650366bab36)`(const double a,const unsigned int n)`            | 
`public inline double `[`rol`](#namespacecimg__library__suffixed_1_1cimg_1aeee82dc035ff6c75d8b05530771090d3)`(const long double a,const unsigned int n)`            | 
`public template<>`  <br/>`inline T `[`ror`](#namespacecimg__library__suffixed_1_1cimg_1ab616eb52e66e664293d16a9bcfa9a9b4)`(const T & a,const unsigned int n)`            | Bitwise-rotate value on the right.
`public inline float `[`ror`](#namespacecimg__library__suffixed_1_1cimg_1a0cc69aa64bca2114676aebf2f689e5e8)`(const float a,const unsigned int n)`            | 
`public inline double `[`ror`](#namespacecimg__library__suffixed_1_1cimg_1a4ac3e4e4369af3c0f7a40fb4ef435e82)`(const double a,const unsigned int n)`            | 
`public inline double `[`ror`](#namespacecimg__library__suffixed_1_1cimg_1a28a92e1f3aec1b1ff7a6c4277473144d)`(const long double a,const unsigned int n)`            | 
`public template<>`  <br/>`inline T `[`abs`](#namespacecimg__library__suffixed_1_1cimg_1a0852e9ad458e82d2c003844cd92bdb8a)`(const T & a)`            | Return absolute value of a value.
`public inline bool `[`abs`](#namespacecimg__library__suffixed_1_1cimg_1a58594a6c544821be41beb663f65ae6f7)`(const bool a)`            | 
`public inline int `[`abs`](#namespacecimg__library__suffixed_1_1cimg_1a98875c08cd797ad18f78b3010d998f43)`(const unsigned char a)`            | 
`public inline int `[`abs`](#namespacecimg__library__suffixed_1_1cimg_1ac065ecac4db3e755a220ba19e423ebb4)`(const unsigned short a)`            | 
`public inline int `[`abs`](#namespacecimg__library__suffixed_1_1cimg_1a442fd2c14c431028a04c10618aa03261)`(const unsigned int a)`            | 
`public inline int `[`abs`](#namespacecimg__library__suffixed_1_1cimg_1a26acb5583d30cb7eeea839ef82a73270)`(const int a)`            | 
`public inline cimg_int64 `[`abs`](#namespacecimg__library__suffixed_1_1cimg_1a806bd69aeff5adab7bb5081132f5c68b)`(const cimg_uint64 a)`            | 
`public inline double `[`abs`](#namespacecimg__library__suffixed_1_1cimg_1a257cae0845617a5813b23d8668ab01a6)`(const double a)`            | 
`public inline float `[`abs`](#namespacecimg__library__suffixed_1_1cimg_1a37ec01e1d8db19fdd1a0c4bfa73e3879)`(const float a)`            | 
`public inline double `[`acosh`](#namespacecimg__library__suffixed_1_1cimg_1a7a4d9fec1f28d1788e47e739fd7089c6)`(const double x)`            | Return hyperbolic arcosine of a value.
`public inline double `[`asinh`](#namespacecimg__library__suffixed_1_1cimg_1a3bbc85a1a73b23640d6a5a2846cc79d9)`(const double x)`            | Return hyperbolic arcsine of a value.
`public inline double `[`atanh`](#namespacecimg__library__suffixed_1_1cimg_1abbd663a9475a67825564aeb3b34687ed)`(const double x)`            | Return hyperbolic arctangent of a value.
`public inline double `[`sinc`](#namespacecimg__library__suffixed_1_1cimg_1ae3375412d53d28356063384da9fd9ad2)`(const double x)`            | Return the sinc of a given value.
`public inline double `[`log2`](#namespacecimg__library__suffixed_1_1cimg_1a03657cf098d3b588e76bcef4426233bd)`(const double x)`            | Return base-2 logarithm of a value.
`public template<>`  <br/>`inline T `[`sqr`](#namespacecimg__library__suffixed_1_1cimg_1ac6d817f750ba83dd8f8b1b64aaaf8b19)`(const T & val)`            | Return square of a value.
`public template<>`  <br/>`inline double `[`cbrt`](#namespacecimg__library__suffixed_1_1cimg_1ad72601dd5481dc3abd338d9ed1604622)`(const T & x)`            | Return cubic root of a value.
`public template<>`  <br/>`inline T `[`pow3`](#namespacecimg__library__suffixed_1_1cimg_1a51beb9e6a54e050ed4e4783d8f1374eb)`(const T & val)`            | 
`public template<>`  <br/>`inline T `[`pow4`](#namespacecimg__library__suffixed_1_1cimg_1a9521f5be7c0f270bfe409214e4c2ebee)`(const T & val)`            | 
`public template<>`  <br/>`inline t `[`min`](#namespacecimg__library__suffixed_1_1cimg_1a091c508a646a5459c00aa2b5ac9ea5e5)`(const t & a,const t & b,const t & c)`            | Return the minimum between three values.
`public template<>`  <br/>`inline t `[`min`](#namespacecimg__library__suffixed_1_1cimg_1ad5459593e7f8a4066cb22ad63de8e92d)`(const t & a,const t & b,const t & c,const t & d)`            | Return the minimum between four values.
`public template<>`  <br/>`inline t `[`minabs`](#namespacecimg__library__suffixed_1_1cimg_1a81ff5885c4c8a51e149d527e85762559)`(const t & a,const t & b)`            | Return the minabs between two values.
`public template<>`  <br/>`inline t `[`minabs`](#namespacecimg__library__suffixed_1_1cimg_1a1f5925ace392b6747002f18ae57c0a39)`(const t & a,const t & b,const t & abs_b)`            | 
`public template<>`  <br/>`inline t `[`max`](#namespacecimg__library__suffixed_1_1cimg_1aae5df5731fe5a367cec402071108c11c)`(const t & a,const t & b,const t & c)`            | Return the maximum between three values.
`public template<>`  <br/>`inline t `[`max`](#namespacecimg__library__suffixed_1_1cimg_1a4b4cabc621d732787bca13016ea8026a)`(const t & a,const t & b,const t & c,const t & d)`            | Return the maximum between four values.
`public template<>`  <br/>`inline t `[`maxabs`](#namespacecimg__library__suffixed_1_1cimg_1aeccf40e5b836c4b56e0dd2d240fb548a)`(const t & a,const t & b)`            | Return the maxabs between two values.
`public template<>`  <br/>`inline t `[`maxabs`](#namespacecimg__library__suffixed_1_1cimg_1af6639a9cff62792d394ccf38294741df)`(const t & a,const t & b,const t & abs_b)`            | 
`public template<>`  <br/>`inline T `[`sign`](#namespacecimg__library__suffixed_1_1cimg_1abecddd9720e89882ff3d10dd35f940d9)`(const T & x)`            | Return the sign of a value.
`public template<>`  <br/>`inline cimg_uint64 `[`nearest_pow2`](#namespacecimg__library__suffixed_1_1cimg_1a3a01572a1d9c448556b2ffa87fde879b)`(const T & x)`            | Return the nearest power of 2 higher than given value.
`public template<>`  <br/>`inline T `[`mod`](#namespacecimg__library__suffixed_1_1cimg_1afcc02428c9b7d9100e1674369d25cc40)`(const T & x,const T & m)`            | Return the modulo of a value.
`public inline int `[`mod`](#namespacecimg__library__suffixed_1_1cimg_1ace8c511f2eaca41092ec4f62aa9661ab)`(const bool x,const bool m)`            | 
`public inline int `[`mod`](#namespacecimg__library__suffixed_1_1cimg_1acaf502340ec0683b4ddabf5a792426c9)`(const unsigned char x,const unsigned char m)`            | 
`public inline int `[`mod`](#namespacecimg__library__suffixed_1_1cimg_1aec9a354db76b695a13fd4d817286bd8d)`(const char x,const char m)`            | 
`public inline int `[`mod`](#namespacecimg__library__suffixed_1_1cimg_1aba178f4f778631ba25c4d715a8bce274)`(const unsigned short x,const unsigned short m)`            | 
`public inline int `[`mod`](#namespacecimg__library__suffixed_1_1cimg_1a5bac7fb02f8b0b7f0436b2f58ae2e5e6)`(const short x,const short m)`            | 
`public inline int `[`mod`](#namespacecimg__library__suffixed_1_1cimg_1af5377d20e562b9a0eced0d2066b3c8ba)`(const unsigned int x,const unsigned int m)`            | 
`public inline int `[`mod`](#namespacecimg__library__suffixed_1_1cimg_1ab87d2b561c521c920cd9f2143d222435)`(const int x,const int m)`            | 
`public inline cimg_int64 `[`mod`](#namespacecimg__library__suffixed_1_1cimg_1a2dbd8f870f77ce3b10731130ce059498)`(const cimg_uint64 x,const cimg_uint64 m)`            | 
`public inline cimg_int64 `[`mod`](#namespacecimg__library__suffixed_1_1cimg_1ad3daae7244a90ad300eea619397db898)`(const cimg_int64 x,const cimg_int64 m)`            | 
`public template<>`  <br/>`inline T `[`minmod`](#namespacecimg__library__suffixed_1_1cimg_1ac9630aa9259053d209c7ff02823efda0)`(const T & a,const T & b)`            | Return the min-mod of two values.
`public template<>`  <br/>`inline T `[`round`](#namespacecimg__library__suffixed_1_1cimg_1a7bed9b422eb303150d7abb503e7201fc)`(const T & x)`            | 
`public template<>`  <br/>`inline int `[`uiround`](#namespacecimg__library__suffixed_1_1cimg_1a5bd7100202f965808ce5a7e28b121ec8)`(const T x)`            | 
`public template<>`  <br/>`inline T `[`round`](#namespacecimg__library__suffixed_1_1cimg_1a66a32585b286a3c7f76d745107ae5300)`(const T & x,const double y,const int rounding_type)`            | Return rounded value.
`public template<>`  <br/>`inline T `[`median`](#namespacecimg__library__suffixed_1_1cimg_1acf4703b2dd4307ecbdf61e7fc5d93800)`(T val0,T val1)`            | 
`public template<>`  <br/>`inline T `[`median`](#namespacecimg__library__suffixed_1_1cimg_1ac941c3a7e6b58e225a63d0f8ee7a28b2)`(T val0,T val1,T val2)`            | 
`public template<>`  <br/>`inline T `[`median`](#namespacecimg__library__suffixed_1_1cimg_1abe9263120cac5615f302f88d2674aab6)`(T val0,T val1,T val2,T val3,T val4)`            | 
`public template<>`  <br/>`inline T `[`median`](#namespacecimg__library__suffixed_1_1cimg_1ac800cb8692cd896502ea26f201e5dc2f)`(T val0,T val1,T val2,T val3,T val4,T val5,T val6)`            | 
`public template<>`  <br/>`inline T `[`median`](#namespacecimg__library__suffixed_1_1cimg_1a76eb106e5afc159f8ec892ddb206de1c)`(T val0,T val1,T val2,T val3,T val4,T val5,T val6,T val7,T val8)`            | 
`public template<>`  <br/>`inline T `[`median`](#namespacecimg__library__suffixed_1_1cimg_1ab87bc357192941440852178fc4820463)`(T val0,T val1,T val2,T val3,T val4,T val5,T val6,T val7,T val8,T val9,T val10,T val11,T val12)`            | 
`public template<>`  <br/>`inline T `[`median`](#namespacecimg__library__suffixed_1_1cimg_1aa147071742c37d4ed5698c612b2ff2f6)`(T val0,T val1,T val2,T val3,T val4,T val5,T val6,T val7,T val8,T val9,T val10,T val11,T val12,T val13,T val14,T val15,T val16,T val17,T val18,T val19,T val20,T val21,T val22,T val23,T val24)`            | 
`public template<>`  <br/>`inline T `[`median`](#namespacecimg__library__suffixed_1_1cimg_1ab28b23392cce9895840d93df30fb2db6)`(T val0,T val1,T val2,T val3,T val4,T val5,T val6,T val7,T val8,T val9,T val10,T val11,T val12,T val13,T val14,T val15,T val16,T val17,T val18,T val19,T val20,T val21,T val22,T val23,T val24,T val25,T val26,T val27,T val28,T val29,T val30,T val31,T val32,T val33,T val34,T val35,T val36,T val37,T val38,T val39,T val40,T val41,T val42,T val43,T val44,T val45,T val46,T val47,T val48)`            | 
`public template<>`  <br/>`inline T `[`hypot`](#namespacecimg__library__suffixed_1_1cimg_1af556f826a8b7acb2fbbaa5259e6d95e8)`(const T x,const T y)`            | Return sqrt(x^2 + y^2).
`public template<>`  <br/>`inline T `[`hypot`](#namespacecimg__library__suffixed_1_1cimg_1abc2af0eccc1059711364e339d73c36cd)`(const T x,const T y,const T z)`            | 
`public template<>`  <br/>`inline T `[`_hypot`](#namespacecimg__library__suffixed_1_1cimg_1a9e49b17ee53d34a8df49b655eb915572)`(const T x,const T y)`            | 
`public inline double `[`factorial`](#namespacecimg__library__suffixed_1_1cimg_1a5c4845e4f0f1c87ec1cd97d7a8923cb6)`(const int n)`            | Return the factorial of n.
`public inline double `[`permutations`](#namespacecimg__library__suffixed_1_1cimg_1a4e6348dd82ed46fecc9f46981dc5bc0a)`(const int k,const int n,const bool with_order)`            | Return the number of permutations of k objects in a set of n objects.
`public inline double `[`_fibonacci`](#namespacecimg__library__suffixed_1_1cimg_1af54e8ac35c9b3c07062005881b2c4e08)`(int exp)`            | 
`public inline double `[`fibonacci`](#namespacecimg__library__suffixed_1_1cimg_1aa9c0e571bc9644b4d838630f9a79534f)`(const int n)`            | Calculate fibonacci number.
`public inline long `[`gcd`](#namespacecimg__library__suffixed_1_1cimg_1accbccc3f867ba4a2f5a3713761e7b1b2)`(long a,long b)`            | Calculate greatest common divisor.
`public inline char `[`lowercase`](#namespacecimg__library__suffixed_1_1cimg_1ac9cf8d2a803d13d85e7fcc48fee55587)`(const char x)`            | Convert character to lower case.
`public inline double `[`lowercase`](#namespacecimg__library__suffixed_1_1cimg_1a8154b2b3cf547bfa32e33547efada626)`(const double x)`            | 
`public inline void `[`lowercase`](#namespacecimg__library__suffixed_1_1cimg_1a633cb3df73dfa78f43ffa2679bd1ebb8)`(char *const str)`            | Convert C-string to lower case.
`public inline char `[`uppercase`](#namespacecimg__library__suffixed_1_1cimg_1afbbd48435496962b08134b7b0101a07f)`(const char x)`            | Convert character to upper case.
`public inline double `[`uppercase`](#namespacecimg__library__suffixed_1_1cimg_1a61266ea59c6fb0b76bba21326718ab41)`(const double x)`            | 
`public inline void `[`uppercase`](#namespacecimg__library__suffixed_1_1cimg_1ac13217912b5cdf549f5744910521881a)`(char *const str)`            | Convert C-string to upper case.
`public inline bool `[`is_blank`](#namespacecimg__library__suffixed_1_1cimg_1a5dc2552c04442ed9c8643598bf1f4208)`(const char c)`            | Return `true` if input character is blank (space, tab, or non-printable character).
`public inline double `[`atof`](#namespacecimg__library__suffixed_1_1cimg_1a00aba235049bc02e53453cbb829469ce)`(const char *const str)`            | Read value in a C-string.
`public inline int `[`strncasecmp`](#namespacecimg__library__suffixed_1_1cimg_1a1304046a29511fe0a015173e46607229)`(const char *const str1,const char *const str2,const int l)`            | Compare the first `l` characters of two C-strings, ignoring the case.
`public inline int `[`strcasecmp`](#namespacecimg__library__suffixed_1_1cimg_1a1c34609cc6fef6f5fe5ffb2f69ad7989)`(const char *const str1,const char *const str2)`            | Compare two C-strings, ignoring the case.
`public inline char * `[`strellipsize`](#namespacecimg__library__suffixed_1_1cimg_1a69a3a1bbdf0f62474211ea5a398f9e72)`(char *const str,const unsigned int l,const bool is_ending)`            | Ellipsize a string.
`public inline char * `[`strellipsize`](#namespacecimg__library__suffixed_1_1cimg_1a79b0ac227dd09ae4cdb84658d2fd919b)`(const char *const str,char *const res,const unsigned int l,const bool is_ending)`            | Ellipsize a string.
`public inline bool `[`strpare`](#namespacecimg__library__suffixed_1_1cimg_1a85cb703b948df7a021fd41ca3bad6696)`(char *const str,const char delimiter,const bool is_symmetric,const bool is_iterative)`            | Remove delimiters on the start and/or end of a C-string.
`public inline bool `[`strpare`](#namespacecimg__library__suffixed_1_1cimg_1ac9e23320a870b0ebce24c7a6059c7467)`(char *const str,const bool is_symmetric,const bool is_iterative)`            | Remove white spaces on the start and/or end of a C-string.
`public inline void `[`strwindows_reserved`](#namespacecimg__library__suffixed_1_1cimg_1a3dff5896c142fb4f9dbd2d49facd33c0)`(char *const str,const char c)`            | Replace reserved characters (for Windows filename) by another character.
`public inline void `[`strunescape`](#namespacecimg__library__suffixed_1_1cimg_1a1ffad008d2b45ffa0ff4d0f32b6c98ec)`(char *const str)`            | Replace escape sequences in C-strings by character values.
`public inline const char * `[`strbuffersize`](#namespacecimg__library__suffixed_1_1cimg_1a73a84376fb4f9577c5786ad58289efad)`(const cimg_ulong size)`            | 
`public inline const char * `[`stros`](#namespacecimg__library__suffixed_1_1cimg_1ac2fe91fca3a53a6a86d6e4ba808c2061)`()`            | 
`public inline const char * `[`basename`](#namespacecimg__library__suffixed_1_1cimg_1a40fb5fe2a0d260120909c617dfd3b07b)`(const char *const s,const char separator)`            | Return the basename of a filename.
`public inline const char * `[`filenamerand`](#namespacecimg__library__suffixed_1_1cimg_1ae92216bbc140ed7afef601f72ba2bd81)`()`            | 
`public inline void `[`winformat_string`](#namespacecimg__library__suffixed_1_1cimg_1a1b401761f9f3c1d01de8ec6ef6bec731)`(char *const str)`            | 
`public inline std::FILE * `[`std_fopen`](#namespacecimg__library__suffixed_1_1cimg_1aa21dee2dbac63e1cfcd7613c159edff3)`(const char *const path,const char *const mode)`            | 
`public inline std::FILE * `[`fopen`](#namespacecimg__library__suffixed_1_1cimg_1a9aafdb8732ff87625052ce2723f8a516)`(const char *const path,const char *const mode)`            | Open a file.
`public inline int `[`fclose`](#namespacecimg__library__suffixed_1_1cimg_1ac436b94e6ffef5fd420bb3d7c05fd416)`(std::FILE * file)`            | Close a file.
`public inline int `[`fseek`](#namespacecimg__library__suffixed_1_1cimg_1a03dbe74029b194eca4b86c10e9fbd1fc)`(FILE * stream,cimg_long offset,int origin)`            | Version of '[fseek()](#namespacecimg__library__suffixed_1_1cimg_1a03dbe74029b194eca4b86c10e9fbd1fc)' that supports >=64bits offsets everywhere (for Windows).
`public inline cimg_long `[`ftell`](#namespacecimg__library__suffixed_1_1cimg_1a6fe7b32c5cfeef7ec973b4cbb538683a)`(FILE * stream)`            | Version of '[ftell()](#namespacecimg__library__suffixed_1_1cimg_1a6fe7b32c5cfeef7ec973b4cbb538683a)' that supports >=64bits offsets everywhere (for Windows).
`public inline bool `[`is_directory`](#namespacecimg__library__suffixed_1_1cimg_1aca0e45a04eb1607f2e25101aae4b8572)`(const char *const path)`            | Check if a path is a directory.
`public inline bool `[`is_file`](#namespacecimg__library__suffixed_1_1cimg_1ad6c9ae2aaaf60bdecbd5c8f57ee5617e)`(const char *const path)`            | Check if a path is a file.
`public inline cimg_int64 `[`fsize`](#namespacecimg__library__suffixed_1_1cimg_1a63af61d735eb705dfeae46df8bf03184)`(const char *const filename)`            | Get file size.
`public template<>`  <br/>`inline int `[`fdate`](#namespacecimg__library__suffixed_1_1cimg_1a0654bf4ceae1444ae9fa1113cbb064ee)`(const char *const path,T * attr,const unsigned int nb_attr)`            | Get last write time of a given file or directory (multiple-attributes version).
`public inline int `[`fdate`](#namespacecimg__library__suffixed_1_1cimg_1a1db87aed0dbd0fd7a0e709894e9f645d)`(const char *const path,unsigned int attr)`            | Get last write time of a given file or directory (single-attribute version).
`public template<>`  <br/>`inline int `[`date`](#namespacecimg__library__suffixed_1_1cimg_1a6b6e28a991c9e426d8cb1c6d1e02849e)`(T * attr,const unsigned int nb_attr)`            | Get current local time (multiple-attributes version).
`public inline int `[`date`](#namespacecimg__library__suffixed_1_1cimg_1aac739bf544269324a04504ebe92b93e9)`(unsigned int attr)`            | Get current local time (single-attribute version).
`public inline const char * `[`temporary_path`](#namespacecimg__library__suffixed_1_1cimg_1ae9af8e17db04e875db3b45cbe58892d6)`(const char *const user_path,const bool reinit_path)`            | Get the file or directory attributes with support for UTF-8 paths (Windows only).
`public inline const char * `[`imagemagick_path`](#namespacecimg__library__suffixed_1_1cimg_1a96cabeea0a54a10aeee97ead7b672f0f)`(const char *const user_path,const bool reinit_path)`            | Get/set path to the *Program Files/* directory (Windows only).
`public inline const char * `[`graphicsmagick_path`](#namespacecimg__library__suffixed_1_1cimg_1ab4063d8fb2c2564596f33f4a75436f76)`(const char *const user_path,const bool reinit_path)`            | Get/set path to the GraphicsMagick's `gm` binary.
`public inline const char * `[`medcon_path`](#namespacecimg__library__suffixed_1_1cimg_1a65c2f6f9671ac4f3eae2b5624313926e)`(const char *const user_path,const bool reinit_path)`            | Get/set path to the XMedcon's `medcon` binary.
`public inline const char * `[`ffmpeg_path`](#namespacecimg__library__suffixed_1_1cimg_1a5b8fba26176c5506b1eb27e70ca44889)`(const char *const user_path,const bool reinit_path)`            | Get/set path to the FFMPEG's `ffmpeg` binary.
`public inline const char * `[`gzip_path`](#namespacecimg__library__suffixed_1_1cimg_1aac00308d827ccbd69bd26c9ba6e1356b)`(const char *const user_path,const bool reinit_path)`            | Get/set path to the `gzip` binary.
`public inline const char * `[`gunzip_path`](#namespacecimg__library__suffixed_1_1cimg_1a7b4390d7bec2ffbf27d108f1c3a699e0)`(const char *const user_path,const bool reinit_path)`            | Get/set path to the `gunzip` binary.
`public inline const char * `[`dcraw_path`](#namespacecimg__library__suffixed_1_1cimg_1ad2459563e2ed326f303b9ac4e91744b0)`(const char *const user_path,const bool reinit_path)`            | Get/set path to the `dcraw` binary.
`public inline const char * `[`wget_path`](#namespacecimg__library__suffixed_1_1cimg_1a36ccf2e6a6542f4e93eac819cf5d91ba)`(const char *const user_path,const bool reinit_path)`            | Get/set path to the `wget` binary.
`public inline const char * `[`curl_path`](#namespacecimg__library__suffixed_1_1cimg_1aebd4f990c3e148573c96c04dbfdcc5c6)`(const char *const user_path,const bool reinit_path)`            | Get/set path to the `curl` binary.
`public inline const char * `[`split_filename`](#namespacecimg__library__suffixed_1_1cimg_1a61e1cd854cf93fdf3f6d06525e1590c5)`(const char *const filename,char *const body)`            | Split filename into two C-strings `body` and `extension`.
`public inline char * `[`number_filename`](#namespacecimg__library__suffixed_1_1cimg_1ae9bdf968dd4f20fdc7542e3b3089c495)`(const char *const filename,const int number,const unsigned int digits,char *const str)`            | Generate a numbered version of a filename.
`public template<>`  <br/>`inline size_t `[`fread`](#namespacecimg__library__suffixed_1_1cimg_1a6b210044fcdb52b1d649ab19006de4ad)`(T *const ptr,const size_t nmemb,std::FILE * stream)`            | Read data from file.
`public template<>`  <br/>`inline size_t `[`fwrite`](#namespacecimg__library__suffixed_1_1cimg_1ad44a7e96cd1e9cdef83f4ffe235dd1fb)`(const T * ptr,const size_t nmemb,std::FILE * stream)`            | Write data to file.
`public inline void `[`fempty`](#namespacecimg__library__suffixed_1_1cimg_1a0f3577978081461118330fc3ecd4b9db)`(std::FILE *const file,const char *const filename)`            | Create an empty file.
`public inline const char * `[`ftype`](#namespacecimg__library__suffixed_1_1cimg_1a56c2dbfe99d9f6e6bc1be9d03b0ddaaa)`(std::FILE *const file,const char *const filename)`            | Try to guess format from an image file.
`public inline bool & `[`network_mode`](#namespacecimg__library__suffixed_1_1cimg_1a470c76a43e2ae6f77c48acf1071fcc67)`(const bool value,const bool is_set)`            | 
`public inline bool & `[`network_mode`](#namespacecimg__library__suffixed_1_1cimg_1a02013cf524a1901b3001ee1038dcea49)`()`            | 
`public inline char * `[`load_network`](#namespacecimg__library__suffixed_1_1cimg_1a90c05fe6fc049cba75f3a12807e97158)`(const char *const url,char *const filename_local,const unsigned int timeout,const bool try_fallback,const char *const referer)`            | Load file from network as a local temporary file.
`public inline const char * `[`option`](#namespacecimg__library__suffixed_1_1cimg_1a2af5d4755bf8a0e4e9e8cf833eb46f31)`(const char *const name,const int argc,const char *const *const argv,const char *const _default,const char *const usage,const bool reset_static)`            | Return options specified on the command line.
`public inline const char * `[`option`](#namespacecimg__library__suffixed_1_1cimg_1afa0edc26d6968a0b6fde84452e51f01f)`(const char *const name,const int argc,const char *const *const argv,const char *const _default,const char *const usage)`            | 
`public inline bool `[`option`](#namespacecimg__library__suffixed_1_1cimg_1ae0751f1e30f631c99f04d351859ee78f)`(const char *const name,const int argc,const char *const *const argv,const bool _default,const char *const usage)`            | 
`public inline int `[`option`](#namespacecimg__library__suffixed_1_1cimg_1aaff0def8ccf096f02c1fb2267af9bf69)`(const char *const name,const int argc,const char *const *const argv,const int _default,const char *const usage)`            | 
`public inline char `[`option`](#namespacecimg__library__suffixed_1_1cimg_1ac2ddab9ad61673b342d32cdd724ac376)`(const char *const name,const int argc,const char *const *const argv,const char _default,const char *const usage)`            | 
`public inline float `[`option`](#namespacecimg__library__suffixed_1_1cimg_1a2d98984b306115047ef266b03164cf23)`(const char *const name,const int argc,const char *const *const argv,const float _default,const char *const usage)`            | 
`public inline double `[`option`](#namespacecimg__library__suffixed_1_1cimg_1a5325ef9b0a96182b545bbdcf31d02798)`(const char *const name,const int argc,const char *const *const argv,const double _default,const char *const usage)`            | 
`public inline int `[`_sort_files`](#namespacecimg__library__suffixed_1_1cimg_1add25d3bf42363c07ad95d4a9a689f729)`(const void * a,const void * b)`            | 
`public inline `[`CImgList`](#structcimg__library__suffixed_1_1CImgList)`< char > `[`files`](#namespacecimg__library__suffixed_1_1cimg_1a9f8980f1308177adebab5f8f52a79835)`(const char *const path,const bool is_pattern,const unsigned int mode,const bool include_path)`            | Return list of files/directories in specified directory.
`public template<>`  <br/>`inline int `[`dialog`](#namespacecimg__library__suffixed_1_1cimg_1a11aed0e6b30d75bf50946ee78d1aed94)`(const char *const title,const char *const msg,const char *const button1_label,const char *const button2_label,const char *const button3_label,const char *const button4_label,const char *const button5_label,const char *const button6_label,const `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< t > & logo,const bool is_centered)`            | Display a simple dialog box, and wait for the user's response.
`public template<>`  <br/>`inline `[`CImg](#structcimg__library__suffixed_1_1CImg)< typename [cimg::superset](#structcimg__library__suffixed_1_1cimg_1_1superset)< double, t >::[type`](#structcimg__library__suffixed_1_1cimg_1_1type)` > `[`eval`](#namespacecimg__library__suffixed_1_1cimg_1ad0fbf2581340a8533f5c3e3d86e2ce60)`(const char *const expression,const `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< t > & xyzc)`            | 
`struct `[`cimg_library_suffixed::cimg::last`](#structcimg__library__suffixed_1_1cimg_1_1last) | 
`struct `[`cimg_library_suffixed::cimg::Mutex_static`](#structcimg__library__suffixed_1_1cimg_1_1Mutex__static) | 
`struct `[`cimg_library_suffixed::cimg::superset`](#structcimg__library__suffixed_1_1cimg_1_1superset) | 
`struct `[`cimg_library_suffixed::cimg::superset2`](#structcimg__library__suffixed_1_1cimg_1_1superset2) | 
`struct `[`cimg_library_suffixed::cimg::superset3`](#structcimg__library__suffixed_1_1cimg_1_1superset3) | 
`struct `[`cimg_library_suffixed::cimg::superset< bool, char >`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01bool_00_01char_01_4) | 
`struct `[`cimg_library_suffixed::cimg::superset< bool, cimg_int64 >`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01bool_00_01cimg__int64_01_4) | 
`struct `[`cimg_library_suffixed::cimg::superset< bool, cimg_uint64 >`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01bool_00_01cimg__uint64_01_4) | 
`struct `[`cimg_library_suffixed::cimg::superset< bool, double >`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01bool_00_01double_01_4) | 
`struct `[`cimg_library_suffixed::cimg::superset< bool, float >`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01bool_00_01float_01_4) | 
`struct `[`cimg_library_suffixed::cimg::superset< bool, int >`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01bool_00_01int_01_4) | 
`struct `[`cimg_library_suffixed::cimg::superset< bool, short >`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01bool_00_01short_01_4) | 
`struct `[`cimg_library_suffixed::cimg::superset< bool, signed char >`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01bool_00_01signed_01char_01_4) | 
`struct `[`cimg_library_suffixed::cimg::superset< bool, unsigned char >`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01bool_00_01unsigned_01char_01_4) | 
`struct `[`cimg_library_suffixed::cimg::superset< bool, unsigned int >`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01bool_00_01unsigned_01int_01_4) | 
`struct `[`cimg_library_suffixed::cimg::superset< bool, unsigned short >`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01bool_00_01unsigned_01short_01_4) | 
`struct `[`cimg_library_suffixed::cimg::superset< char, cimg_int64 >`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01char_00_01cimg__int64_01_4) | 
`struct `[`cimg_library_suffixed::cimg::superset< char, cimg_uint64 >`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01char_00_01cimg__uint64_01_4) | 
`struct `[`cimg_library_suffixed::cimg::superset< char, double >`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01char_00_01double_01_4) | 
`struct `[`cimg_library_suffixed::cimg::superset< char, float >`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01char_00_01float_01_4) | 
`struct `[`cimg_library_suffixed::cimg::superset< char, int >`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01char_00_01int_01_4) | 
`struct `[`cimg_library_suffixed::cimg::superset< char, short >`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01char_00_01short_01_4) | 
`struct `[`cimg_library_suffixed::cimg::superset< char, signed char >`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01char_00_01signed_01char_01_4) | 
`struct `[`cimg_library_suffixed::cimg::superset< char, unsigned char >`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01char_00_01unsigned_01char_01_4) | 
`struct `[`cimg_library_suffixed::cimg::superset< char, unsigned int >`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01char_00_01unsigned_01int_01_4) | 
`struct `[`cimg_library_suffixed::cimg::superset< char, unsigned short >`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01char_00_01unsigned_01short_01_4) | 
`struct `[`cimg_library_suffixed::cimg::superset< cimg_int64, double >`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01cimg__int64_00_01double_01_4) | 
`struct `[`cimg_library_suffixed::cimg::superset< cimg_int64, float >`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01cimg__int64_00_01float_01_4) | 
`struct `[`cimg_library_suffixed::cimg::superset< cimg_uint64, char >`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01cimg__uint64_00_01char_01_4) | 
`struct `[`cimg_library_suffixed::cimg::superset< cimg_uint64, cimg_int64 >`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01cimg__uint64_00_01cimg__int64_01_4) | 
`struct `[`cimg_library_suffixed::cimg::superset< cimg_uint64, double >`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01cimg__uint64_00_01double_01_4) | 
`struct `[`cimg_library_suffixed::cimg::superset< cimg_uint64, float >`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01cimg__uint64_00_01float_01_4) | 
`struct `[`cimg_library_suffixed::cimg::superset< cimg_uint64, int >`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01cimg__uint64_00_01int_01_4) | 
`struct `[`cimg_library_suffixed::cimg::superset< cimg_uint64, short >`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01cimg__uint64_00_01short_01_4) | 
`struct `[`cimg_library_suffixed::cimg::superset< cimg_uint64, signed char >`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01cimg__uint64_00_01signed_01char_01_4) | 
`struct `[`cimg_library_suffixed::cimg::superset< float, double >`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01float_00_01double_01_4) | 
`struct `[`cimg_library_suffixed::cimg::superset< int, cimg_int64 >`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01int_00_01cimg__int64_01_4) | 
`struct `[`cimg_library_suffixed::cimg::superset< int, cimg_uint64 >`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01int_00_01cimg__uint64_01_4) | 
`struct `[`cimg_library_suffixed::cimg::superset< int, double >`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01int_00_01double_01_4) | 
`struct `[`cimg_library_suffixed::cimg::superset< int, float >`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01int_00_01float_01_4) | 
`struct `[`cimg_library_suffixed::cimg::superset< int, unsigned int >`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01int_00_01unsigned_01int_01_4) | 
`struct `[`cimg_library_suffixed::cimg::superset< short, cimg_int64 >`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01short_00_01cimg__int64_01_4) | 
`struct `[`cimg_library_suffixed::cimg::superset< short, cimg_uint64 >`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01short_00_01cimg__uint64_01_4) | 
`struct `[`cimg_library_suffixed::cimg::superset< short, double >`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01short_00_01double_01_4) | 
`struct `[`cimg_library_suffixed::cimg::superset< short, float >`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01short_00_01float_01_4) | 
`struct `[`cimg_library_suffixed::cimg::superset< short, int >`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01short_00_01int_01_4) | 
`struct `[`cimg_library_suffixed::cimg::superset< short, unsigned int >`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01short_00_01unsigned_01int_01_4) | 
`struct `[`cimg_library_suffixed::cimg::superset< short, unsigned short >`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01short_00_01unsigned_01short_01_4) | 
`struct `[`cimg_library_suffixed::cimg::superset< signed char, char >`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01signed_01char_00_01char_01_4) | 
`struct `[`cimg_library_suffixed::cimg::superset< signed char, cimg_int64 >`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01signed_01char_00_01cimg__int64_01_4) | 
`struct `[`cimg_library_suffixed::cimg::superset< signed char, cimg_uint64 >`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01signed_01char_00_01cimg__uint64_01_4) | 
`struct `[`cimg_library_suffixed::cimg::superset< signed char, double >`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01signed_01char_00_01double_01_4) | 
`struct `[`cimg_library_suffixed::cimg::superset< signed char, float >`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01signed_01char_00_01float_01_4) | 
`struct `[`cimg_library_suffixed::cimg::superset< signed char, int >`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01signed_01char_00_01int_01_4) | 
`struct `[`cimg_library_suffixed::cimg::superset< signed char, short >`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01signed_01char_00_01short_01_4) | 
`struct `[`cimg_library_suffixed::cimg::superset< signed char, unsigned char >`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01signed_01char_00_01unsigned_01char_01_4) | 
`struct `[`cimg_library_suffixed::cimg::superset< signed char, unsigned int >`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01signed_01char_00_01unsigned_01int_01_4) | 
`struct `[`cimg_library_suffixed::cimg::superset< signed char, unsigned short >`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01signed_01char_00_01unsigned_01short_01_4) | 
`struct `[`cimg_library_suffixed::cimg::superset< unsigned char, char >`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01char_00_01char_01_4) | 
`struct `[`cimg_library_suffixed::cimg::superset< unsigned char, cimg_int64 >`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01char_00_01cimg__int64_01_4) | 
`struct `[`cimg_library_suffixed::cimg::superset< unsigned char, cimg_uint64 >`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01char_00_01cimg__uint64_01_4) | 
`struct `[`cimg_library_suffixed::cimg::superset< unsigned char, double >`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01char_00_01double_01_4) | 
`struct `[`cimg_library_suffixed::cimg::superset< unsigned char, float >`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01char_00_01float_01_4) | 
`struct `[`cimg_library_suffixed::cimg::superset< unsigned char, int >`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01char_00_01int_01_4) | 
`struct `[`cimg_library_suffixed::cimg::superset< unsigned char, short >`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01char_00_01short_01_4) | 
`struct `[`cimg_library_suffixed::cimg::superset< unsigned char, signed char >`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01char_00_01signed_01char_01_4) | 
`struct `[`cimg_library_suffixed::cimg::superset< unsigned char, unsigned int >`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01char_00_01unsigned_01int_01_4) | 
`struct `[`cimg_library_suffixed::cimg::superset< unsigned char, unsigned short >`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01char_00_01unsigned_01short_01_4) | 
`struct `[`cimg_library_suffixed::cimg::superset< unsigned int, char >`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01int_00_01char_01_4) | 
`struct `[`cimg_library_suffixed::cimg::superset< unsigned int, cimg_int64 >`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01int_00_01cimg__int64_01_4) | 
`struct `[`cimg_library_suffixed::cimg::superset< unsigned int, cimg_uint64 >`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01int_00_01cimg__uint64_01_4) | 
`struct `[`cimg_library_suffixed::cimg::superset< unsigned int, double >`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01int_00_01double_01_4) | 
`struct `[`cimg_library_suffixed::cimg::superset< unsigned int, float >`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01int_00_01float_01_4) | 
`struct `[`cimg_library_suffixed::cimg::superset< unsigned int, int >`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01int_00_01int_01_4) | 
`struct `[`cimg_library_suffixed::cimg::superset< unsigned int, short >`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01int_00_01short_01_4) | 
`struct `[`cimg_library_suffixed::cimg::superset< unsigned int, signed char >`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01int_00_01signed_01char_01_4) | 
`struct `[`cimg_library_suffixed::cimg::superset< unsigned short, char >`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01short_00_01char_01_4) | 
`struct `[`cimg_library_suffixed::cimg::superset< unsigned short, cimg_int64 >`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01short_00_01cimg__int64_01_4) | 
`struct `[`cimg_library_suffixed::cimg::superset< unsigned short, cimg_uint64 >`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01short_00_01cimg__uint64_01_4) | 
`struct `[`cimg_library_suffixed::cimg::superset< unsigned short, double >`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01short_00_01double_01_4) | 
`struct `[`cimg_library_suffixed::cimg::superset< unsigned short, float >`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01short_00_01float_01_4) | 
`struct `[`cimg_library_suffixed::cimg::superset< unsigned short, int >`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01short_00_01int_01_4) | 
`struct `[`cimg_library_suffixed::cimg::superset< unsigned short, short >`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01short_00_01short_01_4) | 
`struct `[`cimg_library_suffixed::cimg::superset< unsigned short, signed char >`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01short_00_01signed_01char_01_4) | 
`struct `[`cimg_library_suffixed::cimg::superset< unsigned short, unsigned int >`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01short_00_01unsigned_01int_01_4) | 
`struct `[`cimg_library_suffixed::cimg::type`](#structcimg__library__suffixed_1_1cimg_1_1type) | 
`struct `[`cimg_library_suffixed::cimg::type< bool >`](#structcimg__library__suffixed_1_1cimg_1_1type_3_01bool_01_4) | 
`struct `[`cimg_library_suffixed::cimg::type< char >`](#structcimg__library__suffixed_1_1cimg_1_1type_3_01char_01_4) | 
`struct `[`cimg_library_suffixed::cimg::type< cimg_int64 >`](#structcimg__library__suffixed_1_1cimg_1_1type_3_01cimg__int64_01_4) | 
`struct `[`cimg_library_suffixed::cimg::type< cimg_uint64 >`](#structcimg__library__suffixed_1_1cimg_1_1type_3_01cimg__uint64_01_4) | 
`struct `[`cimg_library_suffixed::cimg::type< double >`](#structcimg__library__suffixed_1_1cimg_1_1type_3_01double_01_4) | 
`struct `[`cimg_library_suffixed::cimg::type< float >`](#structcimg__library__suffixed_1_1cimg_1_1type_3_01float_01_4) | 
`struct `[`cimg_library_suffixed::cimg::type< int >`](#structcimg__library__suffixed_1_1cimg_1_1type_3_01int_01_4) | 
`struct `[`cimg_library_suffixed::cimg::type< long double >`](#structcimg__library__suffixed_1_1cimg_1_1type_3_01long_01double_01_4) | 
`struct `[`cimg_library_suffixed::cimg::type< short >`](#structcimg__library__suffixed_1_1cimg_1_1type_3_01short_01_4) | 
`struct `[`cimg_library_suffixed::cimg::type< signed char >`](#structcimg__library__suffixed_1_1cimg_1_1type_3_01signed_01char_01_4) | 
`struct `[`cimg_library_suffixed::cimg::type< unsigned char >`](#structcimg__library__suffixed_1_1cimg_1_1type_3_01unsigned_01char_01_4) | 
`struct `[`cimg_library_suffixed::cimg::type< unsigned int >`](#structcimg__library__suffixed_1_1cimg_1_1type_3_01unsigned_01int_01_4) | 
`struct `[`cimg_library_suffixed::cimg::type< unsigned short >`](#structcimg__library__suffixed_1_1cimg_1_1type_3_01unsigned_01short_01_4) | 

<h2> Members </h2>

#### `public inline std::FILE * `[`output`](#namespacecimg__library__suffixed_1_1cimg_1ada686776cc71803df391eea79cd1b3e5)`(std::FILE * file)` {#namespacecimg__library__suffixed_1_1cimg_1ada686776cc71803df391eea79cd1b3e5}

Get/set default output stream for the \CImg library messages.

#### Parameters
* `file` Desired output stream. Set to `0` to get the currently used output stream only. 

#### Returns
Currently used output stream.

#### `public inline void `[`info`](#namespacecimg__library__suffixed_1_1cimg_1a79b7a247520612001a04d8ef1c2991dc)`()` {#namespacecimg__library__suffixed_1_1cimg_1a79b7a247520612001a04d8ef1c2991dc}

Print information about \CImg environment variables.

Output is done on the default output stream.

#### `public template<>`  <br/>`inline void `[`unused`](#namespacecimg__library__suffixed_1_1cimg_1a79aef0cbcf66ceb71c2b74cb66b4deb2)`(const T &,...)` {#namespacecimg__library__suffixed_1_1cimg_1a79aef0cbcf66ceb71c2b74cb66b4deb2}

Avoid warning messages due to unused parameters. Do nothing actually.

#### `public inline int `[`mutex`](#namespacecimg__library__suffixed_1_1cimg_1a9e739e4b4ac058abfba069466617b914)`(const unsigned int n,const int lock_mode)` {#namespacecimg__library__suffixed_1_1cimg_1a9e739e4b4ac058abfba069466617b914}

#### `public inline unsigned int & `[`exception_mode`](#namespacecimg__library__suffixed_1_1cimg_1a9414cac8b0ab20669320c37878fe54cc)`(const unsigned int value,const bool is_set)` {#namespacecimg__library__suffixed_1_1cimg_1a9414cac8b0ab20669320c37878fe54cc}

#### `public inline FILE * `[`_stdin`](#namespacecimg__library__suffixed_1_1cimg_1a01a3b743897290604513ea6d847c9886)`(const bool throw_exception)` {#namespacecimg__library__suffixed_1_1cimg_1a01a3b743897290604513ea6d847c9886}

#### `public inline FILE * `[`_stdout`](#namespacecimg__library__suffixed_1_1cimg_1a493220746e5df3466568bd7862825008)`(const bool throw_exception)` {#namespacecimg__library__suffixed_1_1cimg_1a493220746e5df3466568bd7862825008}

#### `public inline FILE * `[`_stderr`](#namespacecimg__library__suffixed_1_1cimg_1aab8db7528c32a8fd3a3dc471e662782e)`(const bool throw_exception)` {#namespacecimg__library__suffixed_1_1cimg_1aab8db7528c32a8fd3a3dc471e662782e}

#### `public inline unsigned int & `[`exception_mode`](#namespacecimg__library__suffixed_1_1cimg_1aeafab144366eddd11360f32f468fa4af)`(const unsigned int mode)` {#namespacecimg__library__suffixed_1_1cimg_1aeafab144366eddd11360f32f468fa4af}

Set current \CImg exception mode.

The way error messages are handled by \CImg can be changed dynamically, using this function. 
#### Parameters
* `mode` Desired exception mode. Possible values are:

* `0`: Hide library messages (quiet mode).

* `1`: Print library messages on the console.

* `2`: Display library messages on a dialog window.

* `3`: Do as `1` + add extra debug warnings (slow down the code!).

* `4`: Do as `2` + add extra debug warnings (slow down the code!).

#### `public inline unsigned int & `[`exception_mode`](#namespacecimg__library__suffixed_1_1cimg_1a3ee303866379f1c38eb4807afb3c946a)`()` {#namespacecimg__library__suffixed_1_1cimg_1a3ee303866379f1c38eb4807afb3c946a}

Return current \CImg exception mode.

By default, return the value of configuration macro `cimg_verbosity`

#### `public inline unsigned int `[`openmp_mode`](#namespacecimg__library__suffixed_1_1cimg_1a06322e0d3fc278be42e1b3ca3dc3c3d4)`(const unsigned int value,const bool is_set)` {#namespacecimg__library__suffixed_1_1cimg_1a06322e0d3fc278be42e1b3ca3dc3c3d4}

#### `public inline unsigned int `[`openmp_mode`](#namespacecimg__library__suffixed_1_1cimg_1a11975ce0856ede8abd5789e37d82de56)`(const unsigned int mode)` {#namespacecimg__library__suffixed_1_1cimg_1a11975ce0856ede8abd5789e37d82de56}

Set current \CImg openmp mode.

The way openmp-based methods are handled by \CImg can be changed dynamically, using this function. 
#### Parameters
* `mode` Desired openmp mode. Possible values are:

* `0`: Never parallelize.

* `1`: Always parallelize.

* `2`: Adaptive parallelization mode (default behavior).

#### `public inline unsigned int `[`openmp_mode`](#namespacecimg__library__suffixed_1_1cimg_1add0bfd01ecfbfdd24cccf9d2d5640d92)`()` {#namespacecimg__library__suffixed_1_1cimg_1add0bfd01ecfbfdd24cccf9d2d5640d92}

Return current \CImg openmp mode.

#### `public inline int `[`dialog`](#namespacecimg__library__suffixed_1_1cimg_1a89ad6cacc2ade7f8077d34fc6f455dc3)`(const char *const title,const char *const msg,const char *const button1_label,const char *const button2_label,const char *const button3_label,const char *const button4_label,const char *const button5_label,const char *const button6_label,const bool centering)` {#namespacecimg__library__suffixed_1_1cimg_1a89ad6cacc2ade7f8077d34fc6f455dc3}

Display a simple dialog box, and wait for the user's response \specialization.

#### `public inline double `[`eval`](#namespacecimg__library__suffixed_1_1cimg_1a4574a27654d00ba42a108368fa9d7e64)`(const char *const expression,const double x,const double y,const double z,const double c)` {#namespacecimg__library__suffixed_1_1cimg_1a4574a27654d00ba42a108368fa9d7e64}

Evaluate math expression.

#### Parameters
* `expression` C-string describing the formula to evaluate. 

* `x` Value of the pre-defined variable `x`. 

* `y` Value of the pre-defined variable `y`. 

* `z` Value of the pre-defined variable `z`. 

* `c` Value of the pre-defined variable `c`. 

#### Returns
Result of the formula evaluation. 

Set `expression` to `0` to keep evaluating the last specified `expression`. 

Example
```cpp
const double
res1 = cimg::eval("cos(x)^2 + sin(y)^2",2,2),  // will return '1'
res2 = cimg::eval(0,1,1);                    // will return '1' too
```

#### `public inline `[`Mutex_static`](#structcimg__library__suffixed_1_1cimg_1_1Mutex__static)` & `[`Mutex_attr`](#namespacecimg__library__suffixed_1_1cimg_1a0e04fc458732d8608e2739ba724757af)`()` {#namespacecimg__library__suffixed_1_1cimg_1a0e04fc458732d8608e2739ba724757af}

#### `public inline unsigned int `[`nb_cpus`](#namespacecimg__library__suffixed_1_1cimg_1ad359a27ccc2eea27d3a6f1073b2a2ad7)`()` {#namespacecimg__library__suffixed_1_1cimg_1ad359a27ccc2eea27d3a6f1073b2a2ad7}

#### `public inline void `[`warn`](#namespacecimg__library__suffixed_1_1cimg_1acfd3624d72ed7f79c82ec45646c685e7)`(const char *const format,...)` {#namespacecimg__library__suffixed_1_1cimg_1acfd3624d72ed7f79c82ec45646c685e7}

Display a warning message on the default output stream.

#### Parameters
* `format` C-string containing the format of the message, as with `std::printf()`. 

If configuration macro `cimg_strict_warnings` is set, this function throws a `[CImgWarningException](#structcimg__library__suffixed_1_1CImgWarningException)` instead. 

As the first argument is a format string, it is highly recommended to write 
```cpp
cimg::warn("%s",warning_message);
```
 instead of 
```cpp
cimg::warn(warning_message);
```
 if `warning_message` can be arbitrary, to prevent nasty memory access.

#### `public inline int `[`system`](#namespacecimg__library__suffixed_1_1cimg_1a5ddfa532b09b12973f543977f1f688da)`(const char *const command,const char *const module_name,const bool is_verbose)` {#namespacecimg__library__suffixed_1_1cimg_1a5ddfa532b09b12973f543977f1f688da}

#### Parameters
* `command` C-string containing the command line to execute. 

* `module_name` Module name. 

#### Returns
Status value of the executed command, whose meaning is OS-dependent. 

This function is similar to `std::system()` but it does not open an extra console windows on Windows-based systems.

#### `public template<>`  <br/>`inline T & `[`temporary`](#namespacecimg__library__suffixed_1_1cimg_1af931f5a4ed9addcbb7a7d27abd7670e5)`(const T &)` {#namespacecimg__library__suffixed_1_1cimg_1af931f5a4ed9addcbb7a7d27abd7670e5}

Return a reference to a temporary variable of type T.

#### `public template<>`  <br/>`inline void `[`swap`](#namespacecimg__library__suffixed_1_1cimg_1a337eb7828c4ba8532f16e55d0c1468d6)`(T & a,T & b)` {#namespacecimg__library__suffixed_1_1cimg_1a337eb7828c4ba8532f16e55d0c1468d6}

Exchange values of variables `a` and `b`.

#### `public template<>`  <br/>`inline void `[`swap`](#namespacecimg__library__suffixed_1_1cimg_1aa4d77ad5aa3b88a07257c583a1b5d475)`(T1 & a1,T1 & b1,T2 & a2,T2 & b2)` {#namespacecimg__library__suffixed_1_1cimg_1aa4d77ad5aa3b88a07257c583a1b5d475}

Exchange values of variables (`a1`,`a2`) and (`b1`,`b2`).

#### `public template<>`  <br/>`inline void `[`swap`](#namespacecimg__library__suffixed_1_1cimg_1a8e3fcd4b409a2dbd6e61492e2314ed54)`(T1 & a1,T1 & b1,T2 & a2,T2 & b2,T3 & a3,T3 & b3)` {#namespacecimg__library__suffixed_1_1cimg_1a8e3fcd4b409a2dbd6e61492e2314ed54}

Exchange values of variables (`a1`,`a2`,`a3`) and (`b1`,`b2`,`b3`).

#### `public template<>`  <br/>`inline void `[`swap`](#namespacecimg__library__suffixed_1_1cimg_1af4d154f5618084396d21cad69ad479d9)`(T1 & a1,T1 & b1,T2 & a2,T2 & b2,T3 & a3,T3 & b3,T4 & a4,T4 & b4)` {#namespacecimg__library__suffixed_1_1cimg_1af4d154f5618084396d21cad69ad479d9}

Exchange values of variables (`a1`,`a2`,...,`a4`) and (`b1`,`b2`,...,`b4`).

#### `public template<>`  <br/>`inline void `[`swap`](#namespacecimg__library__suffixed_1_1cimg_1a33b9455bf35220ad528091a83ac68707)`(T1 & a1,T1 & b1,T2 & a2,T2 & b2,T3 & a3,T3 & b3,T4 & a4,T4 & b4,T5 & a5,T5 & b5)` {#namespacecimg__library__suffixed_1_1cimg_1a33b9455bf35220ad528091a83ac68707}

Exchange values of variables (`a1`,`a2`,...,`a5`) and (`b1`,`b2`,...,`b5`).

#### `public template<>`  <br/>`inline void `[`swap`](#namespacecimg__library__suffixed_1_1cimg_1a36c2243bde47df38d2d29c32a044e531)`(T1 & a1,T1 & b1,T2 & a2,T2 & b2,T3 & a3,T3 & b3,T4 & a4,T4 & b4,T5 & a5,T5 & b5,T6 & a6,T6 & b6)` {#namespacecimg__library__suffixed_1_1cimg_1a36c2243bde47df38d2d29c32a044e531}

Exchange values of variables (`a1`,`a2`,...,`a6`) and (`b1`,`b2`,...,`b6`).

#### `public template<>`  <br/>`inline void `[`swap`](#namespacecimg__library__suffixed_1_1cimg_1aca980117982a98452e2106fda638def1)`(T1 & a1,T1 & b1,T2 & a2,T2 & b2,T3 & a3,T3 & b3,T4 & a4,T4 & b4,T5 & a5,T5 & b5,T6 & a6,T6 & b6,T7 & a7,T7 & b7)` {#namespacecimg__library__suffixed_1_1cimg_1aca980117982a98452e2106fda638def1}

Exchange values of variables (`a1`,`a2`,...,`a7`) and (`b1`,`b2`,...,`b7`).

#### `public template<>`  <br/>`inline void `[`swap`](#namespacecimg__library__suffixed_1_1cimg_1a2f261b2759f7ba63c4bc84267d5a20c8)`(T1 & a1,T1 & b1,T2 & a2,T2 & b2,T3 & a3,T3 & b3,T4 & a4,T4 & b4,T5 & a5,T5 & b5,T6 & a6,T6 & b6,T7 & a7,T7 & b7,T8 & a8,T8 & b8)` {#namespacecimg__library__suffixed_1_1cimg_1a2f261b2759f7ba63c4bc84267d5a20c8}

Exchange values of variables (`a1`,`a2`,...,`a8`) and (`b1`,`b2`,...,`b8`).

#### `public inline bool `[`endianness`](#namespacecimg__library__suffixed_1_1cimg_1afd898f29e094a625d15928ed19a6b69d)`()` {#namespacecimg__library__suffixed_1_1cimg_1afd898f29e094a625d15928ed19a6b69d}

Return the endianness of the current architecture.

#### Returns
`false` for *Little Endian* or `true` for *Big Endian*.

#### `public template<>`  <br/>`inline void `[`invert_endianness`](#namespacecimg__library__suffixed_1_1cimg_1a1f8e231e39844ce1685d2fa80edd852d)`(T *const buffer,const cimg_ulong size)` {#namespacecimg__library__suffixed_1_1cimg_1a1f8e231e39844ce1685d2fa80edd852d}

Reverse endianness of all elements in a memory buffer.

#### Parameters
* `buffer` Memory buffer whose endianness must be reversed. 

* `size` Number of buffer elements to reverse.

#### `public template<>`  <br/>`inline T & `[`invert_endianness`](#namespacecimg__library__suffixed_1_1cimg_1aaa2e6e8ccab85cc7fc7b9f02060965a2)`(T & a)` {#namespacecimg__library__suffixed_1_1cimg_1aaa2e6e8ccab85cc7fc7b9f02060965a2}

Reverse endianness of a single variable.

#### Parameters
* `a` Variable to reverse. 

#### Returns
Reference to reversed variable.

#### `public inline unsigned int `[`float2uint`](#namespacecimg__library__suffixed_1_1cimg_1abeb336981cf553b3244c800b781e313d)`(const float f)` {#namespacecimg__library__suffixed_1_1cimg_1abeb336981cf553b3244c800b781e313d}

#### `public inline float `[`uint2float`](#namespacecimg__library__suffixed_1_1cimg_1a6293f332d662f83e39a5a388b5abd222)`(const unsigned int u)` {#namespacecimg__library__suffixed_1_1cimg_1a6293f332d662f83e39a5a388b5abd222}

#### `public inline cimg_uint64 `[`time`](#namespacecimg__library__suffixed_1_1cimg_1a67e7c7cbeb79de5fc2f6a21afb06d413)`()` {#namespacecimg__library__suffixed_1_1cimg_1a67e7c7cbeb79de5fc2f6a21afb06d413}

Return the value of a system timer, with a millisecond precision.

The timer does not necessarily starts from `0`.

#### `public inline cimg_uint64 `[`tictoc`](#namespacecimg__library__suffixed_1_1cimg_1a6f96cd4f49d44a2224d3e87b0efdf633)`(const bool is_tic)` {#namespacecimg__library__suffixed_1_1cimg_1a6f96cd4f49d44a2224d3e87b0efdf633}

#### `public inline cimg_uint64 `[`tic`](#namespacecimg__library__suffixed_1_1cimg_1a0455de0827cac0a81e421ef873a95acc)`()` {#namespacecimg__library__suffixed_1_1cimg_1a0455de0827cac0a81e421ef873a95acc}

Start tic/toc timer for time measurement between code instructions.

#### Returns
Current value of the timer (same value as [time()](#namespacecimg__library__suffixed_1_1cimg_1a67e7c7cbeb79de5fc2f6a21afb06d413)).

#### `public inline cimg_uint64 `[`toc`](#namespacecimg__library__suffixed_1_1cimg_1a97115cec272070446ec968fb2c59c2fe)`()` {#namespacecimg__library__suffixed_1_1cimg_1a97115cec272070446ec968fb2c59c2fe}

End tic/toc timer and displays elapsed time from last call to [tic()](#namespacecimg__library__suffixed_1_1cimg_1a0455de0827cac0a81e421ef873a95acc).

#### Returns
Time elapsed (in ms) since last call to [tic()](#namespacecimg__library__suffixed_1_1cimg_1a0455de0827cac0a81e421ef873a95acc).

#### `public inline void `[`sleep`](#namespacecimg__library__suffixed_1_1cimg_1aa2bf8fb0d97c122cbc52e1f2e167e8a6)`(const unsigned int milliseconds)` {#namespacecimg__library__suffixed_1_1cimg_1aa2bf8fb0d97c122cbc52e1f2e167e8a6}

Sleep for a given numbers of milliseconds.

#### Parameters
* `milliseconds` Number of milliseconds to wait for. 

This function frees the CPU resources during the sleeping time. It can be used to temporize your program properly, without wasting CPU time.

#### `public inline unsigned int `[`wait`](#namespacecimg__library__suffixed_1_1cimg_1a5f13deafde0dfee1c1350674f2ddb1df)`(const unsigned int milliseconds,cimg_uint64 *const p_timer)` {#namespacecimg__library__suffixed_1_1cimg_1a5f13deafde0dfee1c1350674f2ddb1df}

#### `public inline unsigned int `[`wait`](#namespacecimg__library__suffixed_1_1cimg_1a88541ea6dcaca1badfeee4367abbd687)`(const unsigned int milliseconds)` {#namespacecimg__library__suffixed_1_1cimg_1a88541ea6dcaca1badfeee4367abbd687}

Wait for a given number of milliseconds since the last call to wait().

#### Parameters
* `milliseconds` Number of milliseconds to wait for. 

#### Returns
Number of milliseconds elapsed since the last call to wait(). 

Same as [sleep()](#namespacecimg__library__suffixed_1_1cimg_1aa2bf8fb0d97c122cbc52e1f2e167e8a6) with a waiting time computed with regard to the last call of wait(). It may be used to temporize your program properly, without wasting CPU time.

#### `public inline cimg_uint64 & `[`rng`](#namespacecimg__library__suffixed_1_1cimg_1a236af06ba834ec94eb49bda7a60a854f)`()` {#namespacecimg__library__suffixed_1_1cimg_1a236af06ba834ec94eb49bda7a60a854f}

#### `public inline unsigned int `[`_rand`](#namespacecimg__library__suffixed_1_1cimg_1a89b0e50db97e9a872e1bed2cb02fc3c0)`(cimg_uint64 *const p_rng)` {#namespacecimg__library__suffixed_1_1cimg_1a89b0e50db97e9a872e1bed2cb02fc3c0}

#### `public inline unsigned int `[`_rand`](#namespacecimg__library__suffixed_1_1cimg_1ac83dc4391189607ffb3b175f3d627485)`()` {#namespacecimg__library__suffixed_1_1cimg_1ac83dc4391189607ffb3b175f3d627485}

#### `public inline void `[`srand`](#namespacecimg__library__suffixed_1_1cimg_1a015732105aafd2d82000eb8ab20fb826)`(cimg_uint64 *const p_rng)` {#namespacecimg__library__suffixed_1_1cimg_1a015732105aafd2d82000eb8ab20fb826}

#### `public inline void `[`srand`](#namespacecimg__library__suffixed_1_1cimg_1a96eab94d07b195c5773617bad4f10936)`()` {#namespacecimg__library__suffixed_1_1cimg_1a96eab94d07b195c5773617bad4f10936}

#### `public inline void `[`srand`](#namespacecimg__library__suffixed_1_1cimg_1af0edbf83957282cd6a5da53a5e60e028)`(const cimg_uint64 seed)` {#namespacecimg__library__suffixed_1_1cimg_1af0edbf83957282cd6a5da53a5e60e028}

#### `public inline double `[`rand`](#namespacecimg__library__suffixed_1_1cimg_1a9ec6c3ef7942ced482047db3e351c9eb)`(const double val_min,const double val_max,cimg_uint64 *const p_rng)` {#namespacecimg__library__suffixed_1_1cimg_1a9ec6c3ef7942ced482047db3e351c9eb}

#### `public inline double `[`rand`](#namespacecimg__library__suffixed_1_1cimg_1ab7c09300be61c8a3361c379069100252)`(const double val_min,const double val_max)` {#namespacecimg__library__suffixed_1_1cimg_1ab7c09300be61c8a3361c379069100252}

#### `public inline double `[`rand`](#namespacecimg__library__suffixed_1_1cimg_1a0bfdfa57a9210107cfd0bce50083202d)`(const double val_max,cimg_uint64 *const p_rng)` {#namespacecimg__library__suffixed_1_1cimg_1a0bfdfa57a9210107cfd0bce50083202d}

#### `public inline double `[`rand`](#namespacecimg__library__suffixed_1_1cimg_1af5cd3397f819c13ccb17e05a7db736b1)`(const double val_max)` {#namespacecimg__library__suffixed_1_1cimg_1af5cd3397f819c13ccb17e05a7db736b1}

#### `public inline double `[`grand`](#namespacecimg__library__suffixed_1_1cimg_1acc4e8695bc96e4629c633368db7ed8b7)`(cimg_uint64 *const p_rng)` {#namespacecimg__library__suffixed_1_1cimg_1acc4e8695bc96e4629c633368db7ed8b7}

#### `public inline double `[`grand`](#namespacecimg__library__suffixed_1_1cimg_1aa12c572ad67f655e27f7b8e3e76dafa5)`()` {#namespacecimg__library__suffixed_1_1cimg_1aa12c572ad67f655e27f7b8e3e76dafa5}

#### `public inline unsigned int `[`prand`](#namespacecimg__library__suffixed_1_1cimg_1a6bd76bd6c22a253a7c76927fba792333)`(const double z,cimg_uint64 *const p_rng)` {#namespacecimg__library__suffixed_1_1cimg_1a6bd76bd6c22a253a7c76927fba792333}

#### `public inline unsigned int `[`prand`](#namespacecimg__library__suffixed_1_1cimg_1a2a18bbfb6a496d8d5a02943be8eaa936)`(const double z)` {#namespacecimg__library__suffixed_1_1cimg_1a2a18bbfb6a496d8d5a02943be8eaa936}

#### `public template<>`  <br/>`inline T `[`cut`](#namespacecimg__library__suffixed_1_1cimg_1a60c895ccdb84e7ccdd884ff61bab29f0)`(const T & val,const t & val_min,const t & val_max)` {#namespacecimg__library__suffixed_1_1cimg_1a60c895ccdb84e7ccdd884ff61bab29f0}

Cut (i.e. clamp) value in specified interval.

#### `public template<>`  <br/>`inline T `[`rol`](#namespacecimg__library__suffixed_1_1cimg_1a1ead565c35064488c8a56fce858da674)`(const T & a,const unsigned int n)` {#namespacecimg__library__suffixed_1_1cimg_1a1ead565c35064488c8a56fce858da674}

Bitwise-rotate value on the left.

#### `public inline float `[`rol`](#namespacecimg__library__suffixed_1_1cimg_1afb7d512cc0b5473301a060131bd415af)`(const float a,const unsigned int n)` {#namespacecimg__library__suffixed_1_1cimg_1afb7d512cc0b5473301a060131bd415af}

#### `public inline double `[`rol`](#namespacecimg__library__suffixed_1_1cimg_1a4263e5084b1303cc58b50650366bab36)`(const double a,const unsigned int n)` {#namespacecimg__library__suffixed_1_1cimg_1a4263e5084b1303cc58b50650366bab36}

#### `public inline double `[`rol`](#namespacecimg__library__suffixed_1_1cimg_1aeee82dc035ff6c75d8b05530771090d3)`(const long double a,const unsigned int n)` {#namespacecimg__library__suffixed_1_1cimg_1aeee82dc035ff6c75d8b05530771090d3}

#### `public template<>`  <br/>`inline T `[`ror`](#namespacecimg__library__suffixed_1_1cimg_1ab616eb52e66e664293d16a9bcfa9a9b4)`(const T & a,const unsigned int n)` {#namespacecimg__library__suffixed_1_1cimg_1ab616eb52e66e664293d16a9bcfa9a9b4}

Bitwise-rotate value on the right.

#### `public inline float `[`ror`](#namespacecimg__library__suffixed_1_1cimg_1a0cc69aa64bca2114676aebf2f689e5e8)`(const float a,const unsigned int n)` {#namespacecimg__library__suffixed_1_1cimg_1a0cc69aa64bca2114676aebf2f689e5e8}

#### `public inline double `[`ror`](#namespacecimg__library__suffixed_1_1cimg_1a4ac3e4e4369af3c0f7a40fb4ef435e82)`(const double a,const unsigned int n)` {#namespacecimg__library__suffixed_1_1cimg_1a4ac3e4e4369af3c0f7a40fb4ef435e82}

#### `public inline double `[`ror`](#namespacecimg__library__suffixed_1_1cimg_1a28a92e1f3aec1b1ff7a6c4277473144d)`(const long double a,const unsigned int n)` {#namespacecimg__library__suffixed_1_1cimg_1a28a92e1f3aec1b1ff7a6c4277473144d}

#### `public template<>`  <br/>`inline T `[`abs`](#namespacecimg__library__suffixed_1_1cimg_1a0852e9ad458e82d2c003844cd92bdb8a)`(const T & a)` {#namespacecimg__library__suffixed_1_1cimg_1a0852e9ad458e82d2c003844cd92bdb8a}

Return absolute value of a value.

#### `public inline bool `[`abs`](#namespacecimg__library__suffixed_1_1cimg_1a58594a6c544821be41beb663f65ae6f7)`(const bool a)` {#namespacecimg__library__suffixed_1_1cimg_1a58594a6c544821be41beb663f65ae6f7}

#### `public inline int `[`abs`](#namespacecimg__library__suffixed_1_1cimg_1a98875c08cd797ad18f78b3010d998f43)`(const unsigned char a)` {#namespacecimg__library__suffixed_1_1cimg_1a98875c08cd797ad18f78b3010d998f43}

#### `public inline int `[`abs`](#namespacecimg__library__suffixed_1_1cimg_1ac065ecac4db3e755a220ba19e423ebb4)`(const unsigned short a)` {#namespacecimg__library__suffixed_1_1cimg_1ac065ecac4db3e755a220ba19e423ebb4}

#### `public inline int `[`abs`](#namespacecimg__library__suffixed_1_1cimg_1a442fd2c14c431028a04c10618aa03261)`(const unsigned int a)` {#namespacecimg__library__suffixed_1_1cimg_1a442fd2c14c431028a04c10618aa03261}

#### `public inline int `[`abs`](#namespacecimg__library__suffixed_1_1cimg_1a26acb5583d30cb7eeea839ef82a73270)`(const int a)` {#namespacecimg__library__suffixed_1_1cimg_1a26acb5583d30cb7eeea839ef82a73270}

#### `public inline cimg_int64 `[`abs`](#namespacecimg__library__suffixed_1_1cimg_1a806bd69aeff5adab7bb5081132f5c68b)`(const cimg_uint64 a)` {#namespacecimg__library__suffixed_1_1cimg_1a806bd69aeff5adab7bb5081132f5c68b}

#### `public inline double `[`abs`](#namespacecimg__library__suffixed_1_1cimg_1a257cae0845617a5813b23d8668ab01a6)`(const double a)` {#namespacecimg__library__suffixed_1_1cimg_1a257cae0845617a5813b23d8668ab01a6}

#### `public inline float `[`abs`](#namespacecimg__library__suffixed_1_1cimg_1a37ec01e1d8db19fdd1a0c4bfa73e3879)`(const float a)` {#namespacecimg__library__suffixed_1_1cimg_1a37ec01e1d8db19fdd1a0c4bfa73e3879}

#### `public inline double `[`acosh`](#namespacecimg__library__suffixed_1_1cimg_1a7a4d9fec1f28d1788e47e739fd7089c6)`(const double x)` {#namespacecimg__library__suffixed_1_1cimg_1a7a4d9fec1f28d1788e47e739fd7089c6}

Return hyperbolic arcosine of a value.

#### `public inline double `[`asinh`](#namespacecimg__library__suffixed_1_1cimg_1a3bbc85a1a73b23640d6a5a2846cc79d9)`(const double x)` {#namespacecimg__library__suffixed_1_1cimg_1a3bbc85a1a73b23640d6a5a2846cc79d9}

Return hyperbolic arcsine of a value.

#### `public inline double `[`atanh`](#namespacecimg__library__suffixed_1_1cimg_1abbd663a9475a67825564aeb3b34687ed)`(const double x)` {#namespacecimg__library__suffixed_1_1cimg_1abbd663a9475a67825564aeb3b34687ed}

Return hyperbolic arctangent of a value.

#### `public inline double `[`sinc`](#namespacecimg__library__suffixed_1_1cimg_1ae3375412d53d28356063384da9fd9ad2)`(const double x)` {#namespacecimg__library__suffixed_1_1cimg_1ae3375412d53d28356063384da9fd9ad2}

Return the sinc of a given value.

#### `public inline double `[`log2`](#namespacecimg__library__suffixed_1_1cimg_1a03657cf098d3b588e76bcef4426233bd)`(const double x)` {#namespacecimg__library__suffixed_1_1cimg_1a03657cf098d3b588e76bcef4426233bd}

Return base-2 logarithm of a value.

#### `public template<>`  <br/>`inline T `[`sqr`](#namespacecimg__library__suffixed_1_1cimg_1ac6d817f750ba83dd8f8b1b64aaaf8b19)`(const T & val)` {#namespacecimg__library__suffixed_1_1cimg_1ac6d817f750ba83dd8f8b1b64aaaf8b19}

Return square of a value.

#### `public template<>`  <br/>`inline double `[`cbrt`](#namespacecimg__library__suffixed_1_1cimg_1ad72601dd5481dc3abd338d9ed1604622)`(const T & x)` {#namespacecimg__library__suffixed_1_1cimg_1ad72601dd5481dc3abd338d9ed1604622}

Return cubic root of a value.

#### `public template<>`  <br/>`inline T `[`pow3`](#namespacecimg__library__suffixed_1_1cimg_1a51beb9e6a54e050ed4e4783d8f1374eb)`(const T & val)` {#namespacecimg__library__suffixed_1_1cimg_1a51beb9e6a54e050ed4e4783d8f1374eb}

#### `public template<>`  <br/>`inline T `[`pow4`](#namespacecimg__library__suffixed_1_1cimg_1a9521f5be7c0f270bfe409214e4c2ebee)`(const T & val)` {#namespacecimg__library__suffixed_1_1cimg_1a9521f5be7c0f270bfe409214e4c2ebee}

#### `public template<>`  <br/>`inline t `[`min`](#namespacecimg__library__suffixed_1_1cimg_1a091c508a646a5459c00aa2b5ac9ea5e5)`(const t & a,const t & b,const t & c)` {#namespacecimg__library__suffixed_1_1cimg_1a091c508a646a5459c00aa2b5ac9ea5e5}

Return the minimum between three values.

#### `public template<>`  <br/>`inline t `[`min`](#namespacecimg__library__suffixed_1_1cimg_1ad5459593e7f8a4066cb22ad63de8e92d)`(const t & a,const t & b,const t & c,const t & d)` {#namespacecimg__library__suffixed_1_1cimg_1ad5459593e7f8a4066cb22ad63de8e92d}

Return the minimum between four values.

#### `public template<>`  <br/>`inline t `[`minabs`](#namespacecimg__library__suffixed_1_1cimg_1a81ff5885c4c8a51e149d527e85762559)`(const t & a,const t & b)` {#namespacecimg__library__suffixed_1_1cimg_1a81ff5885c4c8a51e149d527e85762559}

Return the minabs between two values.

#### `public template<>`  <br/>`inline t `[`minabs`](#namespacecimg__library__suffixed_1_1cimg_1a1f5925ace392b6747002f18ae57c0a39)`(const t & a,const t & b,const t & abs_b)` {#namespacecimg__library__suffixed_1_1cimg_1a1f5925ace392b6747002f18ae57c0a39}

#### `public template<>`  <br/>`inline t `[`max`](#namespacecimg__library__suffixed_1_1cimg_1aae5df5731fe5a367cec402071108c11c)`(const t & a,const t & b,const t & c)` {#namespacecimg__library__suffixed_1_1cimg_1aae5df5731fe5a367cec402071108c11c}

Return the maximum between three values.

#### `public template<>`  <br/>`inline t `[`max`](#namespacecimg__library__suffixed_1_1cimg_1a4b4cabc621d732787bca13016ea8026a)`(const t & a,const t & b,const t & c,const t & d)` {#namespacecimg__library__suffixed_1_1cimg_1a4b4cabc621d732787bca13016ea8026a}

Return the maximum between four values.

#### `public template<>`  <br/>`inline t `[`maxabs`](#namespacecimg__library__suffixed_1_1cimg_1aeccf40e5b836c4b56e0dd2d240fb548a)`(const t & a,const t & b)` {#namespacecimg__library__suffixed_1_1cimg_1aeccf40e5b836c4b56e0dd2d240fb548a}

Return the maxabs between two values.

#### `public template<>`  <br/>`inline t `[`maxabs`](#namespacecimg__library__suffixed_1_1cimg_1af6639a9cff62792d394ccf38294741df)`(const t & a,const t & b,const t & abs_b)` {#namespacecimg__library__suffixed_1_1cimg_1af6639a9cff62792d394ccf38294741df}

#### `public template<>`  <br/>`inline T `[`sign`](#namespacecimg__library__suffixed_1_1cimg_1abecddd9720e89882ff3d10dd35f940d9)`(const T & x)` {#namespacecimg__library__suffixed_1_1cimg_1abecddd9720e89882ff3d10dd35f940d9}

Return the sign of a value.

#### `public template<>`  <br/>`inline cimg_uint64 `[`nearest_pow2`](#namespacecimg__library__suffixed_1_1cimg_1a3a01572a1d9c448556b2ffa87fde879b)`(const T & x)` {#namespacecimg__library__suffixed_1_1cimg_1a3a01572a1d9c448556b2ffa87fde879b}

Return the nearest power of 2 higher than given value.

#### `public template<>`  <br/>`inline T `[`mod`](#namespacecimg__library__suffixed_1_1cimg_1afcc02428c9b7d9100e1674369d25cc40)`(const T & x,const T & m)` {#namespacecimg__library__suffixed_1_1cimg_1afcc02428c9b7d9100e1674369d25cc40}

Return the modulo of a value.

#### Parameters
* `x` Input value. 

* `m` Modulo value. 

This modulo function accepts negative and floating-points modulo numbers, as well as variables of any type.

#### `public inline int `[`mod`](#namespacecimg__library__suffixed_1_1cimg_1ace8c511f2eaca41092ec4f62aa9661ab)`(const bool x,const bool m)` {#namespacecimg__library__suffixed_1_1cimg_1ace8c511f2eaca41092ec4f62aa9661ab}

#### `public inline int `[`mod`](#namespacecimg__library__suffixed_1_1cimg_1acaf502340ec0683b4ddabf5a792426c9)`(const unsigned char x,const unsigned char m)` {#namespacecimg__library__suffixed_1_1cimg_1acaf502340ec0683b4ddabf5a792426c9}

#### `public inline int `[`mod`](#namespacecimg__library__suffixed_1_1cimg_1aec9a354db76b695a13fd4d817286bd8d)`(const char x,const char m)` {#namespacecimg__library__suffixed_1_1cimg_1aec9a354db76b695a13fd4d817286bd8d}

#### `public inline int `[`mod`](#namespacecimg__library__suffixed_1_1cimg_1aba178f4f778631ba25c4d715a8bce274)`(const unsigned short x,const unsigned short m)` {#namespacecimg__library__suffixed_1_1cimg_1aba178f4f778631ba25c4d715a8bce274}

#### `public inline int `[`mod`](#namespacecimg__library__suffixed_1_1cimg_1a5bac7fb02f8b0b7f0436b2f58ae2e5e6)`(const short x,const short m)` {#namespacecimg__library__suffixed_1_1cimg_1a5bac7fb02f8b0b7f0436b2f58ae2e5e6}

#### `public inline int `[`mod`](#namespacecimg__library__suffixed_1_1cimg_1af5377d20e562b9a0eced0d2066b3c8ba)`(const unsigned int x,const unsigned int m)` {#namespacecimg__library__suffixed_1_1cimg_1af5377d20e562b9a0eced0d2066b3c8ba}

#### `public inline int `[`mod`](#namespacecimg__library__suffixed_1_1cimg_1ab87d2b561c521c920cd9f2143d222435)`(const int x,const int m)` {#namespacecimg__library__suffixed_1_1cimg_1ab87d2b561c521c920cd9f2143d222435}

#### `public inline cimg_int64 `[`mod`](#namespacecimg__library__suffixed_1_1cimg_1a2dbd8f870f77ce3b10731130ce059498)`(const cimg_uint64 x,const cimg_uint64 m)` {#namespacecimg__library__suffixed_1_1cimg_1a2dbd8f870f77ce3b10731130ce059498}

#### `public inline cimg_int64 `[`mod`](#namespacecimg__library__suffixed_1_1cimg_1ad3daae7244a90ad300eea619397db898)`(const cimg_int64 x,const cimg_int64 m)` {#namespacecimg__library__suffixed_1_1cimg_1ad3daae7244a90ad300eea619397db898}

#### `public template<>`  <br/>`inline T `[`minmod`](#namespacecimg__library__suffixed_1_1cimg_1ac9630aa9259053d209c7ff02823efda0)`(const T & a,const T & b)` {#namespacecimg__library__suffixed_1_1cimg_1ac9630aa9259053d209c7ff02823efda0}

Return the min-mod of two values.

*minmod(`a`,`b`)* is defined to be:

* *minmod(`a`,`b`) = min(`a`,`b`)*, if `a` and `b` have the same sign.

* *minmod(`a`,`b`) = 0*, if `a` and `b` have different signs.

#### `public template<>`  <br/>`inline T `[`round`](#namespacecimg__library__suffixed_1_1cimg_1a7bed9b422eb303150d7abb503e7201fc)`(const T & x)` {#namespacecimg__library__suffixed_1_1cimg_1a7bed9b422eb303150d7abb503e7201fc}

#### `public template<>`  <br/>`inline int `[`uiround`](#namespacecimg__library__suffixed_1_1cimg_1a5bd7100202f965808ce5a7e28b121ec8)`(const T x)` {#namespacecimg__library__suffixed_1_1cimg_1a5bd7100202f965808ce5a7e28b121ec8}

#### `public template<>`  <br/>`inline T `[`round`](#namespacecimg__library__suffixed_1_1cimg_1a66a32585b286a3c7f76d745107ae5300)`(const T & x,const double y,const int rounding_type)` {#namespacecimg__library__suffixed_1_1cimg_1a66a32585b286a3c7f76d745107ae5300}

Return rounded value.

#### Parameters
* `x` Value to be rounded. 

* `y` Rounding precision. 

* `rounding_type` Type of rounding operation (`0` = nearest, `-1` = backward, `1` = forward). 

#### Returns
Rounded value, having the same type as input value `x`.

#### `public template<>`  <br/>`inline T `[`median`](#namespacecimg__library__suffixed_1_1cimg_1acf4703b2dd4307ecbdf61e7fc5d93800)`(T val0,T val1)` {#namespacecimg__library__suffixed_1_1cimg_1acf4703b2dd4307ecbdf61e7fc5d93800}

#### `public template<>`  <br/>`inline T `[`median`](#namespacecimg__library__suffixed_1_1cimg_1ac941c3a7e6b58e225a63d0f8ee7a28b2)`(T val0,T val1,T val2)` {#namespacecimg__library__suffixed_1_1cimg_1ac941c3a7e6b58e225a63d0f8ee7a28b2}

#### `public template<>`  <br/>`inline T `[`median`](#namespacecimg__library__suffixed_1_1cimg_1abe9263120cac5615f302f88d2674aab6)`(T val0,T val1,T val2,T val3,T val4)` {#namespacecimg__library__suffixed_1_1cimg_1abe9263120cac5615f302f88d2674aab6}

#### `public template<>`  <br/>`inline T `[`median`](#namespacecimg__library__suffixed_1_1cimg_1ac800cb8692cd896502ea26f201e5dc2f)`(T val0,T val1,T val2,T val3,T val4,T val5,T val6)` {#namespacecimg__library__suffixed_1_1cimg_1ac800cb8692cd896502ea26f201e5dc2f}

#### `public template<>`  <br/>`inline T `[`median`](#namespacecimg__library__suffixed_1_1cimg_1a76eb106e5afc159f8ec892ddb206de1c)`(T val0,T val1,T val2,T val3,T val4,T val5,T val6,T val7,T val8)` {#namespacecimg__library__suffixed_1_1cimg_1a76eb106e5afc159f8ec892ddb206de1c}

#### `public template<>`  <br/>`inline T `[`median`](#namespacecimg__library__suffixed_1_1cimg_1ab87bc357192941440852178fc4820463)`(T val0,T val1,T val2,T val3,T val4,T val5,T val6,T val7,T val8,T val9,T val10,T val11,T val12)` {#namespacecimg__library__suffixed_1_1cimg_1ab87bc357192941440852178fc4820463}

#### `public template<>`  <br/>`inline T `[`median`](#namespacecimg__library__suffixed_1_1cimg_1aa147071742c37d4ed5698c612b2ff2f6)`(T val0,T val1,T val2,T val3,T val4,T val5,T val6,T val7,T val8,T val9,T val10,T val11,T val12,T val13,T val14,T val15,T val16,T val17,T val18,T val19,T val20,T val21,T val22,T val23,T val24)` {#namespacecimg__library__suffixed_1_1cimg_1aa147071742c37d4ed5698c612b2ff2f6}

#### `public template<>`  <br/>`inline T `[`median`](#namespacecimg__library__suffixed_1_1cimg_1ab28b23392cce9895840d93df30fb2db6)`(T val0,T val1,T val2,T val3,T val4,T val5,T val6,T val7,T val8,T val9,T val10,T val11,T val12,T val13,T val14,T val15,T val16,T val17,T val18,T val19,T val20,T val21,T val22,T val23,T val24,T val25,T val26,T val27,T val28,T val29,T val30,T val31,T val32,T val33,T val34,T val35,T val36,T val37,T val38,T val39,T val40,T val41,T val42,T val43,T val44,T val45,T val46,T val47,T val48)` {#namespacecimg__library__suffixed_1_1cimg_1ab28b23392cce9895840d93df30fb2db6}

#### `public template<>`  <br/>`inline T `[`hypot`](#namespacecimg__library__suffixed_1_1cimg_1af556f826a8b7acb2fbbaa5259e6d95e8)`(const T x,const T y)` {#namespacecimg__library__suffixed_1_1cimg_1af556f826a8b7acb2fbbaa5259e6d95e8}

Return sqrt(x^2 + y^2).

#### `public template<>`  <br/>`inline T `[`hypot`](#namespacecimg__library__suffixed_1_1cimg_1abc2af0eccc1059711364e339d73c36cd)`(const T x,const T y,const T z)` {#namespacecimg__library__suffixed_1_1cimg_1abc2af0eccc1059711364e339d73c36cd}

#### `public template<>`  <br/>`inline T `[`_hypot`](#namespacecimg__library__suffixed_1_1cimg_1a9e49b17ee53d34a8df49b655eb915572)`(const T x,const T y)` {#namespacecimg__library__suffixed_1_1cimg_1a9e49b17ee53d34a8df49b655eb915572}

#### `public inline double `[`factorial`](#namespacecimg__library__suffixed_1_1cimg_1a5c4845e4f0f1c87ec1cd97d7a8923cb6)`(const int n)` {#namespacecimg__library__suffixed_1_1cimg_1a5c4845e4f0f1c87ec1cd97d7a8923cb6}

Return the factorial of n.

#### `public inline double `[`permutations`](#namespacecimg__library__suffixed_1_1cimg_1a4e6348dd82ed46fecc9f46981dc5bc0a)`(const int k,const int n,const bool with_order)` {#namespacecimg__library__suffixed_1_1cimg_1a4e6348dd82ed46fecc9f46981dc5bc0a}

Return the number of permutations of k objects in a set of n objects.

#### `public inline double `[`_fibonacci`](#namespacecimg__library__suffixed_1_1cimg_1af54e8ac35c9b3c07062005881b2c4e08)`(int exp)` {#namespacecimg__library__suffixed_1_1cimg_1af54e8ac35c9b3c07062005881b2c4e08}

#### `public inline double `[`fibonacci`](#namespacecimg__library__suffixed_1_1cimg_1aa9c0e571bc9644b4d838630f9a79534f)`(const int n)` {#namespacecimg__library__suffixed_1_1cimg_1aa9c0e571bc9644b4d838630f9a79534f}

Calculate fibonacci number.

#### `public inline long `[`gcd`](#namespacecimg__library__suffixed_1_1cimg_1accbccc3f867ba4a2f5a3713761e7b1b2)`(long a,long b)` {#namespacecimg__library__suffixed_1_1cimg_1accbccc3f867ba4a2f5a3713761e7b1b2}

Calculate greatest common divisor.

#### `public inline char `[`lowercase`](#namespacecimg__library__suffixed_1_1cimg_1ac9cf8d2a803d13d85e7fcc48fee55587)`(const char x)` {#namespacecimg__library__suffixed_1_1cimg_1ac9cf8d2a803d13d85e7fcc48fee55587}

Convert character to lower case.

#### `public inline double `[`lowercase`](#namespacecimg__library__suffixed_1_1cimg_1a8154b2b3cf547bfa32e33547efada626)`(const double x)` {#namespacecimg__library__suffixed_1_1cimg_1a8154b2b3cf547bfa32e33547efada626}

#### `public inline void `[`lowercase`](#namespacecimg__library__suffixed_1_1cimg_1a633cb3df73dfa78f43ffa2679bd1ebb8)`(char *const str)` {#namespacecimg__library__suffixed_1_1cimg_1a633cb3df73dfa78f43ffa2679bd1ebb8}

Convert C-string to lower case.

#### `public inline char `[`uppercase`](#namespacecimg__library__suffixed_1_1cimg_1afbbd48435496962b08134b7b0101a07f)`(const char x)` {#namespacecimg__library__suffixed_1_1cimg_1afbbd48435496962b08134b7b0101a07f}

Convert character to upper case.

#### `public inline double `[`uppercase`](#namespacecimg__library__suffixed_1_1cimg_1a61266ea59c6fb0b76bba21326718ab41)`(const double x)` {#namespacecimg__library__suffixed_1_1cimg_1a61266ea59c6fb0b76bba21326718ab41}

#### `public inline void `[`uppercase`](#namespacecimg__library__suffixed_1_1cimg_1ac13217912b5cdf549f5744910521881a)`(char *const str)` {#namespacecimg__library__suffixed_1_1cimg_1ac13217912b5cdf549f5744910521881a}

Convert C-string to upper case.

#### `public inline bool `[`is_blank`](#namespacecimg__library__suffixed_1_1cimg_1a5dc2552c04442ed9c8643598bf1f4208)`(const char c)` {#namespacecimg__library__suffixed_1_1cimg_1a5dc2552c04442ed9c8643598bf1f4208}

Return `true` if input character is blank (space, tab, or non-printable character).

#### `public inline double `[`atof`](#namespacecimg__library__suffixed_1_1cimg_1a00aba235049bc02e53453cbb829469ce)`(const char *const str)` {#namespacecimg__library__suffixed_1_1cimg_1a00aba235049bc02e53453cbb829469ce}

Read value in a C-string.

#### Parameters
* `str` C-string containing the float value to read. 

#### Returns
Read value. 

Same as `std::atof()` extended to manage the retrieval of fractions from C-strings, as in *"1/2"*.

#### `public inline int `[`strncasecmp`](#namespacecimg__library__suffixed_1_1cimg_1a1304046a29511fe0a015173e46607229)`(const char *const str1,const char *const str2,const int l)` {#namespacecimg__library__suffixed_1_1cimg_1a1304046a29511fe0a015173e46607229}

Compare the first `l` characters of two C-strings, ignoring the case.

#### Parameters
* `str1` C-string. 

* `str2` C-string. 

* `l` Number of characters to compare. 

#### Returns
`0` if the two strings are equal, something else otherwise. 

This function has to be defined since it is not provided by all C++-compilers (not ANSI).

#### `public inline int `[`strcasecmp`](#namespacecimg__library__suffixed_1_1cimg_1a1c34609cc6fef6f5fe5ffb2f69ad7989)`(const char *const str1,const char *const str2)` {#namespacecimg__library__suffixed_1_1cimg_1a1c34609cc6fef6f5fe5ffb2f69ad7989}

Compare two C-strings, ignoring the case.

#### Parameters
* `str1` C-string. 

* `str2` C-string. 

#### Returns
`0` if the two strings are equal, something else otherwise. 

This function has to be defined since it is not provided by all C++-compilers (not ANSI).

#### `public inline char * `[`strellipsize`](#namespacecimg__library__suffixed_1_1cimg_1a69a3a1bbdf0f62474211ea5a398f9e72)`(char *const str,const unsigned int l,const bool is_ending)` {#namespacecimg__library__suffixed_1_1cimg_1a69a3a1bbdf0f62474211ea5a398f9e72}

Ellipsize a string.

#### Parameters
* `str` C-string. 

* `l` Max number of characters. 

* `is_ending` Tell if the dots are placed at the end or at the center of the ellipsized string.

#### `public inline char * `[`strellipsize`](#namespacecimg__library__suffixed_1_1cimg_1a79b0ac227dd09ae4cdb84658d2fd919b)`(const char *const str,char *const res,const unsigned int l,const bool is_ending)` {#namespacecimg__library__suffixed_1_1cimg_1a79b0ac227dd09ae4cdb84658d2fd919b}

Ellipsize a string.

#### Parameters
* `str` C-string. 

* `res` output C-string. 

* `l` Max number of characters. 

* `is_ending` Tell if the dots are placed at the end or at the center of the ellipsized string.

#### `public inline bool `[`strpare`](#namespacecimg__library__suffixed_1_1cimg_1a85cb703b948df7a021fd41ca3bad6696)`(char *const str,const char delimiter,const bool is_symmetric,const bool is_iterative)` {#namespacecimg__library__suffixed_1_1cimg_1a85cb703b948df7a021fd41ca3bad6696}

Remove delimiters on the start and/or end of a C-string.

#### Parameters
* `str` C-string to work with (modified at output). 

* `delimiter` Delimiter character code to remove. 

* `is_symmetric` Tells if the removal is done only if delimiters are symmetric (both at the beginning and the end of `s`). 

* `is_iterative` Tells if the removal is done if several iterations are possible. 

#### Returns
`true` if delimiters have been removed, `false` otherwise.

#### `public inline bool `[`strpare`](#namespacecimg__library__suffixed_1_1cimg_1ac9e23320a870b0ebce24c7a6059c7467)`(char *const str,const bool is_symmetric,const bool is_iterative)` {#namespacecimg__library__suffixed_1_1cimg_1ac9e23320a870b0ebce24c7a6059c7467}

Remove white spaces on the start and/or end of a C-string.

#### `public inline void `[`strwindows_reserved`](#namespacecimg__library__suffixed_1_1cimg_1a3dff5896c142fb4f9dbd2d49facd33c0)`(char *const str,const char c)` {#namespacecimg__library__suffixed_1_1cimg_1a3dff5896c142fb4f9dbd2d49facd33c0}

Replace reserved characters (for Windows filename) by another character.

#### Parameters
* `str` C-string to work with (modified at output). 

* `c` Replacement character.

#### `public inline void `[`strunescape`](#namespacecimg__library__suffixed_1_1cimg_1a1ffad008d2b45ffa0ff4d0f32b6c98ec)`(char *const str)` {#namespacecimg__library__suffixed_1_1cimg_1a1ffad008d2b45ffa0ff4d0f32b6c98ec}

Replace escape sequences in C-strings by character values.

#### Parameters
* `str` C-string to work with (modified at output).

#### `public inline const char * `[`strbuffersize`](#namespacecimg__library__suffixed_1_1cimg_1a73a84376fb4f9577c5786ad58289efad)`(const cimg_ulong size)` {#namespacecimg__library__suffixed_1_1cimg_1a73a84376fb4f9577c5786ad58289efad}

#### `public inline const char * `[`stros`](#namespacecimg__library__suffixed_1_1cimg_1ac2fe91fca3a53a6a86d6e4ba808c2061)`()` {#namespacecimg__library__suffixed_1_1cimg_1ac2fe91fca3a53a6a86d6e4ba808c2061}

#### `public inline const char * `[`basename`](#namespacecimg__library__suffixed_1_1cimg_1a40fb5fe2a0d260120909c617dfd3b07b)`(const char *const s,const char separator)` {#namespacecimg__library__suffixed_1_1cimg_1a40fb5fe2a0d260120909c617dfd3b07b}

Return the basename of a filename.

#### `public inline const char * `[`filenamerand`](#namespacecimg__library__suffixed_1_1cimg_1ae92216bbc140ed7afef601f72ba2bd81)`()` {#namespacecimg__library__suffixed_1_1cimg_1ae92216bbc140ed7afef601f72ba2bd81}

#### `public inline void `[`winformat_string`](#namespacecimg__library__suffixed_1_1cimg_1a1b401761f9f3c1d01de8ec6ef6bec731)`(char *const str)` {#namespacecimg__library__suffixed_1_1cimg_1a1b401761f9f3c1d01de8ec6ef6bec731}

#### `public inline std::FILE * `[`std_fopen`](#namespacecimg__library__suffixed_1_1cimg_1aa21dee2dbac63e1cfcd7613c159edff3)`(const char *const path,const char *const mode)` {#namespacecimg__library__suffixed_1_1cimg_1aa21dee2dbac63e1cfcd7613c159edff3}

#### `public inline std::FILE * `[`fopen`](#namespacecimg__library__suffixed_1_1cimg_1a9aafdb8732ff87625052ce2723f8a516)`(const char *const path,const char *const mode)` {#namespacecimg__library__suffixed_1_1cimg_1a9aafdb8732ff87625052ce2723f8a516}

Open a file.

#### Parameters
* `path` Path of the filename to open. 

* `mode` C-string describing the opening mode. 

#### Returns
Opened file. 

Same as `std::fopen()` but throw a `[CImgIOException](#structcimg__library__suffixed_1_1CImgIOException)` when the specified file cannot be opened, instead of returning `0`.

#### `public inline int `[`fclose`](#namespacecimg__library__suffixed_1_1cimg_1ac436b94e6ffef5fd420bb3d7c05fd416)`(std::FILE * file)` {#namespacecimg__library__suffixed_1_1cimg_1ac436b94e6ffef5fd420bb3d7c05fd416}

Close a file.

#### Parameters
* `file` File to close. 

#### Returns
`0` if file has been closed properly, something else otherwise. 

Same as `std::fclose()` but display a warning message if the file has not been closed properly.

#### `public inline int `[`fseek`](#namespacecimg__library__suffixed_1_1cimg_1a03dbe74029b194eca4b86c10e9fbd1fc)`(FILE * stream,cimg_long offset,int origin)` {#namespacecimg__library__suffixed_1_1cimg_1a03dbe74029b194eca4b86c10e9fbd1fc}

Version of '[fseek()](#namespacecimg__library__suffixed_1_1cimg_1a03dbe74029b194eca4b86c10e9fbd1fc)' that supports >=64bits offsets everywhere (for Windows).

#### `public inline cimg_long `[`ftell`](#namespacecimg__library__suffixed_1_1cimg_1a6fe7b32c5cfeef7ec973b4cbb538683a)`(FILE * stream)` {#namespacecimg__library__suffixed_1_1cimg_1a6fe7b32c5cfeef7ec973b4cbb538683a}

Version of '[ftell()](#namespacecimg__library__suffixed_1_1cimg_1a6fe7b32c5cfeef7ec973b4cbb538683a)' that supports >=64bits offsets everywhere (for Windows).

#### `public inline bool `[`is_directory`](#namespacecimg__library__suffixed_1_1cimg_1aca0e45a04eb1607f2e25101aae4b8572)`(const char *const path)` {#namespacecimg__library__suffixed_1_1cimg_1aca0e45a04eb1607f2e25101aae4b8572}

Check if a path is a directory.

#### Parameters
* `path` Specified path to test.

#### `public inline bool `[`is_file`](#namespacecimg__library__suffixed_1_1cimg_1ad6c9ae2aaaf60bdecbd5c8f57ee5617e)`(const char *const path)` {#namespacecimg__library__suffixed_1_1cimg_1ad6c9ae2aaaf60bdecbd5c8f57ee5617e}

Check if a path is a file.

#### Parameters
* `path` Specified path to test.

#### `public inline cimg_int64 `[`fsize`](#namespacecimg__library__suffixed_1_1cimg_1a63af61d735eb705dfeae46df8bf03184)`(const char *const filename)` {#namespacecimg__library__suffixed_1_1cimg_1a63af61d735eb705dfeae46df8bf03184}

Get file size.

#### Parameters
* `filename` Specified filename to get size from. 

#### Returns
File size or '-1' if file does not exist.

#### `public template<>`  <br/>`inline int `[`fdate`](#namespacecimg__library__suffixed_1_1cimg_1a0654bf4ceae1444ae9fa1113cbb064ee)`(const char *const path,T * attr,const unsigned int nb_attr)` {#namespacecimg__library__suffixed_1_1cimg_1a0654bf4ceae1444ae9fa1113cbb064ee}

Get last write time of a given file or directory (multiple-attributes version).

#### Parameters
* `path` Specified path to get attributes from. 

* `attr` Type of requested time attributes. Can be { 0=year | 1=month | 2=day | 3=day of week | 4=hour | 5=minute | 6=second } Replaced by read attributes after return (or -1 if an error occurred). 

* `nb_attr` Number of attributes to read/write. 

#### Returns
Latest read attribute.

#### `public inline int `[`fdate`](#namespacecimg__library__suffixed_1_1cimg_1a1db87aed0dbd0fd7a0e709894e9f645d)`(const char *const path,unsigned int attr)` {#namespacecimg__library__suffixed_1_1cimg_1a1db87aed0dbd0fd7a0e709894e9f645d}

Get last write time of a given file or directory (single-attribute version).

#### Parameters
* `path` Specified path to get attributes from. 

* `attr` Type of requested time attributes. Can be { 0=year | 1=month | 2=day | 3=day of week | 4=hour | 5=minute | 6=second } 

#### Returns
Specified attribute or -1 if an error occurred.

#### `public template<>`  <br/>`inline int `[`date`](#namespacecimg__library__suffixed_1_1cimg_1a6b6e28a991c9e426d8cb1c6d1e02849e)`(T * attr,const unsigned int nb_attr)` {#namespacecimg__library__suffixed_1_1cimg_1a6b6e28a991c9e426d8cb1c6d1e02849e}

Get current local time (multiple-attributes version).

#### Parameters
* `attr` Type of requested time attributes. Can be { 0=year | 1=month | 2=day | 3=day of week | 4=hour | 5=minute | 6=second | 7=millisecond } Replaced by read attributes after return (or -1 if an error occurred). 

* `nb_attr` Number of attributes to read/write. 

#### Returns
Latest read attribute.

#### `public inline int `[`date`](#namespacecimg__library__suffixed_1_1cimg_1aac739bf544269324a04504ebe92b93e9)`(unsigned int attr)` {#namespacecimg__library__suffixed_1_1cimg_1aac739bf544269324a04504ebe92b93e9}

Get current local time (single-attribute version).

#### Parameters
* `attr` Type of requested time attribute. Can be { 0=year | 1=month | 2=day | 3=day of week | 4=hour | 5=minute | 6=second | 7=millisecond } 

#### Returns
Specified attribute or -1 if an error occurred.

#### `public inline const char * `[`temporary_path`](#namespacecimg__library__suffixed_1_1cimg_1ae9af8e17db04e875db3b45cbe58892d6)`(const char *const user_path,const bool reinit_path)` {#namespacecimg__library__suffixed_1_1cimg_1ae9af8e17db04e875db3b45cbe58892d6}

Get the file or directory attributes with support for UTF-8 paths (Windows only).

Get/set path to store temporary files. 
#### Parameters
* `user_path` Specified path, or `0` to get the path currently used. 

* `reinit_path` Force path to be recalculated (may take some time). 

#### Returns
Path where temporary files can be saved.

#### `public inline const char * `[`imagemagick_path`](#namespacecimg__library__suffixed_1_1cimg_1a96cabeea0a54a10aeee97ead7b672f0f)`(const char *const user_path,const bool reinit_path)` {#namespacecimg__library__suffixed_1_1cimg_1a96cabeea0a54a10aeee97ead7b672f0f}

Get/set path to the *Program Files/* directory (Windows only).

#### Parameters
* `user_path` Specified path, or `0` to get the path currently used. 

* `reinit_path` Force path to be recalculated (may take some time). 

#### Returns
Path containing the program files. Get/set path to the ImageMagick's `convert` binary. 

#### Parameters
* `user_path` Specified path, or `0` to get the path currently used. 

* `reinit_path` Force path to be recalculated (may take some time). 

#### Returns
Path containing the `convert` binary.

#### `public inline const char * `[`graphicsmagick_path`](#namespacecimg__library__suffixed_1_1cimg_1ab4063d8fb2c2564596f33f4a75436f76)`(const char *const user_path,const bool reinit_path)` {#namespacecimg__library__suffixed_1_1cimg_1ab4063d8fb2c2564596f33f4a75436f76}

Get/set path to the GraphicsMagick's `gm` binary.

#### Parameters
* `user_path` Specified path, or `0` to get the path currently used. 

* `reinit_path` Force path to be recalculated (may take some time). 

#### Returns
Path containing the `gm` binary.

#### `public inline const char * `[`medcon_path`](#namespacecimg__library__suffixed_1_1cimg_1a65c2f6f9671ac4f3eae2b5624313926e)`(const char *const user_path,const bool reinit_path)` {#namespacecimg__library__suffixed_1_1cimg_1a65c2f6f9671ac4f3eae2b5624313926e}

Get/set path to the XMedcon's `medcon` binary.

#### Parameters
* `user_path` Specified path, or `0` to get the path currently used. 

* `reinit_path` Force path to be recalculated (may take some time). 

#### Returns
Path containing the `medcon` binary.

#### `public inline const char * `[`ffmpeg_path`](#namespacecimg__library__suffixed_1_1cimg_1a5b8fba26176c5506b1eb27e70ca44889)`(const char *const user_path,const bool reinit_path)` {#namespacecimg__library__suffixed_1_1cimg_1a5b8fba26176c5506b1eb27e70ca44889}

Get/set path to the FFMPEG's `ffmpeg` binary.

#### Parameters
* `user_path` Specified path, or `0` to get the path currently used. 

* `reinit_path` Force path to be recalculated (may take some time). 

#### Returns
Path containing the `ffmpeg` binary.

#### `public inline const char * `[`gzip_path`](#namespacecimg__library__suffixed_1_1cimg_1aac00308d827ccbd69bd26c9ba6e1356b)`(const char *const user_path,const bool reinit_path)` {#namespacecimg__library__suffixed_1_1cimg_1aac00308d827ccbd69bd26c9ba6e1356b}

Get/set path to the `gzip` binary.

#### Parameters
* `user_path` Specified path, or `0` to get the path currently used. 

* `reinit_path` Force path to be recalculated (may take some time). 

#### Returns
Path containing the `gzip` binary.

#### `public inline const char * `[`gunzip_path`](#namespacecimg__library__suffixed_1_1cimg_1a7b4390d7bec2ffbf27d108f1c3a699e0)`(const char *const user_path,const bool reinit_path)` {#namespacecimg__library__suffixed_1_1cimg_1a7b4390d7bec2ffbf27d108f1c3a699e0}

Get/set path to the `gunzip` binary.

#### Parameters
* `user_path` Specified path, or `0` to get the path currently used. 

* `reinit_path` Force path to be recalculated (may take some time). 

#### Returns
Path containing the `gunzip` binary.

#### `public inline const char * `[`dcraw_path`](#namespacecimg__library__suffixed_1_1cimg_1ad2459563e2ed326f303b9ac4e91744b0)`(const char *const user_path,const bool reinit_path)` {#namespacecimg__library__suffixed_1_1cimg_1ad2459563e2ed326f303b9ac4e91744b0}

Get/set path to the `dcraw` binary.

#### Parameters
* `user_path` Specified path, or `0` to get the path currently used. 

* `reinit_path` Force path to be recalculated (may take some time). 

#### Returns
Path containing the `dcraw` binary.

#### `public inline const char * `[`wget_path`](#namespacecimg__library__suffixed_1_1cimg_1a36ccf2e6a6542f4e93eac819cf5d91ba)`(const char *const user_path,const bool reinit_path)` {#namespacecimg__library__suffixed_1_1cimg_1a36ccf2e6a6542f4e93eac819cf5d91ba}

Get/set path to the `wget` binary.

#### Parameters
* `user_path` Specified path, or `0` to get the path currently used. 

* `reinit_path` Force path to be recalculated (may take some time). 

#### Returns
Path containing the `wget` binary.

#### `public inline const char * `[`curl_path`](#namespacecimg__library__suffixed_1_1cimg_1aebd4f990c3e148573c96c04dbfdcc5c6)`(const char *const user_path,const bool reinit_path)` {#namespacecimg__library__suffixed_1_1cimg_1aebd4f990c3e148573c96c04dbfdcc5c6}

Get/set path to the `curl` binary.

#### Parameters
* `user_path` Specified path, or `0` to get the path currently used. 

* `reinit_path` Force path to be recalculated (may take some time). 

#### Returns
Path containing the `curl` binary.

#### `public inline const char * `[`split_filename`](#namespacecimg__library__suffixed_1_1cimg_1a61e1cd854cf93fdf3f6d06525e1590c5)`(const char *const filename,char *const body)` {#namespacecimg__library__suffixed_1_1cimg_1a61e1cd854cf93fdf3f6d06525e1590c5}

Split filename into two C-strings `body` and `extension`.

filename and body must not overlap!

#### `public inline char * `[`number_filename`](#namespacecimg__library__suffixed_1_1cimg_1ae9bdf968dd4f20fdc7542e3b3089c495)`(const char *const filename,const int number,const unsigned int digits,char *const str)` {#namespacecimg__library__suffixed_1_1cimg_1ae9bdf968dd4f20fdc7542e3b3089c495}

Generate a numbered version of a filename.

#### `public template<>`  <br/>`inline size_t `[`fread`](#namespacecimg__library__suffixed_1_1cimg_1a6b210044fcdb52b1d649ab19006de4ad)`(T *const ptr,const size_t nmemb,std::FILE * stream)` {#namespacecimg__library__suffixed_1_1cimg_1a6b210044fcdb52b1d649ab19006de4ad}

Read data from file.

#### Parameters
* `ptr` Pointer to memory buffer that will contain the binary data read from file. 

* `nmemb` Number of elements to read. 

* `stream` File to read data from. 

#### Returns
Number of read elements. 

Same as `std::fread()` but may display warning message if all elements could not be read.

#### `public template<>`  <br/>`inline size_t `[`fwrite`](#namespacecimg__library__suffixed_1_1cimg_1ad44a7e96cd1e9cdef83f4ffe235dd1fb)`(const T * ptr,const size_t nmemb,std::FILE * stream)` {#namespacecimg__library__suffixed_1_1cimg_1ad44a7e96cd1e9cdef83f4ffe235dd1fb}

Write data to file.

#### Parameters
* `ptr` Pointer to memory buffer containing the binary data to write on file. 

* `nmemb` Number of elements to write. 

* `stream` File to write data on. 

#### Returns
Number of written elements. 

Similar to `std::fwrite` but may display warning messages if all elements could not be written.

#### `public inline void `[`fempty`](#namespacecimg__library__suffixed_1_1cimg_1a0f3577978081461118330fc3ecd4b9db)`(std::FILE *const file,const char *const filename)` {#namespacecimg__library__suffixed_1_1cimg_1a0f3577978081461118330fc3ecd4b9db}

Create an empty file.

#### Parameters
* `file` Input file (can be `0` if `filename` is set). 

* `filename` Filename, as a C-string (can be `0` if `file` is set).

#### `public inline const char * `[`ftype`](#namespacecimg__library__suffixed_1_1cimg_1a56c2dbfe99d9f6e6bc1be9d03b0ddaaa)`(std::FILE *const file,const char *const filename)` {#namespacecimg__library__suffixed_1_1cimg_1a56c2dbfe99d9f6e6bc1be9d03b0ddaaa}

Try to guess format from an image file.

#### Parameters
* `file` Input file (can be `0` if `filename` is set). 

* `filename` Filename, as a C-string (can be `0` if `file` is set). 

#### Returns
C-string containing the guessed file format, or `0` if nothing has been guessed.

#### `public inline bool & `[`network_mode`](#namespacecimg__library__suffixed_1_1cimg_1a470c76a43e2ae6f77c48acf1071fcc67)`(const bool value,const bool is_set)` {#namespacecimg__library__suffixed_1_1cimg_1a470c76a43e2ae6f77c48acf1071fcc67}

#### `public inline bool & `[`network_mode`](#namespacecimg__library__suffixed_1_1cimg_1a02013cf524a1901b3001ee1038dcea49)`()` {#namespacecimg__library__suffixed_1_1cimg_1a02013cf524a1901b3001ee1038dcea49}

#### `public inline char * `[`load_network`](#namespacecimg__library__suffixed_1_1cimg_1a90c05fe6fc049cba75f3a12807e97158)`(const char *const url,char *const filename_local,const unsigned int timeout,const bool try_fallback,const char *const referer)` {#namespacecimg__library__suffixed_1_1cimg_1a90c05fe6fc049cba75f3a12807e97158}

Load file from network as a local temporary file.

#### Parameters
* `url` URL of the filename, as a C-string. 

* `filename_local` C-string containing the path to a local copy of `filename`. 

* `timeout` Maximum time (in seconds) authorized for downloading the file from the URL. 

* `try_fallback` When using libcurl, tells using system calls as fallbacks in case of libcurl failure. 

* `referer` Referer used, as a C-string. 

#### Returns
Value of `filename_local`. 

Use the `libcurl` library, or the external binaries `wget` or `curl` to perform the download.

#### `public inline const char * `[`option`](#namespacecimg__library__suffixed_1_1cimg_1a2af5d4755bf8a0e4e9e8cf833eb46f31)`(const char *const name,const int argc,const char *const *const argv,const char *const _default,const char *const usage,const bool reset_static)` {#namespacecimg__library__suffixed_1_1cimg_1a2af5d4755bf8a0e4e9e8cf833eb46f31}

Return options specified on the command line.

#### `public inline const char * `[`option`](#namespacecimg__library__suffixed_1_1cimg_1afa0edc26d6968a0b6fde84452e51f01f)`(const char *const name,const int argc,const char *const *const argv,const char *const _default,const char *const usage)` {#namespacecimg__library__suffixed_1_1cimg_1afa0edc26d6968a0b6fde84452e51f01f}

#### `public inline bool `[`option`](#namespacecimg__library__suffixed_1_1cimg_1ae0751f1e30f631c99f04d351859ee78f)`(const char *const name,const int argc,const char *const *const argv,const bool _default,const char *const usage)` {#namespacecimg__library__suffixed_1_1cimg_1ae0751f1e30f631c99f04d351859ee78f}

#### `public inline int `[`option`](#namespacecimg__library__suffixed_1_1cimg_1aaff0def8ccf096f02c1fb2267af9bf69)`(const char *const name,const int argc,const char *const *const argv,const int _default,const char *const usage)` {#namespacecimg__library__suffixed_1_1cimg_1aaff0def8ccf096f02c1fb2267af9bf69}

#### `public inline char `[`option`](#namespacecimg__library__suffixed_1_1cimg_1ac2ddab9ad61673b342d32cdd724ac376)`(const char *const name,const int argc,const char *const *const argv,const char _default,const char *const usage)` {#namespacecimg__library__suffixed_1_1cimg_1ac2ddab9ad61673b342d32cdd724ac376}

#### `public inline float `[`option`](#namespacecimg__library__suffixed_1_1cimg_1a2d98984b306115047ef266b03164cf23)`(const char *const name,const int argc,const char *const *const argv,const float _default,const char *const usage)` {#namespacecimg__library__suffixed_1_1cimg_1a2d98984b306115047ef266b03164cf23}

#### `public inline double `[`option`](#namespacecimg__library__suffixed_1_1cimg_1a5325ef9b0a96182b545bbdcf31d02798)`(const char *const name,const int argc,const char *const *const argv,const double _default,const char *const usage)` {#namespacecimg__library__suffixed_1_1cimg_1a5325ef9b0a96182b545bbdcf31d02798}

#### `public inline int `[`_sort_files`](#namespacecimg__library__suffixed_1_1cimg_1add25d3bf42363c07ad95d4a9a689f729)`(const void * a,const void * b)` {#namespacecimg__library__suffixed_1_1cimg_1add25d3bf42363c07ad95d4a9a689f729}

#### `public inline `[`CImgList`](#structcimg__library__suffixed_1_1CImgList)`< char > `[`files`](#namespacecimg__library__suffixed_1_1cimg_1a9f8980f1308177adebab5f8f52a79835)`(const char *const path,const bool is_pattern,const unsigned int mode,const bool include_path)` {#namespacecimg__library__suffixed_1_1cimg_1a9f8980f1308177adebab5f8f52a79835}

Return list of files/directories in specified directory.

#### Parameters
* `path` Path to the directory. Set to 0 for current directory. 

* `is_pattern` Tell if specified path has a matching pattern in it. 

* `mode` Output type, can be primary { 0=files only | 1=folders only | 2=files + folders }. 

* `include_path` Tell if `path` must be included in resulting filenames. 

#### Returns
A list of filenames.

#### `public template<>`  <br/>`inline int `[`dialog`](#namespacecimg__library__suffixed_1_1cimg_1a11aed0e6b30d75bf50946ee78d1aed94)`(const char *const title,const char *const msg,const char *const button1_label,const char *const button2_label,const char *const button3_label,const char *const button4_label,const char *const button5_label,const char *const button6_label,const `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< t > & logo,const bool is_centered)` {#namespacecimg__library__suffixed_1_1cimg_1a11aed0e6b30d75bf50946ee78d1aed94}

Display a simple dialog box, and wait for the user's response.

#### Parameters
* `title` Title of the dialog window. 

* `msg` Main message displayed inside the dialog window. 

* `button1_label` Label of the 1st button. 

* `button2_label` Label of the 2nd button (`0` to hide button). 

* `button3_label` Label of the 3rd button (`0` to hide button). 

* `button4_label` Label of the 4th button (`0` to hide button). 

* `button5_label` Label of the 5th button (`0` to hide button). 

* `button6_label` Label of the 6th button (`0` to hide button). 

* `logo` Image logo displayed at the left of the main message. 

* `is_centered` Tells if the dialog window must be centered on the screen. 

#### Returns
Index of clicked button (from `0` to `5`), or `-1` if the dialog window has been closed by the user. 

* Up to 6 buttons can be defined in the dialog window.

* The function returns when a user clicked one of the button or closed the dialog window.

* If a button text is set to 0, the corresponding button (and the following) will not appear in the dialog box. At least one button must be specified.

#### `public template<>`  <br/>`inline `[`CImg](#structcimg__library__suffixed_1_1CImg)< typename [cimg::superset](#structcimg__library__suffixed_1_1cimg_1_1superset)< double, t >::[type`](#structcimg__library__suffixed_1_1cimg_1_1type)` > `[`eval`](#namespacecimg__library__suffixed_1_1cimg_1ad0fbf2581340a8533f5c3e3d86e2ce60)`(const char *const expression,const `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< t > & xyzc)` {#namespacecimg__library__suffixed_1_1cimg_1ad0fbf2581340a8533f5c3e3d86e2ce60}

# struct `cimg_library_suffixed::cimg::last` {#structcimg__library__suffixed_1_1cimg_1_1last}

<h2> Summary </h2>

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1last_1a5e61c40425c0b12941add4d01a776591) | 

<h2> Members </h2>

#### `typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1last_1a5e61c40425c0b12941add4d01a776591) {#structcimg__library__suffixed_1_1cimg_1_1last_1a5e61c40425c0b12941add4d01a776591}

# struct `cimg_library_suffixed::cimg::Mutex_static` {#structcimg__library__suffixed_1_1cimg_1_1Mutex__static}

<h2> Summary </h2>

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`public inline  `[`Mutex_static`](#structcimg__library__suffixed_1_1cimg_1_1Mutex__static_1ab1a55f1de6c12b971b839e896f215b6a)`()` | 
`public inline void `[`lock`](#structcimg__library__suffixed_1_1cimg_1_1Mutex__static_1a33d2cfe5b12defbe6e96086eef12c0c2)`(const unsigned int)` | 
`public inline void `[`unlock`](#structcimg__library__suffixed_1_1cimg_1_1Mutex__static_1a76478cf71bb40380f64f92015a4ffc4f)`(const unsigned int)` | 
`public inline int `[`trylock`](#structcimg__library__suffixed_1_1cimg_1_1Mutex__static_1a0eb27b2598953ac49fff472ccbb7b4c4)`(const unsigned int)` | 

<h2> Members </h2>

#### `public inline  `[`Mutex_static`](#structcimg__library__suffixed_1_1cimg_1_1Mutex__static_1ab1a55f1de6c12b971b839e896f215b6a)`()` {#structcimg__library__suffixed_1_1cimg_1_1Mutex__static_1ab1a55f1de6c12b971b839e896f215b6a}

#### `public inline void `[`lock`](#structcimg__library__suffixed_1_1cimg_1_1Mutex__static_1a33d2cfe5b12defbe6e96086eef12c0c2)`(const unsigned int)` {#structcimg__library__suffixed_1_1cimg_1_1Mutex__static_1a33d2cfe5b12defbe6e96086eef12c0c2}

#### `public inline void `[`unlock`](#structcimg__library__suffixed_1_1cimg_1_1Mutex__static_1a76478cf71bb40380f64f92015a4ffc4f)`(const unsigned int)` {#structcimg__library__suffixed_1_1cimg_1_1Mutex__static_1a76478cf71bb40380f64f92015a4ffc4f}

#### `public inline int `[`trylock`](#structcimg__library__suffixed_1_1cimg_1_1Mutex__static_1a0eb27b2598953ac49fff472ccbb7b4c4)`(const unsigned int)` {#structcimg__library__suffixed_1_1cimg_1_1Mutex__static_1a0eb27b2598953ac49fff472ccbb7b4c4}

# struct `cimg_library_suffixed::cimg::superset` {#structcimg__library__suffixed_1_1cimg_1_1superset}

<h2> Summary </h2>

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_1a0de6d4ec641bbc88dafde61fd63c91f8) | 

<h2> Members </h2>

#### `typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_1a0de6d4ec641bbc88dafde61fd63c91f8) {#structcimg__library__suffixed_1_1cimg_1_1superset_1a0de6d4ec641bbc88dafde61fd63c91f8}

# struct `cimg_library_suffixed::cimg::superset2` {#structcimg__library__suffixed_1_1cimg_1_1superset2}

<h2> Summary </h2>

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset2_1a4f850744d5b934265ec7f77920404b89) | 

<h2> Members </h2>

#### `typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset2_1a4f850744d5b934265ec7f77920404b89) {#structcimg__library__suffixed_1_1cimg_1_1superset2_1a4f850744d5b934265ec7f77920404b89}

# struct `cimg_library_suffixed::cimg::superset3` {#structcimg__library__suffixed_1_1cimg_1_1superset3}

<h2> Summary </h2>

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset3_1aba013dc2009712d23706ccbfc3ba326c) | 

<h2> Members </h2>

#### `typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset3_1aba013dc2009712d23706ccbfc3ba326c) {#structcimg__library__suffixed_1_1cimg_1_1superset3_1aba013dc2009712d23706ccbfc3ba326c}

# struct `cimg_library_suffixed::cimg::superset< bool, char >` {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01bool_00_01char_01_4}

<h2> Summary </h2>

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01bool_00_01char_01_4_1acdae5243dfde2cfcae0537d0cea059cd) | 

<h2> Members </h2>

#### `typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01bool_00_01char_01_4_1acdae5243dfde2cfcae0537d0cea059cd) {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01bool_00_01char_01_4_1acdae5243dfde2cfcae0537d0cea059cd}

# struct `cimg_library_suffixed::cimg::superset< bool, cimg_int64 >` {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01bool_00_01cimg__int64_01_4}

<h2> Summary </h2>

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01bool_00_01cimg__int64_01_4_1a7cc8f0581ae2fd8d5fb4f9d1fa91dbe1) | 

<h2> Members </h2>

#### `typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01bool_00_01cimg__int64_01_4_1a7cc8f0581ae2fd8d5fb4f9d1fa91dbe1) {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01bool_00_01cimg__int64_01_4_1a7cc8f0581ae2fd8d5fb4f9d1fa91dbe1}

# struct `cimg_library_suffixed::cimg::superset< bool, cimg_uint64 >` {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01bool_00_01cimg__uint64_01_4}

<h2> Summary </h2>

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01bool_00_01cimg__uint64_01_4_1a2ab2d4c2236902e400451e305ffd9e21) | 

<h2> Members </h2>

#### `typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01bool_00_01cimg__uint64_01_4_1a2ab2d4c2236902e400451e305ffd9e21) {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01bool_00_01cimg__uint64_01_4_1a2ab2d4c2236902e400451e305ffd9e21}

# struct `cimg_library_suffixed::cimg::superset< bool, double >` {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01bool_00_01double_01_4}

<h2> Summary </h2>

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01bool_00_01double_01_4_1a421bed2237f8065dfc21034a205eb345) | 

<h2> Members </h2>

#### `typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01bool_00_01double_01_4_1a421bed2237f8065dfc21034a205eb345) {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01bool_00_01double_01_4_1a421bed2237f8065dfc21034a205eb345}

# struct `cimg_library_suffixed::cimg::superset< bool, float >` {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01bool_00_01float_01_4}

<h2> Summary </h2>

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01bool_00_01float_01_4_1aa08032fc0bd77f43b6a14c23c770b82f) | 

<h2> Members </h2>

#### `typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01bool_00_01float_01_4_1aa08032fc0bd77f43b6a14c23c770b82f) {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01bool_00_01float_01_4_1aa08032fc0bd77f43b6a14c23c770b82f}

# struct `cimg_library_suffixed::cimg::superset< bool, int >` {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01bool_00_01int_01_4}

<h2> Summary </h2>

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01bool_00_01int_01_4_1a58e3cd58cfe47ea7ed381d7aeebab81b) | 

<h2> Members </h2>

#### `typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01bool_00_01int_01_4_1a58e3cd58cfe47ea7ed381d7aeebab81b) {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01bool_00_01int_01_4_1a58e3cd58cfe47ea7ed381d7aeebab81b}

# struct `cimg_library_suffixed::cimg::superset< bool, short >` {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01bool_00_01short_01_4}

<h2> Summary </h2>

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01bool_00_01short_01_4_1ad10e5178f0b07ea71386f97bb41043bf) | 

<h2> Members </h2>

#### `typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01bool_00_01short_01_4_1ad10e5178f0b07ea71386f97bb41043bf) {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01bool_00_01short_01_4_1ad10e5178f0b07ea71386f97bb41043bf}

# struct `cimg_library_suffixed::cimg::superset< bool, signed char >` {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01bool_00_01signed_01char_01_4}

<h2> Summary </h2>

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01bool_00_01signed_01char_01_4_1a1092e516767772f3376345fddaa5eed4) | 

<h2> Members </h2>

#### `typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01bool_00_01signed_01char_01_4_1a1092e516767772f3376345fddaa5eed4) {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01bool_00_01signed_01char_01_4_1a1092e516767772f3376345fddaa5eed4}

# struct `cimg_library_suffixed::cimg::superset< bool, unsigned char >` {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01bool_00_01unsigned_01char_01_4}

<h2> Summary </h2>

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01bool_00_01unsigned_01char_01_4_1a85bd7a20e1c2e1ad0d8b964f473d5494) | 

<h2> Members </h2>

#### `typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01bool_00_01unsigned_01char_01_4_1a85bd7a20e1c2e1ad0d8b964f473d5494) {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01bool_00_01unsigned_01char_01_4_1a85bd7a20e1c2e1ad0d8b964f473d5494}

# struct `cimg_library_suffixed::cimg::superset< bool, unsigned int >` {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01bool_00_01unsigned_01int_01_4}

<h2> Summary </h2>

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01bool_00_01unsigned_01int_01_4_1a1e9c2d39872148d655400d97fa9be87a) | 

<h2> Members </h2>

#### `typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01bool_00_01unsigned_01int_01_4_1a1e9c2d39872148d655400d97fa9be87a) {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01bool_00_01unsigned_01int_01_4_1a1e9c2d39872148d655400d97fa9be87a}

# struct `cimg_library_suffixed::cimg::superset< bool, unsigned short >` {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01bool_00_01unsigned_01short_01_4}

<h2> Summary </h2>

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01bool_00_01unsigned_01short_01_4_1afecefd8d0d371269d4836767bd56c25c) | 

<h2> Members </h2>

#### `typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01bool_00_01unsigned_01short_01_4_1afecefd8d0d371269d4836767bd56c25c) {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01bool_00_01unsigned_01short_01_4_1afecefd8d0d371269d4836767bd56c25c}

# struct `cimg_library_suffixed::cimg::superset< char, cimg_int64 >` {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01char_00_01cimg__int64_01_4}

<h2> Summary </h2>

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01char_00_01cimg__int64_01_4_1abb8cc94a168e4a48b9c1f7f0bdd6bbb3) | 

<h2> Members </h2>

#### `typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01char_00_01cimg__int64_01_4_1abb8cc94a168e4a48b9c1f7f0bdd6bbb3) {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01char_00_01cimg__int64_01_4_1abb8cc94a168e4a48b9c1f7f0bdd6bbb3}

# struct `cimg_library_suffixed::cimg::superset< char, cimg_uint64 >` {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01char_00_01cimg__uint64_01_4}

<h2> Summary </h2>

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01char_00_01cimg__uint64_01_4_1abccd536e281798c17710df88a7762274) | 

<h2> Members </h2>

#### `typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01char_00_01cimg__uint64_01_4_1abccd536e281798c17710df88a7762274) {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01char_00_01cimg__uint64_01_4_1abccd536e281798c17710df88a7762274}

# struct `cimg_library_suffixed::cimg::superset< char, double >` {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01char_00_01double_01_4}

<h2> Summary </h2>

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01char_00_01double_01_4_1a9d8f4d0c4c3dbf9f1afedae5b542929a) | 

<h2> Members </h2>

#### `typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01char_00_01double_01_4_1a9d8f4d0c4c3dbf9f1afedae5b542929a) {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01char_00_01double_01_4_1a9d8f4d0c4c3dbf9f1afedae5b542929a}

# struct `cimg_library_suffixed::cimg::superset< char, float >` {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01char_00_01float_01_4}

<h2> Summary </h2>

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01char_00_01float_01_4_1aa5e8ffc5af471d494b8a4609e2aa89b8) | 

<h2> Members </h2>

#### `typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01char_00_01float_01_4_1aa5e8ffc5af471d494b8a4609e2aa89b8) {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01char_00_01float_01_4_1aa5e8ffc5af471d494b8a4609e2aa89b8}

# struct `cimg_library_suffixed::cimg::superset< char, int >` {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01char_00_01int_01_4}

<h2> Summary </h2>

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01char_00_01int_01_4_1a2f2d753886028c69addbdf4b5480429b) | 

<h2> Members </h2>

#### `typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01char_00_01int_01_4_1a2f2d753886028c69addbdf4b5480429b) {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01char_00_01int_01_4_1a2f2d753886028c69addbdf4b5480429b}

# struct `cimg_library_suffixed::cimg::superset< char, short >` {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01char_00_01short_01_4}

<h2> Summary </h2>

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01char_00_01short_01_4_1a18cfeaa6cbae4b2bb61cf681f88c3924) | 

<h2> Members </h2>

#### `typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01char_00_01short_01_4_1a18cfeaa6cbae4b2bb61cf681f88c3924) {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01char_00_01short_01_4_1a18cfeaa6cbae4b2bb61cf681f88c3924}

# struct `cimg_library_suffixed::cimg::superset< char, signed char >` {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01char_00_01signed_01char_01_4}

<h2> Summary </h2>

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01char_00_01signed_01char_01_4_1a524f73803bfd09dda3ccfc53ec93dd9c) | 

<h2> Members </h2>

#### `typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01char_00_01signed_01char_01_4_1a524f73803bfd09dda3ccfc53ec93dd9c) {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01char_00_01signed_01char_01_4_1a524f73803bfd09dda3ccfc53ec93dd9c}

# struct `cimg_library_suffixed::cimg::superset< char, unsigned char >` {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01char_00_01unsigned_01char_01_4}

<h2> Summary </h2>

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01char_00_01unsigned_01char_01_4_1af7d4c67bd87f51e6f1b2673b33e43329) | 

<h2> Members </h2>

#### `typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01char_00_01unsigned_01char_01_4_1af7d4c67bd87f51e6f1b2673b33e43329) {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01char_00_01unsigned_01char_01_4_1af7d4c67bd87f51e6f1b2673b33e43329}

# struct `cimg_library_suffixed::cimg::superset< char, unsigned int >` {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01char_00_01unsigned_01int_01_4}

<h2> Summary </h2>

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01char_00_01unsigned_01int_01_4_1ae11e313b11f824c6cdad3e9c157c82bd) | 

<h2> Members </h2>

#### `typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01char_00_01unsigned_01int_01_4_1ae11e313b11f824c6cdad3e9c157c82bd) {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01char_00_01unsigned_01int_01_4_1ae11e313b11f824c6cdad3e9c157c82bd}

# struct `cimg_library_suffixed::cimg::superset< char, unsigned short >` {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01char_00_01unsigned_01short_01_4}

<h2> Summary </h2>

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01char_00_01unsigned_01short_01_4_1a9e62306a3b532983cffd73730b330f99) | 

<h2> Members </h2>

#### `typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01char_00_01unsigned_01short_01_4_1a9e62306a3b532983cffd73730b330f99) {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01char_00_01unsigned_01short_01_4_1a9e62306a3b532983cffd73730b330f99}

# struct `cimg_library_suffixed::cimg::superset< cimg_int64, double >` {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01cimg__int64_00_01double_01_4}

<h2> Summary </h2>

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01cimg__int64_00_01double_01_4_1a28db5b8df2001ba46063d503ea771c4e) | 

<h2> Members </h2>

#### `typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01cimg__int64_00_01double_01_4_1a28db5b8df2001ba46063d503ea771c4e) {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01cimg__int64_00_01double_01_4_1a28db5b8df2001ba46063d503ea771c4e}

# struct `cimg_library_suffixed::cimg::superset< cimg_int64, float >` {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01cimg__int64_00_01float_01_4}

<h2> Summary </h2>

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01cimg__int64_00_01float_01_4_1a7e72ede1380d85f601c52ce0d4e3baa5) | 

<h2> Members </h2>

#### `typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01cimg__int64_00_01float_01_4_1a7e72ede1380d85f601c52ce0d4e3baa5) {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01cimg__int64_00_01float_01_4_1a7e72ede1380d85f601c52ce0d4e3baa5}

# struct `cimg_library_suffixed::cimg::superset< cimg_uint64, char >` {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01cimg__uint64_00_01char_01_4}

<h2> Summary </h2>

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01cimg__uint64_00_01char_01_4_1a0da6f18678959c893e087b2f3b6f09b3) | 

<h2> Members </h2>

#### `typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01cimg__uint64_00_01char_01_4_1a0da6f18678959c893e087b2f3b6f09b3) {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01cimg__uint64_00_01char_01_4_1a0da6f18678959c893e087b2f3b6f09b3}

# struct `cimg_library_suffixed::cimg::superset< cimg_uint64, cimg_int64 >` {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01cimg__uint64_00_01cimg__int64_01_4}

<h2> Summary </h2>

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01cimg__uint64_00_01cimg__int64_01_4_1a871e5b305680fb0454dc461f72fe1ee2) | 

<h2> Members </h2>

#### `typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01cimg__uint64_00_01cimg__int64_01_4_1a871e5b305680fb0454dc461f72fe1ee2) {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01cimg__uint64_00_01cimg__int64_01_4_1a871e5b305680fb0454dc461f72fe1ee2}

# struct `cimg_library_suffixed::cimg::superset< cimg_uint64, double >` {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01cimg__uint64_00_01double_01_4}

<h2> Summary </h2>

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01cimg__uint64_00_01double_01_4_1a5246bf86686536651e52a4832bb4da92) | 

<h2> Members </h2>

#### `typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01cimg__uint64_00_01double_01_4_1a5246bf86686536651e52a4832bb4da92) {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01cimg__uint64_00_01double_01_4_1a5246bf86686536651e52a4832bb4da92}

# struct `cimg_library_suffixed::cimg::superset< cimg_uint64, float >` {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01cimg__uint64_00_01float_01_4}

<h2> Summary </h2>

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01cimg__uint64_00_01float_01_4_1a716714d140a416abe480e064606b4383) | 

<h2> Members </h2>

#### `typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01cimg__uint64_00_01float_01_4_1a716714d140a416abe480e064606b4383) {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01cimg__uint64_00_01float_01_4_1a716714d140a416abe480e064606b4383}

# struct `cimg_library_suffixed::cimg::superset< cimg_uint64, int >` {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01cimg__uint64_00_01int_01_4}

<h2> Summary </h2>

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01cimg__uint64_00_01int_01_4_1a2345cd4ea200853ee7725898c070c42e) | 

<h2> Members </h2>

#### `typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01cimg__uint64_00_01int_01_4_1a2345cd4ea200853ee7725898c070c42e) {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01cimg__uint64_00_01int_01_4_1a2345cd4ea200853ee7725898c070c42e}

# struct `cimg_library_suffixed::cimg::superset< cimg_uint64, short >` {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01cimg__uint64_00_01short_01_4}

<h2> Summary </h2>

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01cimg__uint64_00_01short_01_4_1a7220071b52a3082389bfdb8be752c234) | 

<h2> Members </h2>

#### `typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01cimg__uint64_00_01short_01_4_1a7220071b52a3082389bfdb8be752c234) {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01cimg__uint64_00_01short_01_4_1a7220071b52a3082389bfdb8be752c234}

# struct `cimg_library_suffixed::cimg::superset< cimg_uint64, signed char >` {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01cimg__uint64_00_01signed_01char_01_4}

<h2> Summary </h2>

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01cimg__uint64_00_01signed_01char_01_4_1a610a1a9e6a8e0ff415338cc92b234d7f) | 

<h2> Members </h2>

#### `typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01cimg__uint64_00_01signed_01char_01_4_1a610a1a9e6a8e0ff415338cc92b234d7f) {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01cimg__uint64_00_01signed_01char_01_4_1a610a1a9e6a8e0ff415338cc92b234d7f}

# struct `cimg_library_suffixed::cimg::superset< float, double >` {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01float_00_01double_01_4}

<h2> Summary </h2>

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01float_00_01double_01_4_1aa718bce8121fc62d8c666639d1f251e1) | 

<h2> Members </h2>

#### `typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01float_00_01double_01_4_1aa718bce8121fc62d8c666639d1f251e1) {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01float_00_01double_01_4_1aa718bce8121fc62d8c666639d1f251e1}

# struct `cimg_library_suffixed::cimg::superset< int, cimg_int64 >` {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01int_00_01cimg__int64_01_4}

<h2> Summary </h2>

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01int_00_01cimg__int64_01_4_1a6eddf3cd71806d37f55691cc02af0095) | 

<h2> Members </h2>

#### `typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01int_00_01cimg__int64_01_4_1a6eddf3cd71806d37f55691cc02af0095) {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01int_00_01cimg__int64_01_4_1a6eddf3cd71806d37f55691cc02af0095}

# struct `cimg_library_suffixed::cimg::superset< int, cimg_uint64 >` {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01int_00_01cimg__uint64_01_4}

<h2> Summary </h2>

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01int_00_01cimg__uint64_01_4_1a8eec20c2a9229911c7ef9a8a5668a761) | 

<h2> Members </h2>

#### `typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01int_00_01cimg__uint64_01_4_1a8eec20c2a9229911c7ef9a8a5668a761) {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01int_00_01cimg__uint64_01_4_1a8eec20c2a9229911c7ef9a8a5668a761}

# struct `cimg_library_suffixed::cimg::superset< int, double >` {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01int_00_01double_01_4}

<h2> Summary </h2>

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01int_00_01double_01_4_1a4e469080a7f9c9f8cc8a1c346e36534f) | 

<h2> Members </h2>

#### `typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01int_00_01double_01_4_1a4e469080a7f9c9f8cc8a1c346e36534f) {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01int_00_01double_01_4_1a4e469080a7f9c9f8cc8a1c346e36534f}

# struct `cimg_library_suffixed::cimg::superset< int, float >` {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01int_00_01float_01_4}

<h2> Summary </h2>

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01int_00_01float_01_4_1aef3af5c5516d697a44b97506d350d3ce) | 

<h2> Members </h2>

#### `typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01int_00_01float_01_4_1aef3af5c5516d697a44b97506d350d3ce) {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01int_00_01float_01_4_1aef3af5c5516d697a44b97506d350d3ce}

# struct `cimg_library_suffixed::cimg::superset< int, unsigned int >` {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01int_00_01unsigned_01int_01_4}

<h2> Summary </h2>

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01int_00_01unsigned_01int_01_4_1a9c7c85ec59bcc6a30ccf39630833c112) | 

<h2> Members </h2>

#### `typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01int_00_01unsigned_01int_01_4_1a9c7c85ec59bcc6a30ccf39630833c112) {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01int_00_01unsigned_01int_01_4_1a9c7c85ec59bcc6a30ccf39630833c112}

# struct `cimg_library_suffixed::cimg::superset< short, cimg_int64 >` {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01short_00_01cimg__int64_01_4}

<h2> Summary </h2>

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01short_00_01cimg__int64_01_4_1a824a9cd4ce9116587d3106338e6ae618) | 

<h2> Members </h2>

#### `typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01short_00_01cimg__int64_01_4_1a824a9cd4ce9116587d3106338e6ae618) {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01short_00_01cimg__int64_01_4_1a824a9cd4ce9116587d3106338e6ae618}

# struct `cimg_library_suffixed::cimg::superset< short, cimg_uint64 >` {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01short_00_01cimg__uint64_01_4}

<h2> Summary </h2>

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01short_00_01cimg__uint64_01_4_1a39f178f8a05fad58fd7980f234fa0357) | 

<h2> Members </h2>

#### `typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01short_00_01cimg__uint64_01_4_1a39f178f8a05fad58fd7980f234fa0357) {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01short_00_01cimg__uint64_01_4_1a39f178f8a05fad58fd7980f234fa0357}

# struct `cimg_library_suffixed::cimg::superset< short, double >` {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01short_00_01double_01_4}

<h2> Summary </h2>

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01short_00_01double_01_4_1a0a56e1f9affc534c80e19c719ec29cdf) | 

<h2> Members </h2>

#### `typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01short_00_01double_01_4_1a0a56e1f9affc534c80e19c719ec29cdf) {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01short_00_01double_01_4_1a0a56e1f9affc534c80e19c719ec29cdf}

# struct `cimg_library_suffixed::cimg::superset< short, float >` {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01short_00_01float_01_4}

<h2> Summary </h2>

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01short_00_01float_01_4_1acee74c374a8be813324e20ccd3dee19a) | 

<h2> Members </h2>

#### `typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01short_00_01float_01_4_1acee74c374a8be813324e20ccd3dee19a) {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01short_00_01float_01_4_1acee74c374a8be813324e20ccd3dee19a}

# struct `cimg_library_suffixed::cimg::superset< short, int >` {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01short_00_01int_01_4}

<h2> Summary </h2>

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01short_00_01int_01_4_1a5bc30aff54d759be6bdb7a864964ad61) | 

<h2> Members </h2>

#### `typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01short_00_01int_01_4_1a5bc30aff54d759be6bdb7a864964ad61) {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01short_00_01int_01_4_1a5bc30aff54d759be6bdb7a864964ad61}

# struct `cimg_library_suffixed::cimg::superset< short, unsigned int >` {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01short_00_01unsigned_01int_01_4}

<h2> Summary </h2>

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01short_00_01unsigned_01int_01_4_1ad5428836bc6d53e54215f57fc4d6fabf) | 

<h2> Members </h2>

#### `typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01short_00_01unsigned_01int_01_4_1ad5428836bc6d53e54215f57fc4d6fabf) {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01short_00_01unsigned_01int_01_4_1ad5428836bc6d53e54215f57fc4d6fabf}

# struct `cimg_library_suffixed::cimg::superset< short, unsigned short >` {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01short_00_01unsigned_01short_01_4}

<h2> Summary </h2>

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01short_00_01unsigned_01short_01_4_1a272ac1c96b01cb17818576b588ec7075) | 

<h2> Members </h2>

#### `typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01short_00_01unsigned_01short_01_4_1a272ac1c96b01cb17818576b588ec7075) {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01short_00_01unsigned_01short_01_4_1a272ac1c96b01cb17818576b588ec7075}

# struct `cimg_library_suffixed::cimg::superset< signed char, char >` {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01signed_01char_00_01char_01_4}

<h2> Summary </h2>

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01signed_01char_00_01char_01_4_1ab5d01c56fd997d6e68eccae01ded7ba8) | 

<h2> Members </h2>

#### `typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01signed_01char_00_01char_01_4_1ab5d01c56fd997d6e68eccae01ded7ba8) {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01signed_01char_00_01char_01_4_1ab5d01c56fd997d6e68eccae01ded7ba8}

# struct `cimg_library_suffixed::cimg::superset< signed char, cimg_int64 >` {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01signed_01char_00_01cimg__int64_01_4}

<h2> Summary </h2>

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01signed_01char_00_01cimg__int64_01_4_1a8222f6fc102add376a86fe763462f325) | 

<h2> Members </h2>

#### `typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01signed_01char_00_01cimg__int64_01_4_1a8222f6fc102add376a86fe763462f325) {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01signed_01char_00_01cimg__int64_01_4_1a8222f6fc102add376a86fe763462f325}

# struct `cimg_library_suffixed::cimg::superset< signed char, cimg_uint64 >` {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01signed_01char_00_01cimg__uint64_01_4}

<h2> Summary </h2>

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01signed_01char_00_01cimg__uint64_01_4_1a0a42782ab2e78aa22f0078bc3e3182df) | 

<h2> Members </h2>

#### `typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01signed_01char_00_01cimg__uint64_01_4_1a0a42782ab2e78aa22f0078bc3e3182df) {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01signed_01char_00_01cimg__uint64_01_4_1a0a42782ab2e78aa22f0078bc3e3182df}

# struct `cimg_library_suffixed::cimg::superset< signed char, double >` {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01signed_01char_00_01double_01_4}

<h2> Summary </h2>

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01signed_01char_00_01double_01_4_1a72c08549867610f27cedf98e3c795a25) | 

<h2> Members </h2>

#### `typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01signed_01char_00_01double_01_4_1a72c08549867610f27cedf98e3c795a25) {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01signed_01char_00_01double_01_4_1a72c08549867610f27cedf98e3c795a25}

# struct `cimg_library_suffixed::cimg::superset< signed char, float >` {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01signed_01char_00_01float_01_4}

<h2> Summary </h2>

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01signed_01char_00_01float_01_4_1afe8c13a5ba8277de526e34876588fcca) | 

<h2> Members </h2>

#### `typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01signed_01char_00_01float_01_4_1afe8c13a5ba8277de526e34876588fcca) {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01signed_01char_00_01float_01_4_1afe8c13a5ba8277de526e34876588fcca}

# struct `cimg_library_suffixed::cimg::superset< signed char, int >` {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01signed_01char_00_01int_01_4}

<h2> Summary </h2>

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01signed_01char_00_01int_01_4_1a617e3b198272fb8924e7de6bbc57b5f1) | 

<h2> Members </h2>

#### `typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01signed_01char_00_01int_01_4_1a617e3b198272fb8924e7de6bbc57b5f1) {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01signed_01char_00_01int_01_4_1a617e3b198272fb8924e7de6bbc57b5f1}

# struct `cimg_library_suffixed::cimg::superset< signed char, short >` {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01signed_01char_00_01short_01_4}

<h2> Summary </h2>

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01signed_01char_00_01short_01_4_1a2c26ad7eb46576ab84db770dca876d4a) | 

<h2> Members </h2>

#### `typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01signed_01char_00_01short_01_4_1a2c26ad7eb46576ab84db770dca876d4a) {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01signed_01char_00_01short_01_4_1a2c26ad7eb46576ab84db770dca876d4a}

# struct `cimg_library_suffixed::cimg::superset< signed char, unsigned char >` {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01signed_01char_00_01unsigned_01char_01_4}

<h2> Summary </h2>

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01signed_01char_00_01unsigned_01char_01_4_1a24e1e6c704d626e2a0a35a18a91c0255) | 

<h2> Members </h2>

#### `typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01signed_01char_00_01unsigned_01char_01_4_1a24e1e6c704d626e2a0a35a18a91c0255) {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01signed_01char_00_01unsigned_01char_01_4_1a24e1e6c704d626e2a0a35a18a91c0255}

# struct `cimg_library_suffixed::cimg::superset< signed char, unsigned int >` {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01signed_01char_00_01unsigned_01int_01_4}

<h2> Summary </h2>

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01signed_01char_00_01unsigned_01int_01_4_1a4a16bfe2a0cff7a21c5d260b29d65945) | 

<h2> Members </h2>

#### `typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01signed_01char_00_01unsigned_01int_01_4_1a4a16bfe2a0cff7a21c5d260b29d65945) {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01signed_01char_00_01unsigned_01int_01_4_1a4a16bfe2a0cff7a21c5d260b29d65945}

# struct `cimg_library_suffixed::cimg::superset< signed char, unsigned short >` {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01signed_01char_00_01unsigned_01short_01_4}

<h2> Summary </h2>

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01signed_01char_00_01unsigned_01short_01_4_1a7adfc7af518217b389efb0bfc0a8c16c) | 

<h2> Members </h2>

#### `typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01signed_01char_00_01unsigned_01short_01_4_1a7adfc7af518217b389efb0bfc0a8c16c) {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01signed_01char_00_01unsigned_01short_01_4_1a7adfc7af518217b389efb0bfc0a8c16c}

# struct `cimg_library_suffixed::cimg::superset< unsigned char, char >` {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01char_00_01char_01_4}

<h2> Summary </h2>

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01char_00_01char_01_4_1a3163e996e3a2b37ac3a396aa76db475e) | 

<h2> Members </h2>

#### `typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01char_00_01char_01_4_1a3163e996e3a2b37ac3a396aa76db475e) {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01char_00_01char_01_4_1a3163e996e3a2b37ac3a396aa76db475e}

# struct `cimg_library_suffixed::cimg::superset< unsigned char, cimg_int64 >` {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01char_00_01cimg__int64_01_4}

<h2> Summary </h2>

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01char_00_01cimg__int64_01_4_1a6d737c40b6d78eae8ad679b078d1dcc7) | 

<h2> Members </h2>

#### `typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01char_00_01cimg__int64_01_4_1a6d737c40b6d78eae8ad679b078d1dcc7) {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01char_00_01cimg__int64_01_4_1a6d737c40b6d78eae8ad679b078d1dcc7}

# struct `cimg_library_suffixed::cimg::superset< unsigned char, cimg_uint64 >` {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01char_00_01cimg__uint64_01_4}

<h2> Summary </h2>

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01char_00_01cimg__uint64_01_4_1a176ff089eac29305efcc9929fee5563c) | 

<h2> Members </h2>

#### `typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01char_00_01cimg__uint64_01_4_1a176ff089eac29305efcc9929fee5563c) {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01char_00_01cimg__uint64_01_4_1a176ff089eac29305efcc9929fee5563c}

# struct `cimg_library_suffixed::cimg::superset< unsigned char, double >` {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01char_00_01double_01_4}

<h2> Summary </h2>

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01char_00_01double_01_4_1aa3fa9601d84938a96d0ff34b45c4dc28) | 

<h2> Members </h2>

#### `typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01char_00_01double_01_4_1aa3fa9601d84938a96d0ff34b45c4dc28) {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01char_00_01double_01_4_1aa3fa9601d84938a96d0ff34b45c4dc28}

# struct `cimg_library_suffixed::cimg::superset< unsigned char, float >` {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01char_00_01float_01_4}

<h2> Summary </h2>

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01char_00_01float_01_4_1a5bbbc84442f664f77c9e78fa5e1eaf92) | 

<h2> Members </h2>

#### `typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01char_00_01float_01_4_1a5bbbc84442f664f77c9e78fa5e1eaf92) {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01char_00_01float_01_4_1a5bbbc84442f664f77c9e78fa5e1eaf92}

# struct `cimg_library_suffixed::cimg::superset< unsigned char, int >` {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01char_00_01int_01_4}

<h2> Summary </h2>

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01char_00_01int_01_4_1a37daeabce31aa7be86df684059fec2c2) | 

<h2> Members </h2>

#### `typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01char_00_01int_01_4_1a37daeabce31aa7be86df684059fec2c2) {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01char_00_01int_01_4_1a37daeabce31aa7be86df684059fec2c2}

# struct `cimg_library_suffixed::cimg::superset< unsigned char, short >` {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01char_00_01short_01_4}

<h2> Summary </h2>

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01char_00_01short_01_4_1acf0139f61db3180ac2e67ff00b378525) | 

<h2> Members </h2>

#### `typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01char_00_01short_01_4_1acf0139f61db3180ac2e67ff00b378525) {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01char_00_01short_01_4_1acf0139f61db3180ac2e67ff00b378525}

# struct `cimg_library_suffixed::cimg::superset< unsigned char, signed char >` {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01char_00_01signed_01char_01_4}

<h2> Summary </h2>

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01char_00_01signed_01char_01_4_1a9f434661bf301c7225643caac5757d33) | 

<h2> Members </h2>

#### `typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01char_00_01signed_01char_01_4_1a9f434661bf301c7225643caac5757d33) {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01char_00_01signed_01char_01_4_1a9f434661bf301c7225643caac5757d33}

# struct `cimg_library_suffixed::cimg::superset< unsigned char, unsigned int >` {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01char_00_01unsigned_01int_01_4}

<h2> Summary </h2>

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01char_00_01unsigned_01int_01_4_1ad07e13e16e27434e1427857ebb7104dd) | 

<h2> Members </h2>

#### `typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01char_00_01unsigned_01int_01_4_1ad07e13e16e27434e1427857ebb7104dd) {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01char_00_01unsigned_01int_01_4_1ad07e13e16e27434e1427857ebb7104dd}

# struct `cimg_library_suffixed::cimg::superset< unsigned char, unsigned short >` {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01char_00_01unsigned_01short_01_4}

<h2> Summary </h2>

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01char_00_01unsigned_01short_01_4_1af2202f75978a321ae6c5220f4303d41f) | 

<h2> Members </h2>

#### `typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01char_00_01unsigned_01short_01_4_1af2202f75978a321ae6c5220f4303d41f) {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01char_00_01unsigned_01short_01_4_1af2202f75978a321ae6c5220f4303d41f}

# struct `cimg_library_suffixed::cimg::superset< unsigned int, char >` {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01int_00_01char_01_4}

<h2> Summary </h2>

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01int_00_01char_01_4_1a12c0e13f3654cd25a8f6e7204ed84791) | 

<h2> Members </h2>

#### `typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01int_00_01char_01_4_1a12c0e13f3654cd25a8f6e7204ed84791) {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01int_00_01char_01_4_1a12c0e13f3654cd25a8f6e7204ed84791}

# struct `cimg_library_suffixed::cimg::superset< unsigned int, cimg_int64 >` {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01int_00_01cimg__int64_01_4}

<h2> Summary </h2>

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01int_00_01cimg__int64_01_4_1a0491ed6320d98a3c2b30dd6780e8a301) | 

<h2> Members </h2>

#### `typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01int_00_01cimg__int64_01_4_1a0491ed6320d98a3c2b30dd6780e8a301) {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01int_00_01cimg__int64_01_4_1a0491ed6320d98a3c2b30dd6780e8a301}

# struct `cimg_library_suffixed::cimg::superset< unsigned int, cimg_uint64 >` {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01int_00_01cimg__uint64_01_4}

<h2> Summary </h2>

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01int_00_01cimg__uint64_01_4_1a2f82a9bf57e51c773ec4956a94422eaf) | 

<h2> Members </h2>

#### `typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01int_00_01cimg__uint64_01_4_1a2f82a9bf57e51c773ec4956a94422eaf) {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01int_00_01cimg__uint64_01_4_1a2f82a9bf57e51c773ec4956a94422eaf}

# struct `cimg_library_suffixed::cimg::superset< unsigned int, double >` {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01int_00_01double_01_4}

<h2> Summary </h2>

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01int_00_01double_01_4_1afeccf9a3271420bf6ac22ab506e7481e) | 

<h2> Members </h2>

#### `typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01int_00_01double_01_4_1afeccf9a3271420bf6ac22ab506e7481e) {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01int_00_01double_01_4_1afeccf9a3271420bf6ac22ab506e7481e}

# struct `cimg_library_suffixed::cimg::superset< unsigned int, float >` {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01int_00_01float_01_4}

<h2> Summary </h2>

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01int_00_01float_01_4_1a7b6d1655a8b97209f47e0bc6012ee8aa) | 

<h2> Members </h2>

#### `typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01int_00_01float_01_4_1a7b6d1655a8b97209f47e0bc6012ee8aa) {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01int_00_01float_01_4_1a7b6d1655a8b97209f47e0bc6012ee8aa}

# struct `cimg_library_suffixed::cimg::superset< unsigned int, int >` {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01int_00_01int_01_4}

<h2> Summary </h2>

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01int_00_01int_01_4_1a4562c14a4a213b1d1bc2e6e8a4f5c3f8) | 

<h2> Members </h2>

#### `typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01int_00_01int_01_4_1a4562c14a4a213b1d1bc2e6e8a4f5c3f8) {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01int_00_01int_01_4_1a4562c14a4a213b1d1bc2e6e8a4f5c3f8}

# struct `cimg_library_suffixed::cimg::superset< unsigned int, short >` {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01int_00_01short_01_4}

<h2> Summary </h2>

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01int_00_01short_01_4_1acf99769488a811c4e6551606bd9431fc) | 

<h2> Members </h2>

#### `typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01int_00_01short_01_4_1acf99769488a811c4e6551606bd9431fc) {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01int_00_01short_01_4_1acf99769488a811c4e6551606bd9431fc}

# struct `cimg_library_suffixed::cimg::superset< unsigned int, signed char >` {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01int_00_01signed_01char_01_4}

<h2> Summary </h2>

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01int_00_01signed_01char_01_4_1ae26b1cc91c36c62a9abd63a9e8a996da) | 

<h2> Members </h2>

#### `typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01int_00_01signed_01char_01_4_1ae26b1cc91c36c62a9abd63a9e8a996da) {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01int_00_01signed_01char_01_4_1ae26b1cc91c36c62a9abd63a9e8a996da}

# struct `cimg_library_suffixed::cimg::superset< unsigned short, char >` {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01short_00_01char_01_4}

<h2> Summary </h2>

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01short_00_01char_01_4_1af737d539d2d3ac2abec81687fdc82fd9) | 

<h2> Members </h2>

#### `typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01short_00_01char_01_4_1af737d539d2d3ac2abec81687fdc82fd9) {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01short_00_01char_01_4_1af737d539d2d3ac2abec81687fdc82fd9}

# struct `cimg_library_suffixed::cimg::superset< unsigned short, cimg_int64 >` {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01short_00_01cimg__int64_01_4}

<h2> Summary </h2>

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01short_00_01cimg__int64_01_4_1a77bfac105e6337a09d7828b6469ba647) | 

<h2> Members </h2>

#### `typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01short_00_01cimg__int64_01_4_1a77bfac105e6337a09d7828b6469ba647) {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01short_00_01cimg__int64_01_4_1a77bfac105e6337a09d7828b6469ba647}

# struct `cimg_library_suffixed::cimg::superset< unsigned short, cimg_uint64 >` {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01short_00_01cimg__uint64_01_4}

<h2> Summary </h2>

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01short_00_01cimg__uint64_01_4_1acad4cb58562c4d687f15b11f5cd0bcce) | 

<h2> Members </h2>

#### `typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01short_00_01cimg__uint64_01_4_1acad4cb58562c4d687f15b11f5cd0bcce) {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01short_00_01cimg__uint64_01_4_1acad4cb58562c4d687f15b11f5cd0bcce}

# struct `cimg_library_suffixed::cimg::superset< unsigned short, double >` {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01short_00_01double_01_4}

<h2> Summary </h2>

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01short_00_01double_01_4_1a1a36409119e78bbe2a8f8088444a0837) | 

<h2> Members </h2>

#### `typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01short_00_01double_01_4_1a1a36409119e78bbe2a8f8088444a0837) {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01short_00_01double_01_4_1a1a36409119e78bbe2a8f8088444a0837}

# struct `cimg_library_suffixed::cimg::superset< unsigned short, float >` {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01short_00_01float_01_4}

<h2> Summary </h2>

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01short_00_01float_01_4_1a7ca93ba84007cc6685b7a1a7da5ae333) | 

<h2> Members </h2>

#### `typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01short_00_01float_01_4_1a7ca93ba84007cc6685b7a1a7da5ae333) {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01short_00_01float_01_4_1a7ca93ba84007cc6685b7a1a7da5ae333}

# struct `cimg_library_suffixed::cimg::superset< unsigned short, int >` {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01short_00_01int_01_4}

<h2> Summary </h2>

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01short_00_01int_01_4_1acb828d363e7f784d3c087fdaa27a6bd9) | 

<h2> Members </h2>

#### `typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01short_00_01int_01_4_1acb828d363e7f784d3c087fdaa27a6bd9) {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01short_00_01int_01_4_1acb828d363e7f784d3c087fdaa27a6bd9}

# struct `cimg_library_suffixed::cimg::superset< unsigned short, short >` {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01short_00_01short_01_4}

<h2> Summary </h2>

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01short_00_01short_01_4_1a605f030f945625f24f5f81624c59a3b3) | 

<h2> Members </h2>

#### `typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01short_00_01short_01_4_1a605f030f945625f24f5f81624c59a3b3) {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01short_00_01short_01_4_1a605f030f945625f24f5f81624c59a3b3}

# struct `cimg_library_suffixed::cimg::superset< unsigned short, signed char >` {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01short_00_01signed_01char_01_4}

<h2> Summary </h2>

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01short_00_01signed_01char_01_4_1a7362691336de47c9fa23caeec77edb85) | 

<h2> Members </h2>

#### `typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01short_00_01signed_01char_01_4_1a7362691336de47c9fa23caeec77edb85) {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01short_00_01signed_01char_01_4_1a7362691336de47c9fa23caeec77edb85}

# struct `cimg_library_suffixed::cimg::superset< unsigned short, unsigned int >` {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01short_00_01unsigned_01int_01_4}

<h2> Summary </h2>

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01short_00_01unsigned_01int_01_4_1a4feee8ad6d9531c094accdba33262511) | 

<h2> Members </h2>

#### `typedef `[`type`](#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01short_00_01unsigned_01int_01_4_1a4feee8ad6d9531c094accdba33262511) {#structcimg__library__suffixed_1_1cimg_1_1superset_3_01unsigned_01short_00_01unsigned_01int_01_4_1a4feee8ad6d9531c094accdba33262511}

# struct `cimg_library_suffixed::cimg::type` {#structcimg__library__suffixed_1_1cimg_1_1type}

<h2> Summary </h2>

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------

<h2> Members </h2>

# struct `cimg_library_suffixed::cimg::type< bool >` {#structcimg__library__suffixed_1_1cimg_1_1type_3_01bool_01_4}

<h2> Summary </h2>

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------

<h2> Members </h2>

# struct `cimg_library_suffixed::cimg::type< char >` {#structcimg__library__suffixed_1_1cimg_1_1type_3_01char_01_4}

<h2> Summary </h2>

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------

<h2> Members </h2>

# struct `cimg_library_suffixed::cimg::type< cimg_int64 >` {#structcimg__library__suffixed_1_1cimg_1_1type_3_01cimg__int64_01_4}

<h2> Summary </h2>

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------

<h2> Members </h2>

# struct `cimg_library_suffixed::cimg::type< cimg_uint64 >` {#structcimg__library__suffixed_1_1cimg_1_1type_3_01cimg__uint64_01_4}

<h2> Summary </h2>

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------

<h2> Members </h2>

# struct `cimg_library_suffixed::cimg::type< double >` {#structcimg__library__suffixed_1_1cimg_1_1type_3_01double_01_4}

<h2> Summary </h2>

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------

<h2> Members </h2>

# struct `cimg_library_suffixed::cimg::type< float >` {#structcimg__library__suffixed_1_1cimg_1_1type_3_01float_01_4}

<h2> Summary </h2>

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------

<h2> Members </h2>

# struct `cimg_library_suffixed::cimg::type< int >` {#structcimg__library__suffixed_1_1cimg_1_1type_3_01int_01_4}

<h2> Summary </h2>

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------

<h2> Members </h2>

# struct `cimg_library_suffixed::cimg::type< long double >` {#structcimg__library__suffixed_1_1cimg_1_1type_3_01long_01double_01_4}

<h2> Summary </h2>

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------

<h2> Members </h2>

# struct `cimg_library_suffixed::cimg::type< short >` {#structcimg__library__suffixed_1_1cimg_1_1type_3_01short_01_4}

<h2> Summary </h2>

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------

<h2> Members </h2>

# struct `cimg_library_suffixed::cimg::type< signed char >` {#structcimg__library__suffixed_1_1cimg_1_1type_3_01signed_01char_01_4}

<h2> Summary </h2>

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------

<h2> Members </h2>

# struct `cimg_library_suffixed::cimg::type< unsigned char >` {#structcimg__library__suffixed_1_1cimg_1_1type_3_01unsigned_01char_01_4}

<h2> Summary </h2>

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------

<h2> Members </h2>

# struct `cimg_library_suffixed::cimg::type< unsigned int >` {#structcimg__library__suffixed_1_1cimg_1_1type_3_01unsigned_01int_01_4}

<h2> Summary </h2>

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------

<h2> Members </h2>

# struct `cimg_library_suffixed::cimg::type< unsigned short >` {#structcimg__library__suffixed_1_1cimg_1_1type_3_01unsigned_01short_01_4}

<h2> Summary </h2>

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------

<h2> Members </h2>

# struct `cimg_library_suffixed::CImg::_cimg_math_parser` {#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser}

<h2> Summary </h2>

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`public `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< doubleT > `[`mem`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a19a6f6640a3a810465a0e17bb2225c09) | 
`public `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< intT > `[`memtype`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1aec0ea80fb8e7e9357c73621a8f76f9cd) | 
`public `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< intT > `[`memmerge`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a03e7bf89c5af03fe7c0fe2a55d5323db) | 
`public `[`CImgList`](#structcimg__library__suffixed_1_1CImgList)`< ulongT > `[`_code`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1ad7cc81340b797c10f3cea673a4f329ba) | 
`public `[`CImgList`](#structcimg__library__suffixed_1_1CImgList)`< ulongT > & `[`code`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a35ae33f7262da446217fe8f648b3622a) | 
`public `[`CImgList`](#structcimg__library__suffixed_1_1CImgList)`< ulongT > `[`code_begin`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a63430e72e3fe1a54dc6e4d6265a1d4d2) | 
`public `[`CImgList`](#structcimg__library__suffixed_1_1CImgList)`< ulongT > `[`code_end`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a4128a065f7496bfab5469edddae88911) | 
`public `[`CImgList`](#structcimg__library__suffixed_1_1CImgList)`< ulongT > `[`_code_begin_t`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1ae4440eb1baffe032f9853d134a43a934) | 
`public `[`CImgList`](#structcimg__library__suffixed_1_1CImgList)`< ulongT > & `[`code_begin_t`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a5afcf6daf681ed347840a22aea372194) | 
`public `[`CImgList`](#structcimg__library__suffixed_1_1CImgList)`< ulongT > `[`_code_end_t`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1ad6952b82cb7bff47d053010d7026199f) | 
`public `[`CImgList`](#structcimg__library__suffixed_1_1CImgList)`< ulongT > & `[`code_end_t`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a9b0ac8e76c9db164a08ea02d181c14e4) | 
`public `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< ulongT > `[`opcode`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1aedd38c6b9e03423957d1325a909e970c) | 
`public const `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< ulongT > * `[`p_code_end`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a1639820dd8a0adb2003f9772b421d183) | 
`public const `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< ulongT > * `[`p_code`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a881d27cb9ba3d2d26b9c9ad0f09fe576) | 
`public const `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< ulongT > *const `[`p_break`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1ac1446d069d8e5f2734cc2c203f618ed0) | 
`public `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< charT > `[`expr`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a3ac94a843e82d2f1d572b55860f82fe2) | 
`public `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< charT > `[`pexpr`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a0232251483f2882861edb03cf88b44ef) | 
`public const `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< T > & `[`imgin`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a5c67b40412e49fab2fc67bfe6fc7cae1) | 
`public const `[`CImgList`](#structcimg__library__suffixed_1_1CImgList)`< T > & `[`listin`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a2e1fbd6bf16b32b66a0383c19ca01d9f) | 
`public `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< T > & `[`imgout`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a39259c16c1ebc7887d04af6c367fa0ae) | 
`public `[`CImgList`](#structcimg__library__suffixed_1_1CImgList)`< T > & `[`listout`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1ae0dbb5720a05dfc11f2f66e56807b3f4) | 
`public `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< doubleT > `[`_img_stats`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a82d7e4d8dd6c20c50ec657300c7c8fe1) | 
`public `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< doubleT > & `[`img_stats`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a22ea21352d5ac0aa652e261948d614ce) | 
`public `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< doubleT > `[`constcache_vals`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a611341995ebe5a7f14cc53ca007e532c) | 
`public `[`CImgList`](#structcimg__library__suffixed_1_1CImgList)`< doubleT > `[`_list_stats`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a47b1f248278fdefd7d5f5b52c37fcda4) | 
`public `[`CImgList`](#structcimg__library__suffixed_1_1CImgList)`< doubleT > & `[`list_stats`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a8de26a37d501fcbdf118c3dc6a51857e) | 
`public `[`CImgList`](#structcimg__library__suffixed_1_1CImgList)`< doubleT > `[`_list_median`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a6a9b13039bdda75c71958724069fea00) | 
`public `[`CImgList`](#structcimg__library__suffixed_1_1CImgList)`< doubleT > & `[`list_median`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1aac6c5a02c19ca25abcd6051ce9ed7818) | 
`public `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< uintT > `[`mem_img_stats`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a7da236e6f2236698fddbfd91821a5c17) | 
`public `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< uintT > `[`constcache_inds`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1aabc927d60d479efaa7d16e21e3fff7fd) | 
`public `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< uintT > `[`level`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1ad4cae37c319469fda89c212c573b33d4) | 
`public `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< uintT > `[`variable_pos`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1adf916aa7f24f400a959bc9844587f8f1) | 
`public `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< uintT > `[`reserved_label`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a73c8633a448ceb4937663740c94f82ed) | 
`public `[`CImgList`](#structcimg__library__suffixed_1_1CImgList)`< charT > `[`variable_def`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1afc1549a689744825235a5a7cb5648cfb) | 
`public `[`CImgList`](#structcimg__library__suffixed_1_1CImgList)`< charT > `[`macro_def`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a27e1a8a052a765cf08785c444a10b0f3) | 
`public `[`CImgList`](#structcimg__library__suffixed_1_1CImgList)`< charT > `[`macro_body`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a935c01ef1959ad35a20a54b512d36522) | 
`public `[`CImgList`](#structcimg__library__suffixed_1_1CImgList)`< boolT > `[`macro_body_is_string`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1ac46543c13dde69685bba79647fa97649) | 
`public char * `[`user_macro`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1adb28d6dfa1569c5c1b991efb2ab113bb) | 
`public unsigned int `[`mempos`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a5c146b152963764fafaac2ca24fe16c0) | 
`public unsigned int `[`mem_img_median`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a642ad67b422a62d89dadaebf14035cbc) | 
`public unsigned int `[`mem_img_index`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a15e0450fdfe1462be41e82f32f220924) | 
`public unsigned int `[`debug_indent`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1acba7d50d228e12f662aa9b6d8d1e696d) | 
`public unsigned int `[`result_dim`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a0e7796a4fa6f8f4729f34f483beb5f24) | 
`public unsigned int `[`break_type`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a89b38b787c6469bfe40900141ea5252b) | 
`public unsigned int `[`constcache_size`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a258c34a8cce21382f9a2b5c57987f874) | 
`public bool `[`is_parallelizable`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1af6e02c4f8e10199173f67a4fc5231f31) | 
`public bool `[`is_end_code`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1ae20054e176c2e131a0c69948daf3b497) | 
`public bool `[`is_fill`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a2fc55114e1ba46ed83a60fd7f65499ee) | 
`public bool `[`need_input_copy`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1ada8b588b576249397bc4b3e6f1260a0d) | 
`public double * `[`result`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1aa66554e58545c92fe881935a8725d4e3) | 
`public cimg_uint64 `[`rng`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a611096d597d953db010a32fed80c5644) | 
`public const char *const `[`calling_function`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a2bd158f818126d2f87a1d1b214459dd0) | 
`public const char *const * `[`s_op`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a203276ce7308b0bb54fddf16bf0aa9e5) | 
`public const char *const * `[`ss_op`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a405dc98771a9120126075b7389993761) | 
`public inline  `[`~_cimg_math_parser`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1aa621746641c0461f490da91e4a7e8873)`()` | 
`public inline  `[`_cimg_math_parser`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a591684f81af8ba85885b7de9c0c6ca5f)`(const char *const expression,const char *const funcname,const `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< T > & img_input,`[`CImg`](#structcimg__library__suffixed_1_1CImg)`< T > *const img_output,const `[`CImgList`](#structcimg__library__suffixed_1_1CImgList)`< T > *const list_inputs,`[`CImgList`](#structcimg__library__suffixed_1_1CImgList)`< T > *const list_outputs,const bool _is_fill)` | 
`public inline  `[`_cimg_math_parser`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a51a887a873a637b24f851e5762a88749)`()` | 
`public inline  `[`_cimg_math_parser`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1acdbfbefd542dbfd59b359aaf512237e2)`(const `[`_cimg_math_parser`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser)` & mp)` | 
`public inline unsigned int `[`compile`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a318c44c5d1f4f0114355f37ace87a4ae)`(char * ss,char * se,const unsigned int depth,unsigned int *const p_ref,const bool is_single)` | 
`public inline double `[`operator()`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1ac9bcfb16c10b216b5d99c4f3bc17225c)`(const double x,const double y,const double z,const double c)` | 
`public template<>`  <br/>`inline void `[`operator()`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1ae6105cf70f00ad11665a67c23c8e7d29)`(const double x,const double y,const double z,const double c,t *const output)` | 
`public inline void `[`begin_t`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a9a76741901d6903c9d198e5056da96a1)`()` | 
`public inline void `[`end_t`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a5a8bd96525a35656a98d3f4f22a23afb)`()` | 
`public inline void `[`end`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a6707c6d516122d4e601391d6d0d608bc)`()` | 
`public inline void `[`merge`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a864d0eba43d9505512f7d96ddd71facc)`(`[`_cimg_math_parser`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser)` & mp)` | 
`public inline `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< charT > `[`s_calling_function`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1ae1b9c43911c79934dc0782d153769b45)`() const` | 
`public inline `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< charT > `[`s_type`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a2576c21861d4f00e532fd4c562d07615)`(const unsigned int arg) const` | 
`public inline `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< uintT > `[`get_level`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a5cd605113c87e76134db785755492dbb)`(`[`CImg`](#structcimg__library__suffixed_1_1CImg)`< charT > & _expr) const` | 
`public inline unsigned int `[`get_mem_img_index`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1ac8b1808b2f5da32dd062f924b042c22d)`()` | 
`public inline void `[`get_variable_pos`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1ab29fd288b061b6dacc4db714ab465f96)`(const char * variable_name,unsigned int & pos,unsigned int & rpos)` | 
`public inline `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< boolT > `[`is_inside_string`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a320b345dab5cb627c892cf9f9278bd1a)`(`[`CImg`](#structcimg__library__suffixed_1_1CImg)`< charT > & _expr) const` | 
`public inline bool `[`is_varchar`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a2631b8f9f5ac6aa3b4e643516cbf8251)`(const char c) const` | 
`public inline bool `[`is_comp_vector`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a6561d943a1b6cb866ac72467a837a4c9)`(const unsigned int arg) const` | 
`public inline void `[`check_constant`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1ab95626fc3c9df8e9bb3d182328372379)`(const unsigned int arg,const unsigned int n_arg,const unsigned int mode,char *const ss,char *const se,const char saved_char)` | 
`public inline void `[`check_constant_index`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a2f2bfbb6c2e3f0c79fc16d1526ec1f95)`(const unsigned int arg,char *const ss,char *const se,const char saved_char)` | 
`public inline void `[`check_matrix_square`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a9eaf3a1d2c38a1a1b9275604320fc1cc)`(const unsigned int arg,const unsigned int n_arg,char *const ss,char *const se,const char saved_char)` | 
`public inline void `[`check_type`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1ae5bd43fbdd9ff01b95538fd9958ea79f)`(const unsigned int arg,const unsigned int n_arg,const unsigned int mode,const unsigned int N,char *const ss,char *const se,const char saved_char)` | 
`public inline void `[`check_list`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1af19c9440058cbae77a2d7aafb576fb86)`(const bool is_out,char *const ss,char *const se,const char saved_char)` | 
`public inline unsigned int `[`constant`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a1e4b329d6551265b58f355ea6d2229dd)`(const double val)` | 
`public inline unsigned int `[`scalar`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a3fbf24a3096da0af2aca688a11feb616)`()` | 
`public inline unsigned int `[`vector`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1ab3f43a472fa110840243eb500a5b4b2e)`(const unsigned int siz)` | 
`public inline unsigned int `[`vector`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a3a440fb39b9743c44337f4f930f12def)`(const unsigned int siz,const double value)` | 
`public inline unsigned int `[`vector_copy`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a7d9b5b35459bcc94ea2fd2c265b32123)`(const unsigned int arg)` | 
`public inline void `[`set_variable_vector`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a093e737711b2d78bbfdad351794b5b33)`(const unsigned int arg)` | 
`public inline unsigned int `[`scalar0`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a7e2f883a1d6660c9e233ccfd8e611ae5)`(const mp_func op)` | 
`public inline unsigned int `[`scalar1`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a4f752a0ab16ff11f66cbe36c41d28e6e)`(const mp_func op,const unsigned int arg1)` | 
`public inline unsigned int `[`scalar2`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a71ad73003cc670f148a36c031bfdb63e)`(const mp_func op,const unsigned int arg1,const unsigned int arg2)` | 
`public inline unsigned int `[`scalar3`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1ae78d2f0d6168388fca89526501f15fa3)`(const mp_func op,const unsigned int arg1,const unsigned int arg2,const unsigned int arg3)` | 
`public inline unsigned int `[`scalar4`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a896a39dea48354d4621c2b3b69ca7937)`(const mp_func op,const unsigned int arg1,const unsigned int arg2,const unsigned int arg3,const unsigned int arg4)` | 
`public inline unsigned int `[`scalar5`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1ae24ac4a9a45fd573ff49015b81c8576b)`(const mp_func op,const unsigned int arg1,const unsigned int arg2,const unsigned int arg3,const unsigned int arg4,const unsigned int arg5)` | 
`public inline unsigned int `[`scalar6`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a52ff1d240c30fee48cc0903832a2c6c0)`(const mp_func op,const unsigned int arg1,const unsigned int arg2,const unsigned int arg3,const unsigned int arg4,const unsigned int arg5,const unsigned int arg6)` | 
`public inline unsigned int `[`scalar7`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1ae095d22c230ed8cb9760fad0a797569a)`(const mp_func op,const unsigned int arg1,const unsigned int arg2,const unsigned int arg3,const unsigned int arg4,const unsigned int arg5,const unsigned int arg6,const unsigned int arg7)` | 
`public inline void `[`self_vector_s`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1aad42f4efe4a29c92c651b44879c639f5)`(const unsigned int pos,const mp_func op,const unsigned int arg1)` | 
`public inline void `[`self_vector_v`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1ab0821949940cfb53f3ddfa5e39e3ca6d)`(const unsigned int pos,const mp_func op,const unsigned int arg1)` | 
`public inline unsigned int `[`vector1_v`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1aa7cca47d009b3663c2a14aa9307d2ba1)`(const mp_func op,const unsigned int arg1)` | 
`public inline unsigned int `[`vector2_vv`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a930d4d9bb7ea4f7f64283e60f7722139)`(const mp_func op,const unsigned int arg1,const unsigned int arg2)` | 
`public inline unsigned int `[`vector2_vs`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1af3073ae1f236be6068d46c7651a2c2d6)`(const mp_func op,const unsigned int arg1,const unsigned int arg2)` | 
`public inline unsigned int `[`vector2_sv`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a149ded260ecf0cef762feaa47e827077)`(const mp_func op,const unsigned int arg1,const unsigned int arg2)` | 
`public inline unsigned int `[`vector3_vss`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a56491c4fefa5379b35ce87f4654c6001)`(const mp_func op,const unsigned int arg1,const unsigned int arg2,const unsigned int arg3)` | 
`typedef `[`mp_func`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a220deac105e68eef2ee2e612c96a0f75) | 

<h2> Members </h2>

#### `public `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< doubleT > `[`mem`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a19a6f6640a3a810465a0e17bb2225c09) {#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a19a6f6640a3a810465a0e17bb2225c09}

#### `public `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< intT > `[`memtype`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1aec0ea80fb8e7e9357c73621a8f76f9cd) {#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1aec0ea80fb8e7e9357c73621a8f76f9cd}

#### `public `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< intT > `[`memmerge`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a03e7bf89c5af03fe7c0fe2a55d5323db) {#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a03e7bf89c5af03fe7c0fe2a55d5323db}

#### `public `[`CImgList`](#structcimg__library__suffixed_1_1CImgList)`< ulongT > `[`_code`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1ad7cc81340b797c10f3cea673a4f329ba) {#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1ad7cc81340b797c10f3cea673a4f329ba}

#### `public `[`CImgList`](#structcimg__library__suffixed_1_1CImgList)`< ulongT > & `[`code`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a35ae33f7262da446217fe8f648b3622a) {#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a35ae33f7262da446217fe8f648b3622a}

#### `public `[`CImgList`](#structcimg__library__suffixed_1_1CImgList)`< ulongT > `[`code_begin`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a63430e72e3fe1a54dc6e4d6265a1d4d2) {#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a63430e72e3fe1a54dc6e4d6265a1d4d2}

#### `public `[`CImgList`](#structcimg__library__suffixed_1_1CImgList)`< ulongT > `[`code_end`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a4128a065f7496bfab5469edddae88911) {#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a4128a065f7496bfab5469edddae88911}

#### `public `[`CImgList`](#structcimg__library__suffixed_1_1CImgList)`< ulongT > `[`_code_begin_t`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1ae4440eb1baffe032f9853d134a43a934) {#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1ae4440eb1baffe032f9853d134a43a934}

#### `public `[`CImgList`](#structcimg__library__suffixed_1_1CImgList)`< ulongT > & `[`code_begin_t`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a5afcf6daf681ed347840a22aea372194) {#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a5afcf6daf681ed347840a22aea372194}

#### `public `[`CImgList`](#structcimg__library__suffixed_1_1CImgList)`< ulongT > `[`_code_end_t`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1ad6952b82cb7bff47d053010d7026199f) {#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1ad6952b82cb7bff47d053010d7026199f}

#### `public `[`CImgList`](#structcimg__library__suffixed_1_1CImgList)`< ulongT > & `[`code_end_t`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a9b0ac8e76c9db164a08ea02d181c14e4) {#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a9b0ac8e76c9db164a08ea02d181c14e4}

#### `public `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< ulongT > `[`opcode`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1aedd38c6b9e03423957d1325a909e970c) {#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1aedd38c6b9e03423957d1325a909e970c}

#### `public const `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< ulongT > * `[`p_code_end`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a1639820dd8a0adb2003f9772b421d183) {#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a1639820dd8a0adb2003f9772b421d183}

#### `public const `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< ulongT > * `[`p_code`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a881d27cb9ba3d2d26b9c9ad0f09fe576) {#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a881d27cb9ba3d2d26b9c9ad0f09fe576}

#### `public const `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< ulongT > *const `[`p_break`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1ac1446d069d8e5f2734cc2c203f618ed0) {#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1ac1446d069d8e5f2734cc2c203f618ed0}

#### `public `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< charT > `[`expr`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a3ac94a843e82d2f1d572b55860f82fe2) {#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a3ac94a843e82d2f1d572b55860f82fe2}

#### `public `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< charT > `[`pexpr`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a0232251483f2882861edb03cf88b44ef) {#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a0232251483f2882861edb03cf88b44ef}

#### `public const `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< T > & `[`imgin`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a5c67b40412e49fab2fc67bfe6fc7cae1) {#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a5c67b40412e49fab2fc67bfe6fc7cae1}

#### `public const `[`CImgList`](#structcimg__library__suffixed_1_1CImgList)`< T > & `[`listin`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a2e1fbd6bf16b32b66a0383c19ca01d9f) {#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a2e1fbd6bf16b32b66a0383c19ca01d9f}

#### `public `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< T > & `[`imgout`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a39259c16c1ebc7887d04af6c367fa0ae) {#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a39259c16c1ebc7887d04af6c367fa0ae}

#### `public `[`CImgList`](#structcimg__library__suffixed_1_1CImgList)`< T > & `[`listout`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1ae0dbb5720a05dfc11f2f66e56807b3f4) {#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1ae0dbb5720a05dfc11f2f66e56807b3f4}

#### `public `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< doubleT > `[`_img_stats`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a82d7e4d8dd6c20c50ec657300c7c8fe1) {#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a82d7e4d8dd6c20c50ec657300c7c8fe1}

#### `public `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< doubleT > & `[`img_stats`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a22ea21352d5ac0aa652e261948d614ce) {#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a22ea21352d5ac0aa652e261948d614ce}

#### `public `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< doubleT > `[`constcache_vals`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a611341995ebe5a7f14cc53ca007e532c) {#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a611341995ebe5a7f14cc53ca007e532c}

#### `public `[`CImgList`](#structcimg__library__suffixed_1_1CImgList)`< doubleT > `[`_list_stats`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a47b1f248278fdefd7d5f5b52c37fcda4) {#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a47b1f248278fdefd7d5f5b52c37fcda4}

#### `public `[`CImgList`](#structcimg__library__suffixed_1_1CImgList)`< doubleT > & `[`list_stats`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a8de26a37d501fcbdf118c3dc6a51857e) {#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a8de26a37d501fcbdf118c3dc6a51857e}

#### `public `[`CImgList`](#structcimg__library__suffixed_1_1CImgList)`< doubleT > `[`_list_median`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a6a9b13039bdda75c71958724069fea00) {#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a6a9b13039bdda75c71958724069fea00}

#### `public `[`CImgList`](#structcimg__library__suffixed_1_1CImgList)`< doubleT > & `[`list_median`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1aac6c5a02c19ca25abcd6051ce9ed7818) {#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1aac6c5a02c19ca25abcd6051ce9ed7818}

#### `public `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< uintT > `[`mem_img_stats`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a7da236e6f2236698fddbfd91821a5c17) {#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a7da236e6f2236698fddbfd91821a5c17}

#### `public `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< uintT > `[`constcache_inds`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1aabc927d60d479efaa7d16e21e3fff7fd) {#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1aabc927d60d479efaa7d16e21e3fff7fd}

#### `public `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< uintT > `[`level`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1ad4cae37c319469fda89c212c573b33d4) {#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1ad4cae37c319469fda89c212c573b33d4}

#### `public `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< uintT > `[`variable_pos`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1adf916aa7f24f400a959bc9844587f8f1) {#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1adf916aa7f24f400a959bc9844587f8f1}

#### `public `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< uintT > `[`reserved_label`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a73c8633a448ceb4937663740c94f82ed) {#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a73c8633a448ceb4937663740c94f82ed}

#### `public `[`CImgList`](#structcimg__library__suffixed_1_1CImgList)`< charT > `[`variable_def`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1afc1549a689744825235a5a7cb5648cfb) {#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1afc1549a689744825235a5a7cb5648cfb}

#### `public `[`CImgList`](#structcimg__library__suffixed_1_1CImgList)`< charT > `[`macro_def`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a27e1a8a052a765cf08785c444a10b0f3) {#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a27e1a8a052a765cf08785c444a10b0f3}

#### `public `[`CImgList`](#structcimg__library__suffixed_1_1CImgList)`< charT > `[`macro_body`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a935c01ef1959ad35a20a54b512d36522) {#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a935c01ef1959ad35a20a54b512d36522}

#### `public `[`CImgList`](#structcimg__library__suffixed_1_1CImgList)`< boolT > `[`macro_body_is_string`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1ac46543c13dde69685bba79647fa97649) {#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1ac46543c13dde69685bba79647fa97649}

#### `public char * `[`user_macro`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1adb28d6dfa1569c5c1b991efb2ab113bb) {#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1adb28d6dfa1569c5c1b991efb2ab113bb}

#### `public unsigned int `[`mempos`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a5c146b152963764fafaac2ca24fe16c0) {#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a5c146b152963764fafaac2ca24fe16c0}

#### `public unsigned int `[`mem_img_median`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a642ad67b422a62d89dadaebf14035cbc) {#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a642ad67b422a62d89dadaebf14035cbc}

#### `public unsigned int `[`mem_img_index`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a15e0450fdfe1462be41e82f32f220924) {#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a15e0450fdfe1462be41e82f32f220924}

#### `public unsigned int `[`debug_indent`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1acba7d50d228e12f662aa9b6d8d1e696d) {#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1acba7d50d228e12f662aa9b6d8d1e696d}

#### `public unsigned int `[`result_dim`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a0e7796a4fa6f8f4729f34f483beb5f24) {#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a0e7796a4fa6f8f4729f34f483beb5f24}

#### `public unsigned int `[`break_type`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a89b38b787c6469bfe40900141ea5252b) {#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a89b38b787c6469bfe40900141ea5252b}

#### `public unsigned int `[`constcache_size`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a258c34a8cce21382f9a2b5c57987f874) {#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a258c34a8cce21382f9a2b5c57987f874}

#### `public bool `[`is_parallelizable`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1af6e02c4f8e10199173f67a4fc5231f31) {#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1af6e02c4f8e10199173f67a4fc5231f31}

#### `public bool `[`is_end_code`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1ae20054e176c2e131a0c69948daf3b497) {#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1ae20054e176c2e131a0c69948daf3b497}

#### `public bool `[`is_fill`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a2fc55114e1ba46ed83a60fd7f65499ee) {#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a2fc55114e1ba46ed83a60fd7f65499ee}

#### `public bool `[`need_input_copy`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1ada8b588b576249397bc4b3e6f1260a0d) {#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1ada8b588b576249397bc4b3e6f1260a0d}

#### `public double * `[`result`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1aa66554e58545c92fe881935a8725d4e3) {#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1aa66554e58545c92fe881935a8725d4e3}

#### `public cimg_uint64 `[`rng`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a611096d597d953db010a32fed80c5644) {#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a611096d597d953db010a32fed80c5644}

#### `public const char *const `[`calling_function`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a2bd158f818126d2f87a1d1b214459dd0) {#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a2bd158f818126d2f87a1d1b214459dd0}

#### `public const char *const * `[`s_op`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a203276ce7308b0bb54fddf16bf0aa9e5) {#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a203276ce7308b0bb54fddf16bf0aa9e5}

#### `public const char *const * `[`ss_op`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a405dc98771a9120126075b7389993761) {#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a405dc98771a9120126075b7389993761}

#### `public inline  `[`~_cimg_math_parser`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1aa621746641c0461f490da91e4a7e8873)`()` {#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1aa621746641c0461f490da91e4a7e8873}

#### `public inline  `[`_cimg_math_parser`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a591684f81af8ba85885b7de9c0c6ca5f)`(const char *const expression,const char *const funcname,const `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< T > & img_input,`[`CImg`](#structcimg__library__suffixed_1_1CImg)`< T > *const img_output,const `[`CImgList`](#structcimg__library__suffixed_1_1CImgList)`< T > *const list_inputs,`[`CImgList`](#structcimg__library__suffixed_1_1CImgList)`< T > *const list_outputs,const bool _is_fill)` {#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a591684f81af8ba85885b7de9c0c6ca5f}

#### `public inline  `[`_cimg_math_parser`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a51a887a873a637b24f851e5762a88749)`()` {#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a51a887a873a637b24f851e5762a88749}

#### `public inline  `[`_cimg_math_parser`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1acdbfbefd542dbfd59b359aaf512237e2)`(const `[`_cimg_math_parser`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser)` & mp)` {#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1acdbfbefd542dbfd59b359aaf512237e2}

#### `public inline unsigned int `[`compile`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a318c44c5d1f4f0114355f37ace87a4ae)`(char * ss,char * se,const unsigned int depth,unsigned int *const p_ref,const bool is_single)` {#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a318c44c5d1f4f0114355f37ace87a4ae}

#### `public inline double `[`operator()`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1ac9bcfb16c10b216b5d99c4f3bc17225c)`(const double x,const double y,const double z,const double c)` {#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1ac9bcfb16c10b216b5d99c4f3bc17225c}

#### `public template<>`  <br/>`inline void `[`operator()`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1ae6105cf70f00ad11665a67c23c8e7d29)`(const double x,const double y,const double z,const double c,t *const output)` {#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1ae6105cf70f00ad11665a67c23c8e7d29}

#### `public inline void `[`begin_t`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a9a76741901d6903c9d198e5056da96a1)`()` {#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a9a76741901d6903c9d198e5056da96a1}

#### `public inline void `[`end_t`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a5a8bd96525a35656a98d3f4f22a23afb)`()` {#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a5a8bd96525a35656a98d3f4f22a23afb}

#### `public inline void `[`end`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a6707c6d516122d4e601391d6d0d608bc)`()` {#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a6707c6d516122d4e601391d6d0d608bc}

#### `public inline void `[`merge`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a864d0eba43d9505512f7d96ddd71facc)`(`[`_cimg_math_parser`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser)` & mp)` {#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a864d0eba43d9505512f7d96ddd71facc}

#### `public inline `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< charT > `[`s_calling_function`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1ae1b9c43911c79934dc0782d153769b45)`() const` {#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1ae1b9c43911c79934dc0782d153769b45}

#### `public inline `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< charT > `[`s_type`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a2576c21861d4f00e532fd4c562d07615)`(const unsigned int arg) const` {#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a2576c21861d4f00e532fd4c562d07615}

#### `public inline `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< uintT > `[`get_level`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a5cd605113c87e76134db785755492dbb)`(`[`CImg`](#structcimg__library__suffixed_1_1CImg)`< charT > & _expr) const` {#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a5cd605113c87e76134db785755492dbb}

#### `public inline unsigned int `[`get_mem_img_index`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1ac8b1808b2f5da32dd062f924b042c22d)`()` {#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1ac8b1808b2f5da32dd062f924b042c22d}

#### `public inline void `[`get_variable_pos`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1ab29fd288b061b6dacc4db714ab465f96)`(const char * variable_name,unsigned int & pos,unsigned int & rpos)` {#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1ab29fd288b061b6dacc4db714ab465f96}

#### `public inline `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< boolT > `[`is_inside_string`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a320b345dab5cb627c892cf9f9278bd1a)`(`[`CImg`](#structcimg__library__suffixed_1_1CImg)`< charT > & _expr) const` {#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a320b345dab5cb627c892cf9f9278bd1a}

#### `public inline bool `[`is_varchar`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a2631b8f9f5ac6aa3b4e643516cbf8251)`(const char c) const` {#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a2631b8f9f5ac6aa3b4e643516cbf8251}

#### `public inline bool `[`is_comp_vector`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a6561d943a1b6cb866ac72467a837a4c9)`(const unsigned int arg) const` {#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a6561d943a1b6cb866ac72467a837a4c9}

#### `public inline void `[`check_constant`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1ab95626fc3c9df8e9bb3d182328372379)`(const unsigned int arg,const unsigned int n_arg,const unsigned int mode,char *const ss,char *const se,const char saved_char)` {#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1ab95626fc3c9df8e9bb3d182328372379}

#### `public inline void `[`check_constant_index`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a2f2bfbb6c2e3f0c79fc16d1526ec1f95)`(const unsigned int arg,char *const ss,char *const se,const char saved_char)` {#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a2f2bfbb6c2e3f0c79fc16d1526ec1f95}

#### `public inline void `[`check_matrix_square`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a9eaf3a1d2c38a1a1b9275604320fc1cc)`(const unsigned int arg,const unsigned int n_arg,char *const ss,char *const se,const char saved_char)` {#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a9eaf3a1d2c38a1a1b9275604320fc1cc}

#### `public inline void `[`check_type`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1ae5bd43fbdd9ff01b95538fd9958ea79f)`(const unsigned int arg,const unsigned int n_arg,const unsigned int mode,const unsigned int N,char *const ss,char *const se,const char saved_char)` {#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1ae5bd43fbdd9ff01b95538fd9958ea79f}

#### `public inline void `[`check_list`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1af19c9440058cbae77a2d7aafb576fb86)`(const bool is_out,char *const ss,char *const se,const char saved_char)` {#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1af19c9440058cbae77a2d7aafb576fb86}

#### `public inline unsigned int `[`constant`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a1e4b329d6551265b58f355ea6d2229dd)`(const double val)` {#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a1e4b329d6551265b58f355ea6d2229dd}

#### `public inline unsigned int `[`scalar`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a3fbf24a3096da0af2aca688a11feb616)`()` {#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a3fbf24a3096da0af2aca688a11feb616}

#### `public inline unsigned int `[`vector`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1ab3f43a472fa110840243eb500a5b4b2e)`(const unsigned int siz)` {#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1ab3f43a472fa110840243eb500a5b4b2e}

#### `public inline unsigned int `[`vector`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a3a440fb39b9743c44337f4f930f12def)`(const unsigned int siz,const double value)` {#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a3a440fb39b9743c44337f4f930f12def}

#### `public inline unsigned int `[`vector_copy`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a7d9b5b35459bcc94ea2fd2c265b32123)`(const unsigned int arg)` {#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a7d9b5b35459bcc94ea2fd2c265b32123}

#### `public inline void `[`set_variable_vector`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a093e737711b2d78bbfdad351794b5b33)`(const unsigned int arg)` {#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a093e737711b2d78bbfdad351794b5b33}

#### `public inline unsigned int `[`scalar0`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a7e2f883a1d6660c9e233ccfd8e611ae5)`(const mp_func op)` {#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a7e2f883a1d6660c9e233ccfd8e611ae5}

#### `public inline unsigned int `[`scalar1`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a4f752a0ab16ff11f66cbe36c41d28e6e)`(const mp_func op,const unsigned int arg1)` {#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a4f752a0ab16ff11f66cbe36c41d28e6e}

#### `public inline unsigned int `[`scalar2`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a71ad73003cc670f148a36c031bfdb63e)`(const mp_func op,const unsigned int arg1,const unsigned int arg2)` {#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a71ad73003cc670f148a36c031bfdb63e}

#### `public inline unsigned int `[`scalar3`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1ae78d2f0d6168388fca89526501f15fa3)`(const mp_func op,const unsigned int arg1,const unsigned int arg2,const unsigned int arg3)` {#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1ae78d2f0d6168388fca89526501f15fa3}

#### `public inline unsigned int `[`scalar4`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a896a39dea48354d4621c2b3b69ca7937)`(const mp_func op,const unsigned int arg1,const unsigned int arg2,const unsigned int arg3,const unsigned int arg4)` {#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a896a39dea48354d4621c2b3b69ca7937}

#### `public inline unsigned int `[`scalar5`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1ae24ac4a9a45fd573ff49015b81c8576b)`(const mp_func op,const unsigned int arg1,const unsigned int arg2,const unsigned int arg3,const unsigned int arg4,const unsigned int arg5)` {#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1ae24ac4a9a45fd573ff49015b81c8576b}

#### `public inline unsigned int `[`scalar6`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a52ff1d240c30fee48cc0903832a2c6c0)`(const mp_func op,const unsigned int arg1,const unsigned int arg2,const unsigned int arg3,const unsigned int arg4,const unsigned int arg5,const unsigned int arg6)` {#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a52ff1d240c30fee48cc0903832a2c6c0}

#### `public inline unsigned int `[`scalar7`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1ae095d22c230ed8cb9760fad0a797569a)`(const mp_func op,const unsigned int arg1,const unsigned int arg2,const unsigned int arg3,const unsigned int arg4,const unsigned int arg5,const unsigned int arg6,const unsigned int arg7)` {#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1ae095d22c230ed8cb9760fad0a797569a}

#### `public inline void `[`self_vector_s`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1aad42f4efe4a29c92c651b44879c639f5)`(const unsigned int pos,const mp_func op,const unsigned int arg1)` {#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1aad42f4efe4a29c92c651b44879c639f5}

#### `public inline void `[`self_vector_v`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1ab0821949940cfb53f3ddfa5e39e3ca6d)`(const unsigned int pos,const mp_func op,const unsigned int arg1)` {#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1ab0821949940cfb53f3ddfa5e39e3ca6d}

#### `public inline unsigned int `[`vector1_v`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1aa7cca47d009b3663c2a14aa9307d2ba1)`(const mp_func op,const unsigned int arg1)` {#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1aa7cca47d009b3663c2a14aa9307d2ba1}

#### `public inline unsigned int `[`vector2_vv`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a930d4d9bb7ea4f7f64283e60f7722139)`(const mp_func op,const unsigned int arg1,const unsigned int arg2)` {#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a930d4d9bb7ea4f7f64283e60f7722139}

#### `public inline unsigned int `[`vector2_vs`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1af3073ae1f236be6068d46c7651a2c2d6)`(const mp_func op,const unsigned int arg1,const unsigned int arg2)` {#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1af3073ae1f236be6068d46c7651a2c2d6}

#### `public inline unsigned int `[`vector2_sv`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a149ded260ecf0cef762feaa47e827077)`(const mp_func op,const unsigned int arg1,const unsigned int arg2)` {#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a149ded260ecf0cef762feaa47e827077}

#### `public inline unsigned int `[`vector3_vss`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a56491c4fefa5379b35ce87f4654c6001)`(const mp_func op,const unsigned int arg1,const unsigned int arg2,const unsigned int arg3)` {#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a56491c4fefa5379b35ce87f4654c6001}

#### `typedef `[`mp_func`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a220deac105e68eef2ee2e612c96a0f75) {#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser_1a220deac105e68eef2ee2e612c96a0f75}

# struct `cimg_library_suffixed::CImg::_functor2d_expr` {#structcimg__library__suffixed_1_1CImg_1_1__functor2d__expr}

<h2> Summary </h2>

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`public `[`_cimg_math_parser`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser)` * `[`mp`](#structcimg__library__suffixed_1_1CImg_1_1__functor2d__expr_1a326bbd383e5bdaf8c37bfa3cfdf16442) | 
`public inline  `[`~_functor2d_expr`](#structcimg__library__suffixed_1_1CImg_1_1__functor2d__expr_1aa62f7b3ab95d5897ec18a179b2777dfa)`()` | 
`public inline  `[`_functor2d_expr`](#structcimg__library__suffixed_1_1CImg_1_1__functor2d__expr_1a281d2130c226e23e6f3f2491d8ff60b3)`(const char *const expr)` | 
`public inline float `[`operator()`](#structcimg__library__suffixed_1_1CImg_1_1__functor2d__expr_1ae7f97b320d95d5c03e58696b08fafc52)`(const float x,const float y) const` | 

<h2> Members </h2>

#### `public `[`_cimg_math_parser`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser)` * `[`mp`](#structcimg__library__suffixed_1_1CImg_1_1__functor2d__expr_1a326bbd383e5bdaf8c37bfa3cfdf16442) {#structcimg__library__suffixed_1_1CImg_1_1__functor2d__expr_1a326bbd383e5bdaf8c37bfa3cfdf16442}

#### `public inline  `[`~_functor2d_expr`](#structcimg__library__suffixed_1_1CImg_1_1__functor2d__expr_1aa62f7b3ab95d5897ec18a179b2777dfa)`()` {#structcimg__library__suffixed_1_1CImg_1_1__functor2d__expr_1aa62f7b3ab95d5897ec18a179b2777dfa}

#### `public inline  `[`_functor2d_expr`](#structcimg__library__suffixed_1_1CImg_1_1__functor2d__expr_1a281d2130c226e23e6f3f2491d8ff60b3)`(const char *const expr)` {#structcimg__library__suffixed_1_1CImg_1_1__functor2d__expr_1a281d2130c226e23e6f3f2491d8ff60b3}

#### `public inline float `[`operator()`](#structcimg__library__suffixed_1_1CImg_1_1__functor2d__expr_1ae7f97b320d95d5c03e58696b08fafc52)`(const float x,const float y) const` {#structcimg__library__suffixed_1_1CImg_1_1__functor2d__expr_1ae7f97b320d95d5c03e58696b08fafc52}

# struct `cimg_library_suffixed::CImg::_functor2d_float` {#structcimg__library__suffixed_1_1CImg_1_1__functor2d__float}

<h2> Summary </h2>

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`public const `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< T > & `[`ref`](#structcimg__library__suffixed_1_1CImg_1_1__functor2d__float_1a6ea8592ea6d6bdc7b0e95d3f72a4aa20) | 
`public inline  `[`_functor2d_float`](#structcimg__library__suffixed_1_1CImg_1_1__functor2d__float_1a3f5fbc638004f436de102e91e7c7815f)`(const `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< T > & pref)` | 
`public inline float `[`operator()`](#structcimg__library__suffixed_1_1CImg_1_1__functor2d__float_1a07d3963f01f4588d37b9d5de00ce686c)`(const float x,const float y) const` | 

<h2> Members </h2>

#### `public const `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< T > & `[`ref`](#structcimg__library__suffixed_1_1CImg_1_1__functor2d__float_1a6ea8592ea6d6bdc7b0e95d3f72a4aa20) {#structcimg__library__suffixed_1_1CImg_1_1__functor2d__float_1a6ea8592ea6d6bdc7b0e95d3f72a4aa20}

#### `public inline  `[`_functor2d_float`](#structcimg__library__suffixed_1_1CImg_1_1__functor2d__float_1a3f5fbc638004f436de102e91e7c7815f)`(const `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< T > & pref)` {#structcimg__library__suffixed_1_1CImg_1_1__functor2d__float_1a3f5fbc638004f436de102e91e7c7815f}

#### `public inline float `[`operator()`](#structcimg__library__suffixed_1_1CImg_1_1__functor2d__float_1a07d3963f01f4588d37b9d5de00ce686c)`(const float x,const float y) const` {#structcimg__library__suffixed_1_1CImg_1_1__functor2d__float_1a07d3963f01f4588d37b9d5de00ce686c}

# struct `cimg_library_suffixed::CImg::_functor2d_int` {#structcimg__library__suffixed_1_1CImg_1_1__functor2d__int}

<h2> Summary </h2>

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`public const `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< T > & `[`ref`](#structcimg__library__suffixed_1_1CImg_1_1__functor2d__int_1a952a4a6b8aea9d7fe271512db336a0bf) | 
`public inline  `[`_functor2d_int`](#structcimg__library__suffixed_1_1CImg_1_1__functor2d__int_1a074e1ac30146d816693b3f59bcb9f14a)`(const `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< T > & pref)` | 
`public inline float `[`operator()`](#structcimg__library__suffixed_1_1CImg_1_1__functor2d__int_1a32a5f7766c10e90a78d2b64aa8303233)`(const float x,const float y) const` | 

<h2> Members </h2>

#### `public const `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< T > & `[`ref`](#structcimg__library__suffixed_1_1CImg_1_1__functor2d__int_1a952a4a6b8aea9d7fe271512db336a0bf) {#structcimg__library__suffixed_1_1CImg_1_1__functor2d__int_1a952a4a6b8aea9d7fe271512db336a0bf}

#### `public inline  `[`_functor2d_int`](#structcimg__library__suffixed_1_1CImg_1_1__functor2d__int_1a074e1ac30146d816693b3f59bcb9f14a)`(const `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< T > & pref)` {#structcimg__library__suffixed_1_1CImg_1_1__functor2d__int_1a074e1ac30146d816693b3f59bcb9f14a}

#### `public inline float `[`operator()`](#structcimg__library__suffixed_1_1CImg_1_1__functor2d__int_1a32a5f7766c10e90a78d2b64aa8303233)`(const float x,const float y) const` {#structcimg__library__suffixed_1_1CImg_1_1__functor2d__int_1a32a5f7766c10e90a78d2b64aa8303233}

# struct `cimg_library_suffixed::CImg::_functor3d_expr` {#structcimg__library__suffixed_1_1CImg_1_1__functor3d__expr}

<h2> Summary </h2>

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`public `[`_cimg_math_parser`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser)` * `[`mp`](#structcimg__library__suffixed_1_1CImg_1_1__functor3d__expr_1a13d32c6406780bb120d469b0a401d86a) | 
`public inline  `[`~_functor3d_expr`](#structcimg__library__suffixed_1_1CImg_1_1__functor3d__expr_1a06b123f343ca7d0805a8ef4b7544ed80)`()` | 
`public inline  `[`_functor3d_expr`](#structcimg__library__suffixed_1_1CImg_1_1__functor3d__expr_1a5a4b87e578cd3812e35ba9e9ae540a75)`(const char *const expr)` | 
`public inline float `[`operator()`](#structcimg__library__suffixed_1_1CImg_1_1__functor3d__expr_1af766dab4864f9b794f51102234f02d75)`(const float x,const float y,const float z) const` | 

<h2> Members </h2>

#### `public `[`_cimg_math_parser`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser)` * `[`mp`](#structcimg__library__suffixed_1_1CImg_1_1__functor3d__expr_1a13d32c6406780bb120d469b0a401d86a) {#structcimg__library__suffixed_1_1CImg_1_1__functor3d__expr_1a13d32c6406780bb120d469b0a401d86a}

#### `public inline  `[`~_functor3d_expr`](#structcimg__library__suffixed_1_1CImg_1_1__functor3d__expr_1a06b123f343ca7d0805a8ef4b7544ed80)`()` {#structcimg__library__suffixed_1_1CImg_1_1__functor3d__expr_1a06b123f343ca7d0805a8ef4b7544ed80}

#### `public inline  `[`_functor3d_expr`](#structcimg__library__suffixed_1_1CImg_1_1__functor3d__expr_1a5a4b87e578cd3812e35ba9e9ae540a75)`(const char *const expr)` {#structcimg__library__suffixed_1_1CImg_1_1__functor3d__expr_1a5a4b87e578cd3812e35ba9e9ae540a75}

#### `public inline float `[`operator()`](#structcimg__library__suffixed_1_1CImg_1_1__functor3d__expr_1af766dab4864f9b794f51102234f02d75)`(const float x,const float y,const float z) const` {#structcimg__library__suffixed_1_1CImg_1_1__functor3d__expr_1af766dab4864f9b794f51102234f02d75}

# struct `cimg_library_suffixed::CImg::_functor3d_float` {#structcimg__library__suffixed_1_1CImg_1_1__functor3d__float}

<h2> Summary </h2>

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`public const `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< T > & `[`ref`](#structcimg__library__suffixed_1_1CImg_1_1__functor3d__float_1a531d8e028bb752be2629ff14f9fc6a37) | 
`public inline  `[`_functor3d_float`](#structcimg__library__suffixed_1_1CImg_1_1__functor3d__float_1ae04ad42104133ff47ef65a564e49e73c)`(const `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< T > & pref)` | 
`public inline float `[`operator()`](#structcimg__library__suffixed_1_1CImg_1_1__functor3d__float_1a46ac056612fddb7feeeecca759b7988f)`(const float x,const float y,const float z) const` | 

<h2> Members </h2>

#### `public const `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< T > & `[`ref`](#structcimg__library__suffixed_1_1CImg_1_1__functor3d__float_1a531d8e028bb752be2629ff14f9fc6a37) {#structcimg__library__suffixed_1_1CImg_1_1__functor3d__float_1a531d8e028bb752be2629ff14f9fc6a37}

#### `public inline  `[`_functor3d_float`](#structcimg__library__suffixed_1_1CImg_1_1__functor3d__float_1ae04ad42104133ff47ef65a564e49e73c)`(const `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< T > & pref)` {#structcimg__library__suffixed_1_1CImg_1_1__functor3d__float_1ae04ad42104133ff47ef65a564e49e73c}

#### `public inline float `[`operator()`](#structcimg__library__suffixed_1_1CImg_1_1__functor3d__float_1a46ac056612fddb7feeeecca759b7988f)`(const float x,const float y,const float z) const` {#structcimg__library__suffixed_1_1CImg_1_1__functor3d__float_1a46ac056612fddb7feeeecca759b7988f}

# struct `cimg_library_suffixed::CImg::_functor3d_int` {#structcimg__library__suffixed_1_1CImg_1_1__functor3d__int}

<h2> Summary </h2>

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`public const `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< T > & `[`ref`](#structcimg__library__suffixed_1_1CImg_1_1__functor3d__int_1a9706d22ee054bd7e0434e847989f6726) | 
`public inline  `[`_functor3d_int`](#structcimg__library__suffixed_1_1CImg_1_1__functor3d__int_1aa92ae8b290434512ecee05188c3d34cc)`(const `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< T > & pref)` | 
`public inline float `[`operator()`](#structcimg__library__suffixed_1_1CImg_1_1__functor3d__int_1a75c4ca89b7aa725ad9e5144606b31a98)`(const float x,const float y,const float z) const` | 

<h2> Members </h2>

#### `public const `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< T > & `[`ref`](#structcimg__library__suffixed_1_1CImg_1_1__functor3d__int_1a9706d22ee054bd7e0434e847989f6726) {#structcimg__library__suffixed_1_1CImg_1_1__functor3d__int_1a9706d22ee054bd7e0434e847989f6726}

#### `public inline  `[`_functor3d_int`](#structcimg__library__suffixed_1_1CImg_1_1__functor3d__int_1aa92ae8b290434512ecee05188c3d34cc)`(const `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< T > & pref)` {#structcimg__library__suffixed_1_1CImg_1_1__functor3d__int_1aa92ae8b290434512ecee05188c3d34cc}

#### `public inline float `[`operator()`](#structcimg__library__suffixed_1_1CImg_1_1__functor3d__int_1a75c4ca89b7aa725ad9e5144606b31a98)`(const float x,const float y,const float z) const` {#structcimg__library__suffixed_1_1CImg_1_1__functor3d__int_1a75c4ca89b7aa725ad9e5144606b31a98}

# struct `cimg_library_suffixed::CImg::_functor4d_int` {#structcimg__library__suffixed_1_1CImg_1_1__functor4d__int}

<h2> Summary </h2>

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`public const `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< T > & `[`ref`](#structcimg__library__suffixed_1_1CImg_1_1__functor4d__int_1a6c9cfad39fcfbb4617efdd5e33509d46) | 
`public inline  `[`_functor4d_int`](#structcimg__library__suffixed_1_1CImg_1_1__functor4d__int_1a497876b7332984108b6ae60b9bd3a1ce)`(const `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< T > & pref)` | 
`public inline float `[`operator()`](#structcimg__library__suffixed_1_1CImg_1_1__functor4d__int_1a948af15f62a8c8270cfcd5c5eee59ad6)`(const float x,const float y,const float z,const unsigned int c) const` | 

<h2> Members </h2>

#### `public const `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< T > & `[`ref`](#structcimg__library__suffixed_1_1CImg_1_1__functor4d__int_1a6c9cfad39fcfbb4617efdd5e33509d46) {#structcimg__library__suffixed_1_1CImg_1_1__functor4d__int_1a6c9cfad39fcfbb4617efdd5e33509d46}

#### `public inline  `[`_functor4d_int`](#structcimg__library__suffixed_1_1CImg_1_1__functor4d__int_1a497876b7332984108b6ae60b9bd3a1ce)`(const `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< T > & pref)` {#structcimg__library__suffixed_1_1CImg_1_1__functor4d__int_1a497876b7332984108b6ae60b9bd3a1ce}

#### `public inline float `[`operator()`](#structcimg__library__suffixed_1_1CImg_1_1__functor4d__int_1a948af15f62a8c8270cfcd5c5eee59ad6)`(const float x,const float y,const float z,const unsigned int c) const` {#structcimg__library__suffixed_1_1CImg_1_1__functor4d__int_1a948af15f62a8c8270cfcd5c5eee59ad6}

# struct `cimg_library_suffixed::CImg::_functor4d_streamline2d_directed` {#structcimg__library__suffixed_1_1CImg_1_1__functor4d__streamline2d__directed}

<h2> Summary </h2>

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`public const `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< T > & `[`ref`](#structcimg__library__suffixed_1_1CImg_1_1__functor4d__streamline2d__directed_1a83088592588a54fe8db896605d614fe0) | 
`public inline  `[`_functor4d_streamline2d_directed`](#structcimg__library__suffixed_1_1CImg_1_1__functor4d__streamline2d__directed_1a1f75ad71877ddbcd7ae34cac3ed1145c)`(const `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< T > & pref)` | 
`public inline float `[`operator()`](#structcimg__library__suffixed_1_1CImg_1_1__functor4d__streamline2d__directed_1a76002cc085d76e1d4e1f24e151849790)`(const float x,const float y,const float z,const unsigned int c) const` | 

<h2> Members </h2>

#### `public const `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< T > & `[`ref`](#structcimg__library__suffixed_1_1CImg_1_1__functor4d__streamline2d__directed_1a83088592588a54fe8db896605d614fe0) {#structcimg__library__suffixed_1_1CImg_1_1__functor4d__streamline2d__directed_1a83088592588a54fe8db896605d614fe0}

#### `public inline  `[`_functor4d_streamline2d_directed`](#structcimg__library__suffixed_1_1CImg_1_1__functor4d__streamline2d__directed_1a1f75ad71877ddbcd7ae34cac3ed1145c)`(const `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< T > & pref)` {#structcimg__library__suffixed_1_1CImg_1_1__functor4d__streamline2d__directed_1a1f75ad71877ddbcd7ae34cac3ed1145c}

#### `public inline float `[`operator()`](#structcimg__library__suffixed_1_1CImg_1_1__functor4d__streamline2d__directed_1a76002cc085d76e1d4e1f24e151849790)`(const float x,const float y,const float z,const unsigned int c) const` {#structcimg__library__suffixed_1_1CImg_1_1__functor4d__streamline2d__directed_1a76002cc085d76e1d4e1f24e151849790}

# struct `cimg_library_suffixed::CImg::_functor4d_streamline2d_oriented` {#structcimg__library__suffixed_1_1CImg_1_1__functor4d__streamline2d__oriented}

<h2> Summary </h2>

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`public const `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< T > & `[`ref`](#structcimg__library__suffixed_1_1CImg_1_1__functor4d__streamline2d__oriented_1af5aa2bceac87392a9697224e2937e951) | 
`public `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< floatT > * `[`pI`](#structcimg__library__suffixed_1_1CImg_1_1__functor4d__streamline2d__oriented_1afe07c57a8dac96c0bca4b4291544be0a) | 
`public inline  `[`_functor4d_streamline2d_oriented`](#structcimg__library__suffixed_1_1CImg_1_1__functor4d__streamline2d__oriented_1a9a249a9654fe898ee66e6eb6802a4b88)`(const `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< T > & pref)` | 
`public inline  `[`~_functor4d_streamline2d_oriented`](#structcimg__library__suffixed_1_1CImg_1_1__functor4d__streamline2d__oriented_1aeddf9296566b38b1c7238dfee819a9e1)`()` | 
`public inline float `[`operator()`](#structcimg__library__suffixed_1_1CImg_1_1__functor4d__streamline2d__oriented_1aaf4ebdef352f0c57658a8ca758633519)`(const float x,const float y,const float z,const unsigned int c) const` | 

<h2> Members </h2>

#### `public const `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< T > & `[`ref`](#structcimg__library__suffixed_1_1CImg_1_1__functor4d__streamline2d__oriented_1af5aa2bceac87392a9697224e2937e951) {#structcimg__library__suffixed_1_1CImg_1_1__functor4d__streamline2d__oriented_1af5aa2bceac87392a9697224e2937e951}

#### `public `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< floatT > * `[`pI`](#structcimg__library__suffixed_1_1CImg_1_1__functor4d__streamline2d__oriented_1afe07c57a8dac96c0bca4b4291544be0a) {#structcimg__library__suffixed_1_1CImg_1_1__functor4d__streamline2d__oriented_1afe07c57a8dac96c0bca4b4291544be0a}

#### `public inline  `[`_functor4d_streamline2d_oriented`](#structcimg__library__suffixed_1_1CImg_1_1__functor4d__streamline2d__oriented_1a9a249a9654fe898ee66e6eb6802a4b88)`(const `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< T > & pref)` {#structcimg__library__suffixed_1_1CImg_1_1__functor4d__streamline2d__oriented_1a9a249a9654fe898ee66e6eb6802a4b88}

#### `public inline  `[`~_functor4d_streamline2d_oriented`](#structcimg__library__suffixed_1_1CImg_1_1__functor4d__streamline2d__oriented_1aeddf9296566b38b1c7238dfee819a9e1)`()` {#structcimg__library__suffixed_1_1CImg_1_1__functor4d__streamline2d__oriented_1aeddf9296566b38b1c7238dfee819a9e1}

#### `public inline float `[`operator()`](#structcimg__library__suffixed_1_1CImg_1_1__functor4d__streamline2d__oriented_1aaf4ebdef352f0c57658a8ca758633519)`(const float x,const float y,const float z,const unsigned int c) const` {#structcimg__library__suffixed_1_1CImg_1_1__functor4d__streamline2d__oriented_1aaf4ebdef352f0c57658a8ca758633519}

# struct `cimg_library_suffixed::CImg::_functor4d_streamline3d_directed` {#structcimg__library__suffixed_1_1CImg_1_1__functor4d__streamline3d__directed}

<h2> Summary </h2>

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`public const `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< T > & `[`ref`](#structcimg__library__suffixed_1_1CImg_1_1__functor4d__streamline3d__directed_1a1388dcdcefe2dbf80bacf81e4fb29673) | 
`public inline  `[`_functor4d_streamline3d_directed`](#structcimg__library__suffixed_1_1CImg_1_1__functor4d__streamline3d__directed_1ae6cf32c7a4e1b38bf10befe1c8256759)`(const `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< T > & pref)` | 
`public inline float `[`operator()`](#structcimg__library__suffixed_1_1CImg_1_1__functor4d__streamline3d__directed_1a5bd756077b8bcad71a8a24c4e0619d70)`(const float x,const float y,const float z,const unsigned int c) const` | 

<h2> Members </h2>

#### `public const `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< T > & `[`ref`](#structcimg__library__suffixed_1_1CImg_1_1__functor4d__streamline3d__directed_1a1388dcdcefe2dbf80bacf81e4fb29673) {#structcimg__library__suffixed_1_1CImg_1_1__functor4d__streamline3d__directed_1a1388dcdcefe2dbf80bacf81e4fb29673}

#### `public inline  `[`_functor4d_streamline3d_directed`](#structcimg__library__suffixed_1_1CImg_1_1__functor4d__streamline3d__directed_1ae6cf32c7a4e1b38bf10befe1c8256759)`(const `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< T > & pref)` {#structcimg__library__suffixed_1_1CImg_1_1__functor4d__streamline3d__directed_1ae6cf32c7a4e1b38bf10befe1c8256759}

#### `public inline float `[`operator()`](#structcimg__library__suffixed_1_1CImg_1_1__functor4d__streamline3d__directed_1a5bd756077b8bcad71a8a24c4e0619d70)`(const float x,const float y,const float z,const unsigned int c) const` {#structcimg__library__suffixed_1_1CImg_1_1__functor4d__streamline3d__directed_1a5bd756077b8bcad71a8a24c4e0619d70}

# struct `cimg_library_suffixed::CImg::_functor4d_streamline3d_oriented` {#structcimg__library__suffixed_1_1CImg_1_1__functor4d__streamline3d__oriented}

<h2> Summary </h2>

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`public const `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< T > & `[`ref`](#structcimg__library__suffixed_1_1CImg_1_1__functor4d__streamline3d__oriented_1a9d776659c2fdbddec7a8e980a37c0605) | 
`public `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< floatT > * `[`pI`](#structcimg__library__suffixed_1_1CImg_1_1__functor4d__streamline3d__oriented_1ab0942d28e7db2c3130a6051abeb2d6f4) | 
`public inline  `[`_functor4d_streamline3d_oriented`](#structcimg__library__suffixed_1_1CImg_1_1__functor4d__streamline3d__oriented_1a802e4860ae942bde89b9a276aa09d7dc)`(const `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< T > & pref)` | 
`public inline  `[`~_functor4d_streamline3d_oriented`](#structcimg__library__suffixed_1_1CImg_1_1__functor4d__streamline3d__oriented_1ac6d6807bfefa6e1a7b08f31d9d0fc3f1)`()` | 
`public inline float `[`operator()`](#structcimg__library__suffixed_1_1CImg_1_1__functor4d__streamline3d__oriented_1a67b32f469586ab13a6f39fba6910f3d8)`(const float x,const float y,const float z,const unsigned int c) const` | 

<h2> Members </h2>

#### `public const `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< T > & `[`ref`](#structcimg__library__suffixed_1_1CImg_1_1__functor4d__streamline3d__oriented_1a9d776659c2fdbddec7a8e980a37c0605) {#structcimg__library__suffixed_1_1CImg_1_1__functor4d__streamline3d__oriented_1a9d776659c2fdbddec7a8e980a37c0605}

#### `public `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< floatT > * `[`pI`](#structcimg__library__suffixed_1_1CImg_1_1__functor4d__streamline3d__oriented_1ab0942d28e7db2c3130a6051abeb2d6f4) {#structcimg__library__suffixed_1_1CImg_1_1__functor4d__streamline3d__oriented_1ab0942d28e7db2c3130a6051abeb2d6f4}

#### `public inline  `[`_functor4d_streamline3d_oriented`](#structcimg__library__suffixed_1_1CImg_1_1__functor4d__streamline3d__oriented_1a802e4860ae942bde89b9a276aa09d7dc)`(const `[`CImg`](#structcimg__library__suffixed_1_1CImg)`< T > & pref)` {#structcimg__library__suffixed_1_1CImg_1_1__functor4d__streamline3d__oriented_1a802e4860ae942bde89b9a276aa09d7dc}

#### `public inline  `[`~_functor4d_streamline3d_oriented`](#structcimg__library__suffixed_1_1CImg_1_1__functor4d__streamline3d__oriented_1ac6d6807bfefa6e1a7b08f31d9d0fc3f1)`()` {#structcimg__library__suffixed_1_1CImg_1_1__functor4d__streamline3d__oriented_1ac6d6807bfefa6e1a7b08f31d9d0fc3f1}

#### `public inline float `[`operator()`](#structcimg__library__suffixed_1_1CImg_1_1__functor4d__streamline3d__oriented_1a67b32f469586ab13a6f39fba6910f3d8)`(const float x,const float y,const float z,const unsigned int c) const` {#structcimg__library__suffixed_1_1CImg_1_1__functor4d__streamline3d__oriented_1a67b32f469586ab13a6f39fba6910f3d8}

# struct `cimg_library_suffixed::CImg::_functor4d_streamline_expr` {#structcimg__library__suffixed_1_1CImg_1_1__functor4d__streamline__expr}

<h2> Summary </h2>

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`public `[`_cimg_math_parser`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser)` * `[`mp`](#structcimg__library__suffixed_1_1CImg_1_1__functor4d__streamline__expr_1a6a076746dae7afecdab342a31bc4f783) | 
`public inline  `[`~_functor4d_streamline_expr`](#structcimg__library__suffixed_1_1CImg_1_1__functor4d__streamline__expr_1ab73048a58fd20fe9586f11445227a0b1)`()` | 
`public inline  `[`_functor4d_streamline_expr`](#structcimg__library__suffixed_1_1CImg_1_1__functor4d__streamline__expr_1a705878a3cc11c1f31b217fa036fa208d)`(const char *const expr)` | 
`public inline float `[`operator()`](#structcimg__library__suffixed_1_1CImg_1_1__functor4d__streamline__expr_1a1d8e76a4547c9d0289e43f6d3e7a23d7)`(const float x,const float y,const float z,const unsigned int c) const` | 

<h2> Members </h2>

#### `public `[`_cimg_math_parser`](#structcimg__library__suffixed_1_1CImg_1_1__cimg__math__parser)` * `[`mp`](#structcimg__library__suffixed_1_1CImg_1_1__functor4d__streamline__expr_1a6a076746dae7afecdab342a31bc4f783) {#structcimg__library__suffixed_1_1CImg_1_1__functor4d__streamline__expr_1a6a076746dae7afecdab342a31bc4f783}

#### `public inline  `[`~_functor4d_streamline_expr`](#structcimg__library__suffixed_1_1CImg_1_1__functor4d__streamline__expr_1ab73048a58fd20fe9586f11445227a0b1)`()` {#structcimg__library__suffixed_1_1CImg_1_1__functor4d__streamline__expr_1ab73048a58fd20fe9586f11445227a0b1}

#### `public inline  `[`_functor4d_streamline_expr`](#structcimg__library__suffixed_1_1CImg_1_1__functor4d__streamline__expr_1a705878a3cc11c1f31b217fa036fa208d)`(const char *const expr)` {#structcimg__library__suffixed_1_1CImg_1_1__functor4d__streamline__expr_1a705878a3cc11c1f31b217fa036fa208d}

#### `public inline float `[`operator()`](#structcimg__library__suffixed_1_1CImg_1_1__functor4d__streamline__expr_1a1d8e76a4547c9d0289e43f6d3e7a23d7)`(const float x,const float y,const float z,const unsigned int c) const` {#structcimg__library__suffixed_1_1CImg_1_1__functor4d__streamline__expr_1a1d8e76a4547c9d0289e43f6d3e7a23d7}

# struct `cimg_library_suffixed::CImg::_functor_isoline3d` {#structcimg__library__suffixed_1_1CImg_1_1__functor__isoline3d}

<h2> Summary </h2>

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`public `[`CImgList`](#structcimg__library__suffixed_1_1CImgList)`< T > & `[`list`](#structcimg__library__suffixed_1_1CImg_1_1__functor__isoline3d_1a2ffb996235d6dd8da54ccf9ecb8db777) | 
`public inline  `[`_functor_isoline3d`](#structcimg__library__suffixed_1_1CImg_1_1__functor__isoline3d_1a1a080527eccc7954e54929e34e8d81dd)`(`[`CImgList`](#structcimg__library__suffixed_1_1CImgList)`< T > & _list)` | 
`public template<>`  <br/>`inline void `[`operator()`](#structcimg__library__suffixed_1_1CImg_1_1__functor__isoline3d_1aaf4dbf011fffc9d41930254feaaa9093)`(const t x,const t y,const t z)` | 
`public template<>`  <br/>`inline void `[`operator()`](#structcimg__library__suffixed_1_1CImg_1_1__functor__isoline3d_1a82a0d318e94e9be6a01faf309df584a3)`(const t i,const t j)` | 

<h2> Members </h2>

#### `public `[`CImgList`](#structcimg__library__suffixed_1_1CImgList)`< T > & `[`list`](#structcimg__library__suffixed_1_1CImg_1_1__functor__isoline3d_1a2ffb996235d6dd8da54ccf9ecb8db777) {#structcimg__library__suffixed_1_1CImg_1_1__functor__isoline3d_1a2ffb996235d6dd8da54ccf9ecb8db777}

#### `public inline  `[`_functor_isoline3d`](#structcimg__library__suffixed_1_1CImg_1_1__functor__isoline3d_1a1a080527eccc7954e54929e34e8d81dd)`(`[`CImgList`](#structcimg__library__suffixed_1_1CImgList)`< T > & _list)` {#structcimg__library__suffixed_1_1CImg_1_1__functor__isoline3d_1a1a080527eccc7954e54929e34e8d81dd}

#### `public template<>`  <br/>`inline void `[`operator()`](#structcimg__library__suffixed_1_1CImg_1_1__functor__isoline3d_1aaf4dbf011fffc9d41930254feaaa9093)`(const t x,const t y,const t z)` {#structcimg__library__suffixed_1_1CImg_1_1__functor__isoline3d_1aaf4dbf011fffc9d41930254feaaa9093}

#### `public template<>`  <br/>`inline void `[`operator()`](#structcimg__library__suffixed_1_1CImg_1_1__functor__isoline3d_1a82a0d318e94e9be6a01faf309df584a3)`(const t i,const t j)` {#structcimg__library__suffixed_1_1CImg_1_1__functor__isoline3d_1a82a0d318e94e9be6a01faf309df584a3}

# struct `cimg_library_suffixed::CImg::_functor_isosurface3d` {#structcimg__library__suffixed_1_1CImg_1_1__functor__isosurface3d}

<h2> Summary </h2>

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`public `[`CImgList`](#structcimg__library__suffixed_1_1CImgList)`< T > & `[`list`](#structcimg__library__suffixed_1_1CImg_1_1__functor__isosurface3d_1a4aa77a03319b942082488bda916333e6) | 
`public inline  `[`_functor_isosurface3d`](#structcimg__library__suffixed_1_1CImg_1_1__functor__isosurface3d_1a67c61dfb6c3c82167804b486f34cfba6)`(`[`CImgList`](#structcimg__library__suffixed_1_1CImgList)`< T > & _list)` | 
`public template<>`  <br/>`inline void `[`operator()`](#structcimg__library__suffixed_1_1CImg_1_1__functor__isosurface3d_1acdef7c1d729fa5b085203496b194d8fa)`(const t x,const t y,const t z)` | 

<h2> Members </h2>

#### `public `[`CImgList`](#structcimg__library__suffixed_1_1CImgList)`< T > & `[`list`](#structcimg__library__suffixed_1_1CImg_1_1__functor__isosurface3d_1a4aa77a03319b942082488bda916333e6) {#structcimg__library__suffixed_1_1CImg_1_1__functor__isosurface3d_1a4aa77a03319b942082488bda916333e6}

#### `public inline  `[`_functor_isosurface3d`](#structcimg__library__suffixed_1_1CImg_1_1__functor__isosurface3d_1a67c61dfb6c3c82167804b486f34cfba6)`(`[`CImgList`](#structcimg__library__suffixed_1_1CImgList)`< T > & _list)` {#structcimg__library__suffixed_1_1CImg_1_1__functor__isosurface3d_1a67c61dfb6c3c82167804b486f34cfba6}

#### `public template<>`  <br/>`inline void `[`operator()`](#structcimg__library__suffixed_1_1CImg_1_1__functor__isosurface3d_1acdef7c1d729fa5b085203496b194d8fa)`(const t x,const t y,const t z)` {#structcimg__library__suffixed_1_1CImg_1_1__functor__isosurface3d_1acdef7c1d729fa5b085203496b194d8fa}

Generated by [Moxygen](https://sourcey.com/moxygen)