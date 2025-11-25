# d.to.rast

**Category**: display

## Description

Saves the contents of the active display monitor to a raster map.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.d_to_rast(output,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`output : str | type(np.ndarray) | type(np.array) | type(gs.array.array), required`**
   - Name for output raster map
   - Used as: output, raster, name

2. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

3. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

4. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

5. **`superquiet : bool, optional`**
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

d.to.rast saves the content of the currently selected monitor into a
raster map. The active monitor can be selected with d.mon . d.to.rast can be run from GUI Console tab, too. This module is not sensitive to
computational region settings.

---

## See Also

Related tools:
- [`d.out.file`](https://grass.osgeo.org/grass-devel/manuals/d.out.file.html)
- [`d.erase`](https://grass.osgeo.org/grass-devel/manuals/d.erase.html)
- [`d.rast`](https://grass.osgeo.org/grass-devel/manuals/d.rast.html)
- [`d.vect`](https://grass.osgeo.org/grass-devel/manuals/d.vect.html)
- [`d.mon`](https://grass.osgeo.org/grass-devel/manuals/d.mon.html)

---

## Resources

- [Official d.to.rast manual](https://grass.osgeo.org/grass-devel/manuals/d.to.rast.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/d.to.rast.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
