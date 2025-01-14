# iOS逆向：Framework动态库

* 最新版本：`v1.1.0`
* 更新时间：`20241023`

## 简介

介绍iOS逆向期间常涉及到的Framework动态库dylib相关内容。先对于Framework动态库概述；介绍常见Framework；介绍dyld_shared_cache即dyld的shared cache，常见文件是dyld_shared_cache_arm64；接着介绍提取工具和相关的代码、工具和涉及的地方；提取工具主要有DyldExtractor、dyld_decache、dyld_cache_extract、dsc_extractor、dyld-cache-dump。尤其是可用和好用的DyldExtractor，支持提取单个库和全部的库；以及一些经验心得；其他工具有update_dyld_shared_cache。

## 源码+浏览+下载

本书的各种源码、在线浏览地址、多种格式文件下载如下：

### HonKit源码

* [crifan/ios_re_framework_dylib: iOS逆向：Framework动态库](https://github.com/crifan/ios_re_framework_dylib)

#### 如何使用此HonKit源码去生成发布为电子书

详见：[crifan/honkit_template: demo how to use crifan honkit template and demo](https://github.com/crifan/honkit_template)

### 在线浏览

* [iOS逆向：Framework动态库 book.crifan.org](https://book.crifan.org/books/ios_re_framework_dylib/website/)
* [iOS逆向：Framework动态库 crifan.github.io](https://crifan.github.io/ios_re_framework_dylib/website/)

### 离线下载阅读

* [iOS逆向：Framework动态库 PDF](https://book.crifan.org/books/ios_re_framework_dylib/pdf/ios_re_framework_dylib.pdf)
* [iOS逆向：Framework动态库 ePub](https://book.crifan.org/books/ios_re_framework_dylib/epub/ios_re_framework_dylib.epub)
* [iOS逆向：Framework动态库 Mobi](https://book.crifan.org/books/ios_re_framework_dylib/mobi/ios_re_framework_dylib.mobi)

## 版权和用途说明

此电子书教程的全部内容，如无特别说明，均为本人原创。其中部分内容参考自网络，均已备注了出处。如发现有侵权，请通过邮箱联系我 `admin 艾特 crifan.com`，我会尽快删除。谢谢合作。

各种技术类教程，仅作为学习和研究使用。请勿用于任何非法用途。如有非法用途，均与本人无关。

## 鸣谢

感谢我的老婆**陈雪**的包容理解和悉心照料，才使得我`crifan`有更多精力去专注技术专研和整理归纳出这些电子书和技术教程，特此鸣谢。

## 其他

### 作者的其他电子书

本人`crifan`还写了其他`150+`本电子书教程，感兴趣可移步至：

[crifan/crifan_ebook_readme: Crifan的电子书的使用说明](https://github.com/crifan/crifan_ebook_readme)

### 关于作者

关于作者更多介绍，详见：

[关于CrifanLi李茂 – 在路上](https://www.crifan.org/about/)
