# openjdk源码的编译

1. 环境
   macos
   xcode
2. 步骤  
   1. 安装软件
```
    安装jdk7
    brew install ccache  
    brew install freetype
    brew install gcc
```
   2. 下载源码
```
    wget [http://hg.openjdk.java.net/jdk8/jdk8/jdk/archive/tip.zip](http://hg.openjdk.java.net/jdk8/jdk8/jdk/archive/tip.zip)
```   
   3. 编译
```
bash ./configration
make all
```
3. 遇到的问题
   1. 找不到gcc complier
```
   注释generated-configure.sh的20061和21640行（common/autoconf/generated-configure.sh）
```
   2. 


