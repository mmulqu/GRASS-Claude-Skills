# r.in.ascii

**Category**: raster

## Description

Converts a GRASS ASCII raster file to binary raster map.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_in_ascii(input,output,type=None,title=None,multiplier=None,null_value=None,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str | io.StringIO, required`**
   - Name of input file to be imported
   - '-' for standard input
   - Used as: input, file, name

2. **`output : str | type(np.ndarray) | type(np.array) | type(gs.array.array), required`**
   - Name for output raster map
   - Used as: output, raster, name

3. **`type : str, optional`**
   - Type of raster map to be created
   - Default: CELL for integer values, DCELL for floating-point values
   - Allowed values: CELL, FCELL, DCELL
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/r.in.ascii.html#__tabbed_2_3) for all details)*

4. **`title : str, optional`**
   - Title for resultant raster map
   - Used as: phrase

5. **`multiplier : float, optional`**
   - Multiplier for ASCII data
   - Default: read from header

6. **`null_value : str, optional`**
   - String representing NULL value data cell
   - Default: read from header
   - Used as: string

7. **`flags : str, optional`**
   - Allowed values: s
   - s
   - SURFER (Golden Software) ASCII file will be imported

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


*Showing 10 of 11 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/r.in.ascii.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | np.ndarray | tuple[np.ndarray] | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned. If an array type (e.g., np.ndarray) is used for one of the raster outputs, the result will be an array and will have the shape corresponding to the computational region. If an array type is used for more than one raster output, the result will be a tuple of arrays.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

r.in.ascii allows a user to create a (binary) GRASS raster map layer
from an ASCII raster input file with (optional) TITLE.

The GRASS ASCII input file has a header section which describes the
location and size of the data, followed by the data itself.

The header has 6 lines:

The north, south, east, and west field values entered are the
coordinates of the edges of the geographic region. The rows and cols
field values entered describe the dimensions of the matrix of data to
follow. The data which follows is r rows of c integers.

Optionally the following parameters can be defined in the header
section:

"null" defines a string or number to be converted to NULL value (no
data). "type" defines the data type (int, float double) and is not required. "multiplier" is an optional parameter to multiply each cell value.

---

## See Also

Related tools:
- [`r.import`](https://grass.osgeo.org/grass-devel/manuals/r.import.html)
- [`r.out.ascii`](https://grass.osgeo.org/grass-devel/manuals/r.out.ascii.html)
- [`r.in.gdal`](https://grass.osgeo.org/grass-devel/manuals/r.in.gdal.html)
- [`r.out.gdal`](https://grass.osgeo.org/grass-devel/manuals/r.out.gdal.html)
- [`r.in.bin`](https://grass.osgeo.org/grass-devel/manuals/r.in.bin.html)
- [`r3.in.ascii`](https://grass.osgeo.org/grass-devel/manuals/r3.in.ascii.html)

---

## Authors

Michael Shapiro, U.S. Army Construction Engineering Research
Laboratory Surfer support by Roger Miller

---

## Resources

- [Official r.in.ascii manual](https://grass.osgeo.org/grass-devel/manuals/r.in.ascii.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.in.ascii.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
