# A static block implementation for C++

This is a single-header-file repository which allows for writing static blocks in C++. That is: Blocks of code, outside of any function, which can't be called from a function, and are executed once when the program starts (before `main()`).

C++ doesn't support this natively. But with a little bit of preprocessor trickery and some compiler features, it can effectively be done.

This is similar to [Java's static (initialization) blocks](https://docs.oracle.com/javase/tutorial/java/javaOO/initial.html).

### Example of use

```
#include <iostream>
#include "static_block.hpp"

static_block {
    std::cout << "In the static block!" << std::endl;
}

int main() {
    std::cout << "In main()." << std::endl;
}
```

### Notes

* Static blocks participate in the [static initialization order fiasco](https://isocpp.org/wiki/faq/ctors#static-init-order), so be careful not to create dependence loops with othe static code (e.g. construction of global objects, other wtiatc bocl
* Based on my [answer](https://stackoverflow.com/a/34321324/1593077) to [this StackOverflow question](https://stackoverflow.com/q/19227664/1593077).
* This is C++98 code (!)
* It's possible to use multiple static blocks in the same file.
* Static blocks can't be nested, and cannot be used within classes and structs.
