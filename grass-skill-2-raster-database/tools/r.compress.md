# r.compress

**Category**: raster

## Description

Compresses and decompresses raster maps.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_compress(map,flags=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`map : str | list[str], required`**
   - Name of existing raster map(s)
   - Used as: input, raster, name

2. **`flags : str, optional`**
   - Allowed values: u, p, g
   - u
   - Uncompress the map
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/r.compress.html#__tabbed_2_3) for all details)*

3. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

4. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

5. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

r.compress can be used to compress or decompress raster maps.
Additionally, it prints information about the compression method and
data type of the input raster map(s).

All raster maps (those imported for the first time and those newly
generated) are compressed by default using the ZSTD compression method
if available, otherwise ZLIB compression is used (see below). Related no
data files (i.e.: NULL files), if present, are compressed by default
unless a specific environment variable is set to explicitly disable NULL
file compression ( GRASS_COMPRESS_NULLS , see below).

During compression or re-compression, r.compress compresses raster
maps using the method specified by means of the environment variable GRASS_COMPRESSOR . The default compression method is ZSTD if available,
otherwise ZLIB's "deflate" algorithm (LZ77-based). Raster maps that
contain very little information (such as boundary, geology, soils and
land use maps) can be greatly reduced in size. Some raster maps are
shrunk to roughly 1% of their original sizes. All newly generated raster
maps are automatically stored as compressed data with varying methods
depending on the raster format (i.e., CELL: integer; FCELL: single
precision; DCELL: double precision; see below). All GRASS modules
are able to read both compressed and uncompressed raster maps.

Raster maps that are already compressed might be compressed again,
either by setting a different method with GRASS_COMPRESSOR (supported
methods: RLE, ZLIB, LZ4, BZIP2, ZSTD) or, for the case of ZLIB
compression, by changing the compression level with the environment
variable GRASS_ZLIB_LEVEL .

Compressed raster maps may be decompressed using r.compress with the -u flag. If a raster map was already decompressed and the -u flag is set, the module simply informs the user that the map is already
decompressed and exits.

Information about the compression method and data type of the input
raster map(s) can be printed in shell style with the -g flag. In
this case, the module prints to stdout one line per input map with the
fields "input map name", "data type", "name of data compression method",
"NULL file compression" separated by the pipe character. NULL file
compression is indicated with "YES" or "NO".

The following compression methods are available (set by export GRASS_COMPRESSOR= method ):

Important: the NULL file compression can be turned off with export GRASS_COMPRESS_NULLS=0 . Raster maps with NULL file compression
can only be opened with GRASS GIS 7.2.0 or later. NULL file compression
for a particular raster map can be managed with r.null -z . The NULL
file compression is using the LZ4 method as being the best compromise
between speed and compression rate.

All GRASS raster map types are by default ZSTD compressed if
available, otherwise ZLIB compressed. Through the environment variable GRASS_COMPRESSOR the compression method can be set to RLE, ZLIB, LZ4,
BZIP2, or ZSTD.

Integer (CELL type) raster maps can be compressed with RLE if the
environment variable GRASS_COMPRESSOR exists and is set to RLE.
However, this is not recommended.

Floating point (FCELL, DCELL) raster maps never use RLE compression;
they are either compressed with ZLIB, LZ4, BZIP2, ZSTD or are
uncompressed.

RLE DEPRECATED Run-Length Encoding, poor compression ratio but fast. It
is kept for backwards compatibility to read raster maps created with
GRASS 6. It is only used for raster maps of type CELL. FCELL and DCELL
maps are never and have never been compressed with RLE.

ZLIB ZLIB's deflate is the default compression method for all raster maps, if
ZSTD is not available. GRASS 8 uses by default 1 as ZLIB compression
level which is the best compromise between speed and compression ratio,
also when compared to other available compression methods. Valid levels
are in the range [1, 9] and can be set with the environment variable GRASS_ZLIB_LEVEL .

LZ4 LZ4 is a very fast compression method, about as fast as no compression.
Decompression is also very fast. The compression ratio is generally
higher than for RLE but worse than for ZLIB. LZ4 is recommended if disk
space is not a limiting factor.

BZIP2 BZIP2 can provide compression ratios much higher than the other methods,
but only for large raster maps (> 10000 columns). For large raster
maps, disk space consumption can be reduced by 30 - 50% when using BZIP2
instead of ZLIB's deflate. BZIP2 is the slowest compression and
decompression method. However, if reading from / writing to a storage
device is the limiting factor, BZIP2 compression can speed up raster map
processing. Be aware that for smaller raster maps, BZIP2 compression
ratio can be worse than other compression methods.

ZSTD ZSTD (Zstandard) provides compression ratios higher than ZLIB but lower
than BZIP2 (for large data). ZSTD compresses up to 4x faster than ZLIB,
and usually decompresses 6x faster than ZLIB. ZSTD is the default
compression method if available.

---

## See Also

Related tools:
- [`r.info`](https://grass.osgeo.org/grass-devel/manuals/r.info.html)
- [`r.null`](https://grass.osgeo.org/grass-devel/manuals/r.null.html)
- [`r.support`](https://grass.osgeo.org/grass-devel/manuals/r.support.html)

---

## Authors

James Westervelt and Michael Shapiro, U.S. Army Construction Engineering
Research Laboratory
Markus Metz

---

## Resources

- [Official r.compress manual](https://grass.osgeo.org/grass-devel/manuals/r.compress.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.compress.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
