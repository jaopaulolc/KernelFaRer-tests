CLANGPLUS ?= clang++

CXXFLAGS = -Wall -O3 -g \
					 -mllvm --enable-kernel-replacer \
					 -mllvm --gemmfarer-replacement-mode=cblas-interface \
					 -mllvm --debug-only=gemm-replacer-pass

SRCS = $(wildcard *.cc)
LLS = $(SRCS:.cc=.ll)

all: $(LLS)

%.ll: %.cc
	$(CLANGPLUS) $(CPPFLAGS) $(CXXFLAGS) $^ -S -emit-llvm -o $@

clean:
	$(RM) *.ll
