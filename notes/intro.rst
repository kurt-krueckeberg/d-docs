D Introduction
==============

Scripts in D
--------------------------

The Linux shebang 

.. code-block:: bash

    #!/usr/bin/env rdmd

turns your **D** file into a script (after ``chmod +x script_name.d`` is done).

Basic DUB Package Manager Usage
-------------------------------

.. list-table:: Title
   :widths: 25 125
   :header-rows: 1

   * - dub command
     - Explanation
   * - dub init <project_name>
     - Creates a new project
   * - dub 
     - Running dub inside <project_name> fetches all dependencies, compiles the application and then runs it.

import
------

The ``import`` statement makes all public functions and types from the given module available. The D standard library modules are contained within the ``std`` package and imported using ``import std.MODULE;`` 

.. code-block::d

    import std.studio;
    import std.socket;

The import statement need not appear at the top of the file; it can appear within local scopes, and you can also selectively import symbols from a module

.. code-block::d

    import std.studio : writeln, writefln;

D Fundamental Types
-------------------

.. list-table:: D Basic Types
   :widths: 25 60 50
   :header-rows: 1

   * - Type
     - Definition
     -  Initial Value
   * - bool
     - Boolean type
     -  false
   * - byte
     - signed 8 bits
     - 0
   * - ubyte
     - unsigned 8 bits
     - 0
   * - short
     - signed 16 bits
     -  0
   * - ushort
     - unsigned 16 bits
     - 0
   * - int
     - signed 32 bits
     - 0
   * - uint
     - unsigned 32 bits
     - 0
   * - long
     - signed 64 bits
     - 0L
   * - ulong
     - unsigned 64 bits
     - 0LU
   * - float
     - 32-bit floating point
     - float.nan
   * - double
     - 64-bit floating point
     - double.nan
   * - real
     - either the largest floating point type that the hardware supports or double; whichever is larger
     - real.nan
   * - ifloat
     - imaginary value type of float
     - float.nan * 1.0i
   * - idouble
     - imaginary value type of double
     - double.nan * 1.0i
   * - ireal
     - imaginary value type of real
     - real.nan * 1.0i
   * - cfloat
     - complex number type made of two floats
     - float.nan + float.nan * 1.0i
   * - cdouble
     - complex number type made of two doubles
     - double.nan + double.nan * 1.0i
   * - creal
     - complex number type made of two reals
     - real.nan + real.nan * 1.0i
   * - char
     - UTF-8 code unit
     - 0xFF
   * - wchar
     - UTF-16 code unit
     - 0xFFFF
   * - dchar
     - UTF-32 code unit and Unicode code point
     - 0x0000FFFF

Skipping Whitespace in stdin
----------------------------

Most often when reading input from **stdin**, we need to ignore special input characters such as whitespace characters like newline, tab, etc; otherwise, the ``read("%s", &someVariable)`` like that in the code below will fail

.. code-block:: d

    void main() {
        write("How many students are there? ");
        int studentCount;
        readf("%s", &studentCount);
    
        write("How many teachers are there? ");
        int teacherCount;
        readf("%s", &teacherCount); // <-- '\n' will cause this line to fail, and exception to be thrown.
    
        writeln("Got it: There are ", studentCount, " students",
                " and ", teacherCount, " teachers.");
    }
    
Input like this::

    100[EnterCode]20[EnterCode]

will cause ``readf("%s", &teacherCount)`` to throw an exception. The solution is to change the first argument to `` %s``. Since spaces that are in the format strings are used to read and ignore zero or more invisible characters that would otherwise appear in the input. 

.. note::  Use **" %s"** with **read(" %s", &someVar)** to ignore whitespace characters in stdin.
