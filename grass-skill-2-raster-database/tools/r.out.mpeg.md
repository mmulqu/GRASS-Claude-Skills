# r.out.mpeg

**Category**: raster

## Description

Converts raster map series to MPEG movie.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_out_mpeg(view1,view2=None,view3=None,view4=None,output,quality=3,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`view1 : str | list[str], required`**
   - Name of input raster map(s) for view no.1
   - Used as: input, raster, name

2. **`view2 : str | list[str], optional`**
   - Name of input raster map(s) for view no.2
   - Used as: input, raster, name

3. **`view3 : str | list[str], optional`**
   - Name of input raster map(s) for view no.3
   - Used as: input, raster, name

4. **`view4 : str | list[str], optional`**
   - Name of input raster map(s) for view no.4
   - Used as: input, raster, name

5. **`output : str, required`**
   - Name for output file
   - Used as: output, file, name

6. **`quality : int, optional`**
   - Quality factor (1 = highest quality, lowest compression)
   - Allowed values: 1-5
   - Default: 3

7. **`flags : str, optional`**
   - Allowed values: c
   - c
   - Convert on the fly, uses less disk space

8. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

9. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

10. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

11. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 11 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/r.out.mpeg.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

r.out.mpeg is a tool for combining a series of GRASS raster maps into
a single MPEG-1 ( Motion Pictures Experts
Group )
format file. MPEG-1 is a "lossy" video compression format, so the
quality of each resulting frame of the animation will be much diminished
from the original raster image. The resulting output file may then be
viewed using your favorite mpeg-format viewing program. MPEG-2 and
MPEG-4 provide much better quality animations.

The user may define up to four "views", or sub-windows, to animate
simultaneously. e.g., View 1 could be rainfall, View 2 flooded areas,
View 3 damage to bridges or levees, View 4 other economic damage, all
animated as a time series. A black border 2 pixels wide is drawn around
each view. There is an arbitrary limit of 400 files per view (400
animation frames). Temporary files are created in the conversion
process, so lack of adequate tmp space could also limit the number of
frames you are able to convert.

The environment variable GMPEG_SIZE is checked for a value to use as the
dimension, in pixels, of the longest dimension of the animation image.
If GMPEG_SIZE is not set, the animation size defaults to the rows &
columns in the current GRASS region, scaling if necessary to a default
minimum size of 200 and maximum of 500. These size defaults are
overridden when using the -c flag (see below). The resolution of the
current GRASS region is maintained, independent of image size. Playback
programs have to decode the compressed data "on-the-fly", therefore
smaller dimensioned animations will provide higher frame rates and
smoother animations.

UNIX - style wild cards may be used with the command line version in
place of a raster map name, but wild cards must be quoted.

A quality value of quality=1 will yield higher quality images, but
with less compression (larger MPEG file size). Compression ratios will
vary depending on the number of frames in the animation, but an MPEG
produced using quality=5 will usually be about 60% the size of the
MPEG produced using quality=1 .

---

## See Also

Related tools:
- [`r.out.ppm`](https://grass.osgeo.org/grass-devel/manuals/r.out.ppm.html)

---

## Resources

- [Official r.out.mpeg manual](https://grass.osgeo.org/grass-devel/manuals/r.out.mpeg.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.out.mpeg.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
