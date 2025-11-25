# r.to.rast3

**Category**: raster

## Description

Converts 2D raster map slices to one 3D raster volume map.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_to_rast3(input,output,tilesize=32,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str | list[str], required`**
   - 2D raster maps which represent the slices
   - Used as: input, raster, name

2. **`output : str, required`**
   - Name for output 3D raster map
   - Used as: output, raster_3d, name

3. **`tilesize : int, optional`**
   - The maximum tile size in kilo bytes. Default is 32KB.
   - Default: 32

4. **`flags : str, optional`**
   - Allowed values: m
   - m
   - Use 3D raster mask (if exists) with output map

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

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

r.to.rast3 converts 2D raster map(s) into one raster3D map. It is
important to properly set the 3D region settings, especially number or
layers and depth of layers. If the 2D and 3D region settings are
different, the 2D resolution will be adjusted to the 3D resolution.

How r.to.rast3 works

---

## See Also

Related tools:
- [`g.region`](https://grass.osgeo.org/grass-devel/manuals/g.region.html)
- [`r3.to.rast`](https://grass.osgeo.org/grass-devel/manuals/r3.to.rast.html)
- [`r.to.rast3elev`](https://grass.osgeo.org/grass-devel/manuals/r.to.rast3elev.html)

---

## Resources

- [Official r.to.rast3 manual](https://grass.osgeo.org/grass-devel/manuals/r.to.rast3.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.to.rast3.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
