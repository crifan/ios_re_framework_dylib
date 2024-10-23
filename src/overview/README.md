# Framework动态库概述

* `Frameworks`=`框架`=`库`=`动态库`
  * 含义：**框架**是一个`动态库`和该库的`资源`，例如图像和本地化字符串
    * Frameworks are bundles that contain a linkable library (usually a dylib) and the associated resources and headers for development.
  * 框架的文件扩展名：`.framework`
  * 分类
    * 在iOS中有两种`框架`=`库`
      * `public`=`公开的`：`public frameworks`=公开框架=公开库
        * 主要位置：`/System/Library/Frameworks`
        * 解释：公共框架允许在App Store应用中使用
      * `private`=`私有的`：`private frameworks`=私有框架=私有库
        * 主要位置：`/System/Library/PrivateFrameworks`
        * 解释：私有框架只用于苹果的应用程序，并且在固件更改时更不稳定
          * 但许多有趣的功能都在私有框架中
            * 逆向和插件可以调用这类私有库中的API接口，实现各种功能
  * 额外说明
    * 后续进化为
      * [dyld_shared_cache](../dyld_shared_cache/README.md)
