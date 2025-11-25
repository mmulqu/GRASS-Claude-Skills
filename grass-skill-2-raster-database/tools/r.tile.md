# r.tile

**Category**: raster

## Description

Splits a raster map into tiles.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_tile(input,output,width,height,overlap=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str | np.ndarray, required`**
   - Name of input raster map
   - Used as: input, raster, name

2. **`output : str, required`**
   - Output base name

3. **`width : int, required`**
   - Width of tiles (columns)

4. **`height : int, required`**
   - Height of tiles (rows)

5. **`overlap : int, optional`**
   - Overlap of tiles

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

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

r.tile retiles an existing raster map with user defined x and y tile
size.

---

## See Also

Related tools:
- [`g.region`](https://grass.osgeo.org/grass-devel/manuals/g.region.html)
- [`r3.retile`](https://grass.osgeo.org/grass-devel/manuals/r3.retile.html)

---

## Resources

- [Official r.tile manual](https://grass.osgeo.org/grass-devel/manuals/r.tile.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.tile.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
