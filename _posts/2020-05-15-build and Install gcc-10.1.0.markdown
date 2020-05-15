---
title: Build And Install gcc-10.1.0
layout: post
tag: ENV
---

<br/>

2020.5.7 发布了 gcc-10.1.0，虽然只是部分支持 c++20 标准，如下图所示：

![avatar](./figures/c++20_compiler_support.png)

下载源码：\
http://ftp.tsukuba.wide.ad.jp/software/gcc/releases/gcc-10.1.0/gcc-10.1.0.tar.gz

下载依赖的组件：\
gmp:  http://gcc.gnu.org/pub/gcc/infrastructure/gmp-6.1.0.tar.bz2 \
mpfr: http://gcc.gnu.org/pub/gcc/infrastructure/mpfr-3.1.4.tar.bz2 \
mpc:  http://gcc.gnu.org/pub/gcc/infrastructure/mpfr-3.1.4.tar.bz2 \
isl:  http://gcc.gnu.org/pub/gcc/infrastructure/mpfr-3.1.4.tar.bz2 

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

<br/>

