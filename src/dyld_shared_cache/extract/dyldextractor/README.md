# DyldExtractor

* `DyldExtractor`
  * 功能：从Dyld的Shared cache中提取出二进制（动态库）文件
    * Extract Binaries from Apple's Dyld Shared Cache
  * 安装
    ```bash
    python3 -m pip install dyldextractor
    ```
    * 或
      ```bash
      pip install dyldextractor
      ```
  * 安装后（的脚本工具）的位置
    * `/usr/local/bin/dyldex`
    * `/usr/local/bin/dyldex_all`
 * 用法举例
   * 导出单个库
     ```bash
     dyldex -e libdyld.dylib ./dyld_shared_cache_arm64
     ```
   * 导出全部库
     ```bash
     dyldex_all ./dyld_shared_cache_arm64
     ```
 * 官网
   * PyPI
     * https://pypi.org/project/dyldextractor/
       * `pip install dyldextractor`
   * Github
     * https://github.com/arandomdev/dyldextractor
       * `python3 -m pip install dyldextractor`
