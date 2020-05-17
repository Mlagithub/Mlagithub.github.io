---
title: Build And Install gcc-10.1.0
layout: post
tag: ENV
---

# 编译安装 gcc-10.1.0

2020.5.7 发布了 gcc-10.1.0，虽然只是<a href="https://en.cppreference.com/w/cpp/compiler_support">部分支持</a> c++20 标准（），而且相较于gcc-5等老版本，编译器性能及错误提示友好了许多（快赶上clang了），所以还是值得一试的。

![avatar][compiler-support]

[compiler-support]: ./figures/c++20_compiler_support.png

<!-- <div align="center">
<img src="figures/c++20_compiler_support.png" alt="c++20 compiler support">
</div> -->

下载源码：
<a href="http://ftp.tsukuba.wide.ad.jp/software/gcc/releases/gcc-10.1.0/gcc-10.1.0.tar.gz">gcc-10.1.0.tar.gz</a>，
及依赖的组件：
<a href="http://gcc.gnu.org/pub/gcc/infrastructure/gmp-6.1.0.tar.bz2">gmp</a>，
<a href="http://gcc.gnu.org/pub/gcc/infrastructure/mpfr-3.1.4.tar.bz2">mpfr</a>，
<a href="https://gcc.gnu.org/pub/gcc/infrastructure/mpc-1.0.3.tar.gz">mpc</a>，
<a href="http://gcc.gnu.org/pub/gcc/infrastructure/mpfr-3.1.4.tar.bz2">isl</a>

解压下载好的 gcc-10.1.0.tar.gz， 并进入解压后的目录:

```shell
tar -xf gcc-10.1.0.tar.gz
cd gcc-10.1.0
```

新建并进入编译目录： `mkdir build && cd build`

配置：

```shell
../configure --prefix=xxx --enable-languages=c,c++ --disable-multilib
```

编译安装：`make -j n && make install` 

配置环境变量:

```shell
export PATH=xxx/bin:$PATH
export LD_LIBRARY_PATH=xxx/lib64:$LD_LIBRARY_PATH
export C_INCLUDE_PATH=xxx/include:$C_INCLUDE_PATH 
```
