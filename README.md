# KernelFaRer Tests

Tests used to collect the results for the following paper published at ACM's Transactions on Architecture and Code Optimization (TACO) 2021.

> KernelFaRer: Replacing Native-Code Idioms with High-Performance Library Calls ([Preprint](https://www.researchgate.net/publication/350453412_KernelFaRer_Replacing_Native-Code_Idioms_with_High-Performance_Library_Calls))

by

> João P. L. de Carvalho, Braedy Kuzma, Ivan Korostelev, José Nelson Amaral, Christopher Barton, José Moreira, and Guido Araujo.

KernelFarer source code is open-sourced [here](https://github.com/jaopaulolc/KernelFaRer).

Please follow the instructions bellow to compile LLVM tools with KernelFaRer support:

~~~bash
$ git clone https://github.com/jaopaulolc/KernelFaRer.git
$ cd KernelFaRer
KernelFaRer $ mkdir build
KernelFaRer/build $ cd build
KernelFaRer/build $ cmake ../llvm         \
     -GNinja                              \
    -DLLVM_PARALLEL_LINK_JOBS=2           \
    -DLLVM_OPTIMIZED_TABLEGEN=ON          \
    -DCMAKE_BUILD_TYPE=RelWithDebInfo     \
    -DLLVM_EXTERNAL_PROJECTS="eigen-runtime" \
    -DLLVM_ENABLE_PROJECTS="clang;llvm;polly;libcxx;libcxxabi;openmp;eigen-runtime" \
    -DLLVM_POLLY_LINK_INTO_TOOLS=ON       \
    -DCMAKE_INSTALL_PREFIX=$PWD/install   \
    -DLLVM_INSTALL_UTILS=ON               \
    -DBUILD_SHARED_LIBS=ON                \
    -DLLVM_ENABLE_RTTI=ON                 \
    -DLLVM_ENABLE_ASSERTIONS=ON
KernelFaRer/build $ ninja install
~~~

The LLVM tools with KernelFaRer are installed under `KernelFarer/build/install`.
