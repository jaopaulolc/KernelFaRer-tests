# C++ Unit Tests

The tests here are similar to the lit tests under [llvm/test/Transforms/GEMMFaRer](https://github.com/jaopaulolc/KernelFaRer/tree/kernelfarer/llvm/test/Transforms/GEMMFaRer) but written in C++ functions.

They test if the matcher in KernelFaRer can match different variations of functions that implement a GeMM (General Matrix-Matrix Multiply).

They can be execute as follows:

~~~bash
cplus-tests $ make CLANGPLUS=<path to KernelFarer enabled Clang>/clang++ 2>&1 | grep 'Kernel rewritable'
~~~

The previous command line show generate an output similar to the follow:

~~~bash
Kernel rewritable at line 3
Kernel rewritable at line 3
Kernel rewritable at line 3
Kernel rewritable at line 3
Kernel rewritable at line 3
Kernel rewritable at line 3
Kernel rewritable at line 3
Kernel rewritable at line 3
Kernel rewritable at line 3
Kernel rewritable at line 3
Kernel rewritable at line 3
Kernel rewritable at line 3
Kernel rewritable at line 3
Kernel rewritable at line 3
Kernel rewritable at line 3
Kernel rewritable at line 3
~~~

The output show contain 16 lines, one per `.cc` file.
