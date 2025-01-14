# update_dyld_shared_cache

## man page

```bash
update_dyld_shared_cache(1)				    BSD General Commands Manual 			       update_dyld_shared_cache(1)

NAME

     update_dyld_shared_cache -- Updates dyld's shared cache

SYNOPSIS

     update_dyld_shared_cache [-root directory] [-overlay directory] [-arch arch] [-force] [-debug] [-sort_by_name] [-universal_boot] [-verify]
			      [-dylib_list file] [-iPhone] [-cache_dir dir]

DESCRIPTION

     update_dyld_shared_cache ensures that dyld's shared cache is up-to-date.  This tool is normally only run by Apple's Installer and Software
     Update, as they are the only official ways for OS dylibs to be updated.  But if for some reason you used another mechanism to alter an OS
     dylib, you should manually run update_dyld_shared_cache.

     Note that the new cache does not take effect until the OS is rebooted.

     If a safe-boot is done (booting with shift key held down) the cache is deleted.

     The dyld shared cache is mapped by dyld into a process at launch time. Later, when loading any mach-o image, dyld will first check if is in
     the share cache, and if it is will use that pre-bound version instead of opening, mapping, and binding the original file.	This results in
     significant performance improvements to launch time.

     update_dyld_shared_cache scans the directory /var/db/dyld/shared_region_roots for text files containing paths to mach-o executables.  The
     full dependencies of all dylibs required by those executables is used to determine which libraries are commonly used and should be placed in
     the shared cache. If one of the text files contains a path to a dylib, that dylib and its dependents will be forced into the cache.

     update_dyld_shared_cache builds a separate cache file for each architecture.  The cache files and a readable text map of the cached are gen-
     erated to /var/db/dyld.

     You must be root to run this tool.

     The options are as follows:

     -root directory
		 This option specifies the root of an OS installation for which dyld's shared cache should be updated.	This is used by the In-
		 staller to update the dyld shared cache in a partition other than the one you into which you are currently booted.  The cache
		 files are created in the var/db/dyld directory of the specified directory.  Note: if you are manually doing this, be sure to run
		 the update_dyld_shared_cache tool that is in the partition being updated.  This assures the cache format created will match that
		 expected when booting off that partition.

     -overlay directory
		 This option specifies the root of a sparse directory tree.  When building the dyld shared cache, any corresponding mach-o files
		 in the sparse directory will override those in the boot partition.  This is used by Software Update to build a dyld shared cache
		 for the update that is about to be installed.	The cache files are created in the var/db/dyld directory of the specified direc-
		 tory.

     -arch arch  By default update_dyld_shared_cache generates cache files for all architecture that the current machine can execute.  You can
		 override this behavior by specifying one or more -arch options and list exactly which architectures should have their shared
		 caches updated.

     -force	 This option will cause update_dyld_shared_cache to regenerated the shared cache files even if they appear to be already up-to-
		 date.

     -debug	 This option prints out additional information about the work being done.

     -sort_by_name
		 By default update_dyld_shared_cache assigns a random start address to each mach-o image in the cache.	This option causes the
		 start addresses to be chosen in path order, thus subsequent runs will produce the same address layout which can help reproduce
		 some bugs.

     -universal_boot
		 This option can only be used running on an machine with an Intel processor.  It builds caches that can be used when booting on
		 both 32-bit and 64-bit machines.

     -dylib_list file
		 Instead of scanning /var/db/dyld/shared_region_roots/, this option provides a file that contains a list of the dylibs to use when
		 building the shared cache file.

     -verify	 Will regenerate a shared cache in-memory that matches the randomization of the existing shared cache file.  Then instead of writ-
		 ing the cache file, it compares the in-memory cache file to the on disk version and reports any differences.

     -iPhone	 indicates that cache is not for the current Mac OS X, but for rather for an iPhone

     -cache_dir directory
		 This option specifies the directory in which to create the cache file(s).  If not specified, the cache file(s) are created in the
		 standard location (e.g. var/db/dyld/) of the root partition.

FILES

     /var/db/dyld/shared_region_roots directory of text files with paths to mach-o images used to determine what should be in shared cache.

SEE ALSO

     dyld(1)

Darwin								   Oct 10, 2008 							    Darwin
```
