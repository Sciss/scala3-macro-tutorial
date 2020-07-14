# Cross compilation with Scala 2

The Scala 2 macros are compiler dependent. In other words, macros defined in a Scala 2 library cannot be consumed by a different compiler version.

Scala 3 will break this limitation but it comes with the cost of rewriting all the macro usages of the Scala ecosystem.

## Before rewriting a macro

Before getting deep into reimplementing a macro your should check if it can be supported using Scala 3 new features.

* Can I encode the logic of the macro using the new scala 3 features?
  * [List of Scala 3 features](http://dotty.epfl.ch/docs/reference/overview.html)
* Can I use *match types* to reimplement the interface of my macro?
  * [Match Types](http://dotty.epfl.ch/docs/reference/new-types/match-types.html)
* Can I use `inline` and the metaprogramming features in `scala.compiletime` to reimplement my logic?
  * [Inline](http://dotty.epfl.ch/docs/reference/metaprogramming/inline.html)
  * [`scala.compiletime`](http://dotty.epfl.ch/api/scala/compiletime/index.html)
* Can I use the simpler and safer expression based macros to implement my macro?
  * [Simple macros](http://dotty.epfl.ch/docs/reference/metaprogramming/macros.html)
* I really need to have access to the raw AST trees
  * [TASTy Reflect](http://dotty.epfl.ch/docs/reference/metaprogramming/tasty-reflect.html)
  * [TASTy inspector](http://dotty.epfl.ch/docs/reference/metaprogramming/tasty-inspect.html)

A good reference for this is [Shapeless 3](https://github.com/dotty-staging/shapeless/tree/shapeless-3). It uses Scala 3 features most of the time for a feature that would have been macros in Scala 2 and only uses macros where absolutely necessary.

## Diffrent source directories
If you are already cross-compiling your macro for different versions of Scala 2 and you have sources folders for each version, then you can add an extra source folder for Scala 3.


* SBT examples:
  * *Coming soon* <!-- TODO add SBT example -->
* Mill examples
  * *Coming soon* <!-- TODO Mill example -->
  * [utest](https://github.com/dotty-staging/utest/tree/dotty)
  * [sourcecode](https://github.com/dotty-staging/sourcecode/tree/dotty-community-build)


## Dual macros
*Coming soon*


