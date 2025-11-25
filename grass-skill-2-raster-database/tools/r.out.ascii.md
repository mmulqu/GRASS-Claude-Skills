# r.out.ascii

**Category**: raster

## Description

Converts a raster map layer into a GRASS ASCII text file.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_out_ascii(input,output=None,precision=None,width=None,null_value="*",flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str | np.ndarray, required`**
   - Name of input raster map
   - Used as: input, raster, name

2. **`output : str, optional`**
   - Name for output ASCII grid map (use out=- for stdout)
   - Used as: output, file, name

3. **`precision : int, optional`**
   - Number of significant digits (floating point only)

4. **`width : int, optional`**
   - Number of values printed before wrapping a line (only SURFER or MODFLOW format)

5. **`null_value : str, optional`**
   - String to represent null cell (GRASS grid only)
   - Used as: string
   - Default: *

6. **`flags : str, optional`**
   - Allowed values: h, s, m, l, i
   - h
   - Suppress printing of header information
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/r.out.ascii.html#__tabbed_2_3) for all details)*

7. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

8. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

9. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

10. **`superquiet : bool, optional`**
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

r.out.ascii converts a user-specified raster map layer
( input = name ) into an ASCII grid in a text file ( output = name )
suitable for export to other computer systems.

The GRASS program r.in.ascii can be used to perform
the reverse function, converting an ASCII file in suitable format to
GRASS raster map format.

To write a SURFER .grd ASCII GRID file (with reverted row order and
different header) use the -s flag:

NULL data are coded to \"1.70141e+038\" for SURFER ASCII GRID files
(ignoring the null= parameter).

To write a LISFLOOD .dem ASCII GRID file (with different header) use the -l flag:

NULL data output are set by the user at \"-9999\" in this case, see
below:

---

## See Also

Related tools:
- [`r.in.ascii`](https://grass.osgeo.org/grass-devel/manuals/r.in.ascii.html)
- [`r.in.gdal`](https://grass.osgeo.org/grass-devel/manuals/r.in.gdal.html)
- [`r.out.bin`](https://grass.osgeo.org/grass-devel/manuals/r.out.bin.html)
- [`r.out.gdal`](https://grass.osgeo.org/grass-devel/manuals/r.out.gdal.html)
- [`r.out.xyz`](https://grass.osgeo.org/grass-devel/manuals/r.out.xyz.html)

---

## Authors

Michael Shapiro, U.S. Army Construction Engineering Research Laboratory
Surfer support by Markus Neteler

---

## Resources

- [Official r.out.ascii manual](https://grass.osgeo.org/grass-devel/manuals/r.out.ascii.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.out.ascii.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
