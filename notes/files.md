Files Module
============

[Working with files in the D programming language](http://nomad.uk.net/articles/working-with-files-in-the-d-programming-language.html) explains **std.file** with numerous examples.

To iterate a file line by line, you use `file.byLine`:

 q: What does file.byLine return--what is its return type?

````d
import std.exception;
import std.stdio;
import std.regex;

void main(string[] args)
{
   try { // <-- Later: Change try/catch/finally to scope(blah blah) D-idion.

      auto file = File("./text.txt", "r");

      auto rx = regex(r"^([^#]+)\s#\s(.*)$"); 

      /*
       * Files tutorial: http://nomad.uk.net/articles/more-hidden-treasure-in-the-d-standard-library.html
       */

      foreach (line; file.byLine) {

         foreach (c; matchAll(line, rx)) // matchAll() vs just simply match the regex 
          writeln(c.hit);
      }

   } catch ( ErrnoException e) { // FileException is unidentified.

      writeln(e.msg); 
      writeln(e.file); 
      writeln(e.line); 
       
   } finally {

   }
}
````
