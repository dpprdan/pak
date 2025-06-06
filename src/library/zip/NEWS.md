# zip 2.3.3

* `zip_list()` now has a `type` column, for the file type.

* `unzip()` now correctly creates symbolic links on Unix (#127).

# zip 2.3.2

* `zip_list()` now returns a `tbl` object, and loads the pillar package,
  if installed, to produce the nicer output for long data frames.

# zip 2.3.1

* The zip shared library now hides its symbols (on platforms that support
  this), to avoid name clashes with other libraries (#98).

# zip 2.3.0

* zip now handles large zip files on Windows (#65, #75, #79, @weshinsley).

* zip now behaves better for absolute paths in mirror mode, and when the
  paths contain a `:` character (#69, #70).

* `zip::unzip()` now uses the process's umask value (see `umask(2)`) on Unix
  if the zip file does not contain Unix permissions (#67).

* Fix segmentation fault when zip file can't be created (#91, @zeehio)

* Fix delayed evaluation error on zipfile when `zip::zip()`
  is used (#92, @zeehio)

* New `deflate()` and `inflate()` functions to compress and uncompress
  GZIP streams in memory.

# zip 2.2.2

* No user visible changes.

# zip 2.2.1

* No user visible changes.

# 2.2.0

* Header values (of version made by and external attributes) are now
  correctly read and written on big-endian systems (#68).

* `zip_list()` now also returns `crc32` and `offset` (#74, @jefferis).

# 2.1.1

This version has no user visible changes.

# 2.1.0

* `unzip_process()` now does not fail randomly on Windows (#60).

* Now all functions handle Unicode paths correctly, on Windows
  as well (#42, #53).

* `unzip_process()` now works when R library is on different drive
  than `exdir` on Windows (#45)

* zip functions now have a `mode` argument to choose how files and
  directories are assembled into the archive. See the docs for
  details.

* zip functions now have a `root` argument, zip changes the working
  directory to this before creating the archive, so all files are
  relative to `root`.

* `zip()` and `zip_append()` are not deprecated any more, as it was
  hard to achieve the same functionality with the other zip functions.

# 2.0.4

* `unzip_process()` prints better error messages to the standard error,
  and exits with a non-zero status, on error.

# 2.0.3

* `zipr()` and `zipr_append()` get an `include_directories = TRUE`
  argument, that can be used to omit directory entries from the zip
  archive. These entries may cause problems in MS Office docx files (#34).

# 2.0.2

* `zip_process()` and `unzip_process()` can now pass extra arguments to
  `processx::process` (#32).

* `unzip_process()` now makes sure the `exdir` path is created with
  forward slashes on Windows, mixing forward and backward slashes can
  cause errors.

# 2.0.1

* `zip()` and `zip_append()` are now soft-deprecated, please use
  `zipr()` and `zipr_append()` instead.

# 2.0.0

* New `zipr()` and `zipr_append()`, they always store relative file names
  in the archive.

* New `unzip()` function for uncompressing zip archives.

* New `zip_process()` and `unzip_process()` functions to create or
  uncompress an archive in a background process.

* `zip()`, `zipr()`, `zip_append()` and `zipr_append()` all include
  directories in the archives, empty ones as well.

* `zip()`, `zipr()`, `zip_append()` and `zipr_append()` all add time stamps
  to the archive and `zip_list()` returns then in the `timestamp` column.

* `zip()`, `zipr()`, `zip_append()` and `zipr_append()` all add file
  and directory permissions to the archive on Unix systems, and
  `zip_list()` returns them in the `permissions` column.

* `zip_list()` now correctly reports the size of large files in the archive.

* Use miniz 2.0.8 internally.

# 1.0.0

First public release.
