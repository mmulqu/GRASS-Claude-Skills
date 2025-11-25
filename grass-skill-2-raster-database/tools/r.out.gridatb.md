# r.out.gridatb

**Category**: raster

## Description

Exports GRASS raster map to GRIDATB.FOR map file (TOPMODEL).

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_out_gridatb(input,output,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str | np.ndarray, required`**
   - Name of input raster map
   - Used as: input, raster, name

2. **`output : str, required`**
   - Name for output file
   - Used as: output, file, name

3. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

4. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

5. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

6. **`superquiet : bool, optional`**
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

r.out.gridatb exports a GRASS raster map to GRIDATB.FOR map file
(TOPMODEL)

---

## See Also

Related tools:
- [`r.topmodel`](https://grass.osgeo.org/grass-devel/manuals/r.topmodel.html)
- [`r.in.gridatb`](https://grass.osgeo.org/grass-devel/manuals/r.in.gridatb.html)

---

## Resources

- [Official r.out.gridatb manual](https://grass.osgeo.org/grass-devel/manuals/r.out.gridatb.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.out.gridatb.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
