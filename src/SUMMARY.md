# iOS逆向：Framework动态库

* [前言](README.md)
* [Framework动态库概述](overview/README.md)
* [常见Framework](common_framework/README.md)
* [dyld_shared_cache](dyld_shared_cache/README.md)
  * [dyld_shared_cache_arm64](dyld_shared_cache/dyld_shared_cache_arm64.md)
  * [提取工具](dyld_shared_cache/extract/README.md)
    * [DyldExtractor](dyld_shared_cache/extract/dyldextractor/README.md)
      * [导出单个库](dyld_shared_cache/extract/dyldextractor/extract_single.md)
      * [导出全部库](dyld_shared_cache/extract/dyldextractor/extract_all/README.md)
        * [过程](dyld_shared_cache/extract/dyldextractor/extract_all/extracting.md)
        * [结果](dyld_shared_cache/extract/dyldextractor/extract_all/result.md)
      * [心得](dyld_shared_cache/extract/dyldextractor/experience.md)
    * [dyld_decache](dyld_shared_cache/extract/dyld_decache.md)
    * [dyld_cache_extract](dyld_shared_cache/extract/dyld_cache_extract.md)
    * [dsc_extractor](dyld_shared_cache/extract/dsc_extractor.md)
    * [dyld-cache-dump](dyld_shared_cache/extract/dyld_cache_dump.md)
  * [相关](dyld_shared_cache/related/README.md)
    * [代码](dyld_shared_cache/related/code.md)
    * [工具](dyld_shared_cache/related/tool/README.md)
      * [update_dyld_shared_cache](dyld_shared_cache/related/tool/update_dyld_shared_cache.md)
    * [涉及的地方](dyld_shared_cache/related/use_case.md)
* [附录](appendix/README.md)
  * [参考资料](appendix/reference.md)
