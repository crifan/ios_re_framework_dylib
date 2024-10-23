# dyld_decache

## `dyld_decache`插件

* `dyld_decache`插件
  * 评价：**暂未用过**
    * 此处无需自己手动编译
  * 下载
    * https://www.ios-repo-updates.com/repository/jonas-gessner-s-repo/package/de.j-gessner.dyld-decache/
  * 思路
    * 去安装到越狱iPhone中，然后导出（arm版的）工具（dyld_decache）到Mac（此处正好是arm64的：Mac  M2 Max）中 ，应该也可以在Mac中直接使用

## `dyld_decache`源码

* `dyld_decache`源码
  * 评价：**需要自己编译，很麻烦**
    * 已完成部分过程，详见
      * 【未解决】Mac中自己编译kennytm的dyld_decache
        ```bash
        g++ -o dyld_decache -O3 -Wall -Wextra -std=c++98 /usr/local/lib/libboost_filesystem-mt.a /usr/local/lib/libboost_system-mt.a dyld_decache.cpp DataFile.cpp
        ```
      * 【已解决】Mac中编译dyld_decache报错：clang error no such file or directory /usr/local/lib/libboost_system-mt.a
        ```bash
        g++ -o dyld_decache -O3 -Wall -Wextra -std=c++98 -lboost_system-mt -lboost_thread-mt dyld_decache.cpp DataFile.cpp
        ```
      * 【已解决】Mac中编译dyld_decache报错：dyld_decache.cpp fatal error boost/filesystem.hpp file not found
        ```bash
        brew install boost
        ```
      * 【已解决】Mac中编译dyld_decache报错：error_category.hpp error unknown type name constexpr
        ```bash
        g++ -o dyld_decache -O3 -Wall -Wextra -std=c++11 -lboost_system-mt -lboost_thread-mt
        ```
      * 【已解决】Mac中编译dyld_decache报错：ld warning ignoring file libboost_system-mt.dylib found architecture x86_64 required architecture arm64
        ```bash
        g++ -o dyld_decache -O3 -Wall -Wextra -std=c++11 -L/opt/homebrew/Cellar/boost/1.86.0_1/lib -lboost_system-mt -lboost_thread-mt
        ```
  * 代码
    * https://github.com/kennytm/Miscellaneous/blob/master/dyld_decache.cpp
  * 相关
    * https://github.com/iosre/iOSAppReverseEngineering/blob/master/iOSAppReverseEngineering.pdf
