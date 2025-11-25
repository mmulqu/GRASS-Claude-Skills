# i.albedo

**Category**: imagery

## Description

Computes broad band albedo from surface reflectance.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.i_albedo(input,output,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str | list[str], required`**
   - Name of input raster map
   - Used as: input, raster, name

2. **`output : str | type(np.ndarray) | type(np.array) | type(gs.array.array), required`**
   - Name for output raster map
   - Used as: output, raster, name

3. **`flags : str, optional`**
   - Allowed values: m, n, l, 8, a, c, d
   - m
   - MODIS (7 input bands:1,2,3,4,5,6,7)
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/i.albedo.html#__tabbed_2_3) for all details)*

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

i.albedo calculates the albedo, that is the Shortwave surface
reflectance in the range of 0.3-3 micro-meters. It takes as input
individual bands of surface reflectance originating from MODIS, AVHRR,
Landsat or Aster satellite sensors and calculates the albedo for those.
This is a precursor to r.sun and any energy-balance processing.

---

## See Also

Related tools:
- [`r.sun`](https://grass.osgeo.org/grass-devel/manuals/r.sun.html)
- [`i.vi`](https://grass.osgeo.org/grass-devel/manuals/i.vi.html)

---

## Resources

- [Official i.albedo manual](https://grass.osgeo.org/grass-devel/manuals/i.albedo.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/i.albedo.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
