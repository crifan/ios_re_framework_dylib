# 相关代码

## 相关源码

* 源码
	* github.com
		* https://github.com/opensource-apple/dyld/tree/master/launch-cache
			* https://github.com/opensource-apple/dyld/blob/master/launch-cache/dyld_shared_cache_util.cpp
			* https://github.com/opensource-apple/dyld/blob/master/launch-cache/dsc_extractor.cpp
			* https://github.com/opensource-apple/dyld/blob/master/launch-cache/dsc_iterator.cpp
	* opensource.apple.com
		* 旧：已打不开
  		* https://opensource.apple.com/source/dyld/dyld-852.2/dyld3/shared-cache/
  			* https://opensource.apple.com/source/dyld/dyld-852.2/dyld3/shared-cache/dyld_shared_cache_util.cpp.auto.html
  			* https://opensource.apple.com/source/dyld/dyld-852.2/dyld3/shared-cache/dsc_extractor.cpp.auto.html
  			* https://opensource.apple.com/source/dyld/dyld-852.2/dyld3/shared-cache/dsc_iterator.cpp.auto.html
  			* https://opensource.apple.com/source/dyld/dyld-852.2/dyld3/shared-cache/dyldinfo.cpp.auto.html
  			* https://opensource.apple.com/source/dyld/dyld-852.2/dyld3/shared-cache/DyldSharedCache.cpp.auto.html
  	* 新
      * https://opensource.apple.com/releases/
        * -> https://github.com/apple-oss-distributions/dyld/releases/
          * 最新版本：[dyld-1231.3](https://github.com/apple-oss-distributions/dyld/releases/tag/dyld-1231.3)
            * https://github.com/apple-oss-distributions/dyld/archive/refs/tags/dyld-1231.3.zip
              * 里面有各个工具的代码
                * `dyld-dyld-1231.3/`
                  * `other-tools/chroot_util.cpp`
                  * `other-tools/dsc_extractor.cpp`
                  * `other-tools/dsc_iterator.cpp`
                  * `other-tools/dyld_closure_util.cpp`
                  * `other-tools/dyld_info.cpp`
                  * `other-tools/dyld_inspect.cpp`
                  * `other-tools/dyld_nm.cpp`
                  * `other-tools/dyld_shared_cache_util.cpp`
                  * `other-tools/dyld_symbols_cache.cpp`
                  * `other-tools/dyld_usage.cpp`

## 相关函数

## dyld_priv.h

[dyld_priv.h](https://opensource.apple.com/source/dyld/dyld-852.2/include/mach-o/dyld_priv.h.auto.html)

```c
// Returns if any OS dylib has overridden its copy in the shared cache
//
// Exists in iPhoneOS 3.1 and later 
// Exists in Mac OS X 10.10 and later
extern bool dyld_shared_cache_some_image_overridden(void);

// Returns path used by dyld for standard dyld shared cache file for the current arch.
//
// Exists in Mac OS X 10.11 and later
extern const char* dyld_shared_cache_file_path(void);

struct dyld_shared_cache_dylib_text_info {
	uint64_t		version;		// current version 2
	// following fields all exist in version 1
	uint64_t		loadAddressUnslid;
	uint64_t		textSegmentSize; 
	uuid_t			dylibUuid;
	const char*		path;			// pointer invalid at end of iterations
	// following fields all exist in version 2
	uint64_t        textSegmentOffset;  // offset from start of cache
};
typedef struct dyld_shared_cache_dylib_text_info dyld_shared_cache_dylib_text_info;


#ifdef __BLOCKS__
// Given the UUID of a dyld shared cache file, this function will attempt to locate the cache
// file and if found iterate all images, returning info about each one.  Returns 0 on success.
//
// Exists in Mac OS X 10.11 and later
//           iOS 9.0 and later
extern int dyld_shared_cache_iterate_text(const uuid_t cacheUuid, void (^callback)(const dyld_shared_cache_dylib_text_info* info));

// Given the UUID of a dyld shared cache file, and a NULL terminated array of extra directory paths to search,
// this function will scan the standard and extra directories looking for a cache file that matches the UUID
// and if found iterate all images, returning info about each one.  Returns 0 on success.
//
// Exists in Mac OS X 10.12 and later
//           iOS 10.0 and later
extern int dyld_shared_cache_find_iterate_text(const uuid_t cacheUuid, const char* extraSearchDirs[], void (^callback)(const dyld_shared_cache_dylib_text_info* info));
#endif /* __BLOCKS */

// Gets the UUID of the dyld shared cache in the current process.
// Returns false if there is no dyld shared cache in use by the processes.
//
// Exists in Mac OS X 10.12 and later
// Exists in iOS 10.0 and later
extern bool _dyld_get_shared_cache_uuid(uuid_t uuid);

// Returns the start address of the dyld cache in the process and sets length to the size of the cache.
// Returns NULL if the process is not using a dyld shared cache
//
// Exists in Mac OS X 10.13 and later
// Exists in iOS 11.0 and later
extern const void* _dyld_get_shared_cache_range(size_t* length);

// Returns if the currently active dyld shared cache is optimized.
// Note: macOS does not use optimized caches and will always return false.
//
// Exists in Mac OS X 10.15 and later
// Exists in iOS 13.0 and later
extern bool _dyld_shared_cache_optimized(void);

// Returns if the currently active dyld shared cache was built locally.
//
// Exists in Mac OS X 10.15 and later
// Exists in iOS 13.0 and later
extern bool _dyld_shared_cache_is_locally_built(void);

// This is similar to _dyld_shared_cache_contains_path(), except that it returns the canonical
// shared cache path for the given path.
//
// Exists in macOS 10.16 and later
// Exists in iOS 14.0 and later
extern const char* _dyld_shared_cache_real_path(const char* path);
```
