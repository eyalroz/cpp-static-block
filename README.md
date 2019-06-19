# A static block implementation for C++

This is a single-header-file repository which allows for writing static blocks in C++: 

* Blocks of code
* outside of any function
* Which can't be called from a function
* Executed once when the program starts (before `main()`).

This is similar to [Java's static (initialization) blocks](https://docs.oracle.com/javase/tutorial/java/javaOO/initial.html).

Notes:

* Static blocks participate in the [static initialization order fiasco](https://isocpp.org/wiki/faq/ctors#static-init-order), so be careful not to create dependence loops with othe static code (e.g. construction of global objects, other wtiatc bocl
* Based on my [answer](https://stackoverflow.com/a/34321324/1593077) to [this StackOverflow question](https://stackoverflow.com/q/19227664/1593077).
