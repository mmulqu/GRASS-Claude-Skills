# g.gui.animation

**Category**: general

## Description

Tool for animating a series of raster and vector maps or a space time raster or vector dataset.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.g_gui_animation(raster=None,vector=None,strds=None,stvds=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`raster : str | list[str], optional`**
   - Raster maps to animate
   - Used as: input, raster, name

2. **`vector : str | list[str], optional`**
   - Vector maps to animate
   - Or data source(s) for direct OGR access
   - Used as: input, vector, name

3. **`strds : str, optional`**
   - Space time raster dataset to animate
   - Used as: input, strds, name

4. **`stvds : str, optional`**
   - Space time vector dataset to animate
   - Used as: input, stvds, name

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

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

The Animation Tool is a wxGUI component for animating
series of GRASS raster or vector maps or space time datasets (created by
t.* modules).

Animation Tool allows you to:

3D view animation enables to animate raster (as an elevation map or a
color map) or vector map (points, lines). Internally, module m.nviz.image is used. To display 3D view animation
follow these steps:



---

## Note

The Animation Tool follows the computational region settings, so please
be sure your computational region is set to the geographic extent of
maps you are animating. You can change the computational region (using g.region ) and then reload the maps to update the
animation.

---

## See Also

Related tools:

---

## Resources

- [Official g.gui.animation manual](https://grass.osgeo.org/grass-devel/manuals/g.gui.animation.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/g.gui.animation.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
