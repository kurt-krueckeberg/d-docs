D Introduction
==============

Scripts in D
--------------------------

The Linux shebang 

.. code-block:: bash

    #!/usr/bin/env rdmd

enables a `.d` file to be used as an executable "script" once `chmod +x script_name.d` is done.

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

The import statement makes all public functions and types from the given module available. The D standard library modules are contained within the ``std`` package and imported using ``import std.MODULE;`` 

.. code-block::d

    import std.studio;
    import std.socket;

The import statement need not appear at the top of the file; it can appear within local scopes, and you can also selectively import symbols from a module

.. code-block::d

    import std.studio : writeln, writefln;

.. todo:: continue from https://tour.dlang.org/tour/en/basics/imports-and-modules
