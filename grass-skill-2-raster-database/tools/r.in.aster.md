# r.in.aster

**Category**: raster

## Description

Georeference, rectify, and import Terra-ASTER imagery and relative DEMs using gdalwarp.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_in_aster(input,proctype="L1B",band="all",output,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str | io.StringIO, required`**
   - Name of input ASTER image
   - Used as: input, file, name

2. **`proctype : str, required`**
   - ASTER imagery processing type (Level 1A, Level 1B, or relative DEM)
   - Allowed values: L1A, L1B, L1T, DEM
   - Default: L1B

3. **`band : str, required`**
   - List L1A L1B or L1T band to translate (1,2,3n,...), or enter 'all' to translate all bands
   - Default: all

4. **`output : str | type(np.ndarray) | type(np.array) | type(gs.array.array), required`**
   - Base name for output raster map (band number will be appended to base name)
   - Used as: output, raster, name

5. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

6. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

7. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

8. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None

### Returns

result : grass.tools.support.ToolResult | np.ndarray | tuple[np.ndarray] | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned. If an array type (e.g., np.ndarray) is used for one of the raster outputs, the result will be an array and will have the shape corresponding to the computational region. If an array type is used for more than one raster output, the result will be a tuple of arrays.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

r.in.aster rectifies, georeferences, and imports Terra-ASTER imagery
to current project using gdalwarp, hdf 4, and r.in.gdal, using
projection parameters from g.proj. It can import Level 1A, Level 1B,
their relative DEM products, and Level 1T.

The program may be run interactively or non-interactively from the
command line. In either case, the user must specify an input *.hdf
file name, the type of processing used, the image band to
import, and an output GRASS raster map name.

The type parameter can take values of L1A, L1B, L1T or DEM.

The band parameter can take values of 1, 2, 3n, 3b, 4-14

---

## Authors

Michael Barton, Arizona State University and Paul Kelly

---

## Resources

- [Official r.in.aster manual](https://grass.osgeo.org/grass-devel/manuals/r.in.aster.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.in.aster.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
