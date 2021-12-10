# Modules

## Intro

In modules there is no need to separate function and type declarations from their definitions. By default, symbols in a module are publicly accessible, but can be made internal
via the private keyword. This is analogous to the usage of static in C, but given that D supports access modifiers in class and struct definitions, where static has nothing to do with access
control, it made sense to use private at module scope instead of static.

See:

* D Language Reference article on [Modules](https://dlang.org/spec/module.html)
* D Phobos standard library [list of modules in D](https://dlang.org/spec/module.html).
