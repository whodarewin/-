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
   2. https://github.com/hgomez/obuildfactory/issues/51
   3. https://bugs.openjdk.java.net/browse/JDK-8033898?page=com.atlassian.jira.plugin.system.issuetabpanels%3Aall-tabpanel
```
make all COMPILER_WARNINGS_FATAL=false LFLAGS='-Xlinker -lstdc++' CC=clang USE_CLANG=true LP64=1
```
   4. friend declaration specifying a default argument must be a definition
   https://juejin.im/entry/5a6c36af6fb9a01cb64f05b8
   5. error: ordered comparison between pointer and zero ('char *' and 'int')
   https://www.cnblogs.com/JunFengChan/p/9266033.html
   6. fatal error: 'X11/Intrinsic.h' file not found
   安装https://www.xquartz.org/  
   sudo ln -s /opt/X11/include/X11 /usr/local/include/X11
   7. class jdk.nashorn.internal.objects.ScriptFunctionImpl overrides final method setPrototype.(Ljava/lang/Object;)V
   https://blog.csdn.net/manageer/article/details/72812149
   
4. build success

```
----- Build times -------
Start 2019-05-07 15:57:12
End   2019-05-07 15:59:37
00:00:00 corba
00:00:01 demos
00:01:17 docs
00:00:01 hotspot
00:01:02 images
00:00:00 jaxp
00:00:00 jaxws
00:00:01 jdk
00:00:00 langtools
00:00:01 nashorn
00:02:25 TOTAL
-------------------------
Finished building OpenJDK for target 'all'
```


