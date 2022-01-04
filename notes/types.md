Using D Built-in Types
=======================

## Built-in Scalar Types

D has these familiar built-in scalar types:

|Type|Definition|Initial Value|
|----|----------|-------------|
|bool|Boolean type|false|
|byte|signed 8 bits|0|
|ubyte|unsigned 8 bits|0|
|short|signed short int 16 bits|0|
|ushort|unsigned short int 16 bits|0|
|int|signed 32 bits|0|
|uint|unsigned 32 bits|0|
|long|signed 64 bits|0L|
|ulong|unsigned 64 bits|0LU|
|float|32-bit floating point|float.nan|
|double|64-bit floating point|double.nan|
|real|either the largest floating point type that the hardware supports or double, whichever is larger|real.nan|
|ifloat|imaginary value type of float|float.nan * 1.0i|
|idouble|imaginary value type of double|double.nan * 1.0i|
|ireal|imaginary value type of real|real.nan * 1.0i|
|cfloat|complex number type made of two floats|float.nan + float.nan * 1.0i|
|cdouble|complex number type made of two doubles|double.nan + double.nan * 1.0i|
|creal|complex number type made of two reals|real.nan + real.nan * 1.0i|
|char|UTF-8 code unit|0xFF|
|wchar|UTF-16 code unit|0xFFFF|
|dchar|UTF-32 code unit and Unicode code point|0x0000FFFF|

## Properties of Types in D

### Properties of All Types

| Property|Description|
|---------|-----------|
|.init|initializer|
.sizeof	size in bytes
|.alignof|alignment size|
|.mangleof|string representing the ‘mangled’ representation of the type|
|.stringof|string representing the source representation of the type|

### Properties for Integral Types

|Property|Description|
|--------|----------|
|.init|initializer|
|.max|maximum value|
|.min|minimum value|

### Properties for Floating Point Types

|Property|Description|
|--------|----------|
|.init|initializer (NaN)|
|.infinity|infinity value|
|.nan|NaN value|
|.dig|number of decimal digits of precision|
|.epsilon|smallest increment to the value 1|
|.mant_dig|number of bits in mantissa|
|.max_10_exp|maximum int value such that 10max_10_exp is representable|
|.max_exp|maximum int value such that 2max_exp-1 is representable|
|.min_10_exp|minimum int value such that 10min_10_exp is representable as a normalized value|
|.min_exp|minimum int value such that 2min_exp-1 is representable as a normalized value|
|.max|largest representable value that's not infinity|
|.min_normal|smallest representable normalized value that's not 0|
|.re|real part|
|.im|imaginary part|

### Properties for Class Types

|Property|Description|
|--------|-----------|
|.classinfo|Information about the dynamic type of the class|

Built-in types do has the following properties:

For details on implicit type promptions

## Other Built-in Types

As explained in [D Builtin Rationale](https://dlang.org/articles/builtin.html), D has three other built-in types traditionally implemented in a standard library:

- dynamic arrays
- associateve arrays
- strings

This is in contrast to C++, for example, were dynamic arrays, associative arrays (hash tables) and strings are implemented in the C++ standard library&mdash;in the `std::vector`, `std::unordered_map` and `std::string`, repectively. 
