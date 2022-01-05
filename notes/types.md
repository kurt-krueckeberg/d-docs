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
|char|UTF-8 code unit|0xFF|
|wchar|UTF-16 code unit|0xFFFF|
|dchar|UTF-32 code unit and Unicode code point|0x0000FFFF|

### sizeof Output

This code show the number of bypes per type using the built-in `sizeof` property:

<pre>
import std.stdio;

void main(string[] args)
{
   writefln("bool.sizeof\t= %s", bool.sizeof);
   
   writefln("byte.sizeof\t= %s", byte.sizeof);
   
   writefln("ubyte.sizeof\t= %s", ubyte.sizeof);
   
   writefln("short.sizeof\t= %s", short.sizeof);
   
   writefln("ushort.sizeof\t= %s", ushort.sizeof);
   
   writefln("int.sizeof\t= %s", int.sizeof);
   
   writefln("uint.sizeof\t= %s", uint.sizeof);
   
   writefln("long.sizeof\t= %s", long.sizeof);
   
   writefln("ulong.sizeof\t= %s", ulong.sizeof);
   
   writefln("float.sizeof\t= %s", float.sizeof);
   
   writefln("double.sizeof\t= %s", double.sizeof);
   
   writefln("real.sizeof\t= %s", real.sizeof);

   writefln("char.sizeof\t= %s", char.sizeof);
   
   writefln("wchar.sizeof\t= %s", wchar.sizeof);
   
   writefln("dchar.sizeof\t= %s", dchar.sizeof);
}   
</pre>

This output is:

<pre>
bool.sizeof	= 1
byte.sizeof	= 1
ubyte.sizeof	= 1
short.sizeof	= 2
ushort.sizeof	= 2
int.sizeof	= 4
uint.sizeof	= 4
long.sizeof	= 8
ulong.sizeof	= 8
float.sizeof	= 4
double.sizeof	= 8
real.sizeof	= 16
char.sizeof	= 1
wchar.sizeof	= 2
dchar.sizeof	= 4
</pre>

## Complex type

`std.complex.Complex` implements the complex number template class parametrised by a type T, which must be either float, double or real.

## Other Built-in Types in D

As explained in [D Builtin Rationale](https://dlang.org/articles/builtin.html), D has three types traditionally implemented in a standard library, but in D they are built-in, implemented in the compiler:

- dynamic arrays
- associateve arrays
- strings

This is in contrast to C++, for example, were dynamic arrays, associative arrays (hash tables) and strings are implemented in the C++ standard library&mdash;in the `std::vector`, `std::unordered_map` and `std::string`, repectively. 

## Properties of Types in D

### Properties of All Types

All types in D have these properties:

| Property|Description|
|---------|-----------|
|.init|initializer|
|.sizeof|size in bytes|
|.alignof|alignment size|
|.mangleof|string representing the ‘mangled’ representation of the type|
|.stringof|string representing the source representation of the type|

### Properties for Integral Types

Integral types have these properties:

|Property|Description|
|--------|----------|
|.init|initializer|
|.max|maximum value|
|.min|minimum value|

### Properties for Floating Point Types

And floating point types have these:

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

Classes declared in D have this property:

|Property|Description|
|--------|-----------|
|.classinfo|Information about the dynamic type of the class|

For details on implicit type promptions, about, ....
