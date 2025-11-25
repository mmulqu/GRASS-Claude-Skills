# r.in.bin

**Category**: raster

## Description

Import a binary raster file into a GRASS raster map layer.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_in_bin(input,output,title=None,bytes=None,header=0,bands=1,order="native",north=None,south=None,east=None,west=None,rows=None,cols=None,anull=None,flip=None,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str, required`**
   - Name of binary raster file to be imported
   - Used as: input, file, name

2. **`output : str | type(np.ndarray) | type(np.array) | type(gs.array.array), required`**
   - Output name or prefix if several bands are imported
   - Used as: output, raster, name

3. **`title : str, optional`**
   - Title for resultant raster map
   - Used as: phrase

4. **`bytes : int, optional`**
   - Number of bytes per cell
   - Allowed values: 1, 2, 4, 8

5. **`header : int, optional`**
   - Header size in bytes
   - Default: 0

6. **`bands : int, optional`**
   - Number of bands in input file
   - Bands must be in band-sequential order
   - Default: 1

7. **`order : str, optional`**
   - Output byte order
   - Allowed values: big, little, native, swap
   - Default: native

8. **`north : float, optional`**
   - Northern limit of geographic region (outer edge)

9. **`south : float, optional`**
   - Southern limit of geographic region (outer edge)

10. **`east : float, optional`**
   - Eastern limit of geographic region (outer edge)

11. **`west : float, optional`**
   - Western limit of geographic region (outer edge)

12. **`rows : int, optional`**
   - Number of rows

13. **`cols : int, optional`**
   - Number of columns

14. **`anull : float, optional`**
   - Set Value to NULL

15. **`flip : str | list[str], optional`**
   - Flip input horizontal and/or vertical
   - Allowed values: h, v
   - h: Flip input horizontal (East - West)

16. **`flags : str, optional`**
   - Allowed values: f, d, s, b, h
   - f
   - Import as floating-point data (default: integer)
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/r.in.bin.html#__tabbed_2_3) for all details)*

17. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

18. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

19. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

20. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 20 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/r.in.bin.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | np.ndarray | tuple[np.ndarray] | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned. If an array type (e.g., np.ndarray) is used for one of the raster outputs, the result will be an array and will have the shape corresponding to the computational region. If an array type is used for more than one raster output, the result will be a tuple of arrays.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

r.in.bin allows the user to create a (binary) GRASS raster map layer
from a variety of binary raster data formats.

The -s flag is used for importing two's-complement signed data.

The -h flag is used to read region information from a Generic
Mapping Tools (GMT) type binary header. It is compatible with GMT binary
grid types 1 and 2.

The north, south, east, and west field values are the coordinates of the
edges of the geographic region. The rows and cols values describe the
dimensions of the matrix of data to follow. If the input is a GMT binary array (-h flag),
the six dimension fields (north, south, east, west, rows and cols) are
obtained from the GMT header. If the bytes field is entered incorrectly
an error will be generated suggesting a closer bytes value.

r.in.bin can be used to import numerous binary arrays including:
ETOPO30, ETOPO-5, ETOPO-2, Globe DEM, BIL, AVHRR and GMT binary arrays
(ID 1 & 2).

---

## See Also

Related tools:
- [`r.import`](https://grass.osgeo.org/grass-devel/manuals/r.import.html)
- [`r.out.bin`](https://grass.osgeo.org/grass-devel/manuals/r.out.bin.html)
- [`r.in.ascii`](https://grass.osgeo.org/grass-devel/manuals/r.in.ascii.html)
- [`r.out.ascii`](https://grass.osgeo.org/grass-devel/manuals/r.out.ascii.html)
- [`r.in.gdal`](https://grass.osgeo.org/grass-devel/manuals/r.in.gdal.html)
- [`r.out.gdal`](https://grass.osgeo.org/grass-devel/manuals/r.out.gdal.html)
- [`r.in.srtm`](https://grass.osgeo.org/grass-devel/manuals/r.in.srtm.html)

---

## Authors

Jacques Bouchard, France ( bouchard@onera.fr ) Bob Covill, Canada ( bcovill@tekmap.ns.ca ) Markus Metz Man page: Zsolt Felker ( felker@c160.pki.matav.hu )

---

## Resources

- [Official r.in.bin manual](https://grass.osgeo.org/grass-devel/manuals/r.in.bin.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.in.bin.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
