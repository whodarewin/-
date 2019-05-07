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
bash ./configure --with-freetype=/usr/local/opt/freetype --disable-zip-debug-info --disable-warnings-as-errors --with-debug-level=slowdebug 2>&1 | tee configure_mac_x64.log
```


