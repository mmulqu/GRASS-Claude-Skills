# r.latlong

**Category**: raster

## Description

Creates a latitude/longitude raster map.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_latlong(input,output,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str | np.ndarray, required`**
   - Name of input raster map
   - Used as: input, raster, name

2. **`output : str | type(np.ndarray) | type(np.array) | type(gs.array.array), required`**
   - Name for output latitude or longitude raster map
   - Used as: output, raster, name

3. **`flags : str, optional`**
   - Allowed values: l
   - l
   - Longitude output

4. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

5. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

6. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

7. **`superquiet : bool, optional`**
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

r.latlong creates a latitude (degree decimal) map, or longitude if the
-l flag is used, from any map in any projection using PROJ library. This
is an input to r.sun and i.evapo.potrad .

---

## See Also

Related tools:
- [`r.sun`](https://grass.osgeo.org/grass-devel/manuals/r.sun.html)
- [`r.sunhours`](https://grass.osgeo.org/grass-devel/manuals/r.sunhours.html)

---

## Resources

- [Official r.latlong manual](https://grass.osgeo.org/grass-devel/manuals/r.latlong.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.latlong.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
