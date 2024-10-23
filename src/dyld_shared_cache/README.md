# dyld_shared_cache

* dyld的shared cache = dyld (shared) cache
  * 概述：所有Framework库都被合并到共享缓存shared cache中了
  * 详解
    * 从`iOS 3.1`之后，所有默认的（公共的public和私有的private）库都被合并到一个大的**缓存文件**中
      * 目的：提高性能
      * 效果：
        * 原始库对于非设备上的开发人员不再有用，因此它们被从系统中删除
          * -》直接去原始位置
            * public=公开的库
              * `/System/Library/Frameworks`
            * private=私有的库
              * `/System/Library/PrivateFrameworks`
          * 找对应的系统库文件，就会出找不到的现象
        * 框架文件夹仍然包含其他资源，例如本地化字符串
  * 位置
    * 典型位置：`/System/Library/Caches/com.apple.dyld/`
      * `/System/Library/Caches/com.apple.dyld/dyld_shared_cache_armX`
        * 其中：`X`= `6`/`7`/`7s`/`64`
          * 举例
            * `/System/Library/Caches/com.apple.dyld/dyld_shared_cache_arm64`
    * 其他的位置？
      * `/System/Library/dyld/dyld_shared_cache_arm64e`
  * 资料
    * [Dev:dyld_shared_cache - The Apple Wiki](https://theapplewiki.com/wiki/Dev:Dyld_shared_cache)
