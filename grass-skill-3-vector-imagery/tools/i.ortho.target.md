# i.ortho.target

**Category**: imagery

## Description

Select or modify the imagery group target.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.i_ortho_target(group,target_project,target_mapset,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`group : str, required`**
   - Name of imagery group for ortho-rectification
   - Used as: input, group, name

2. **`target_project : str, required`**
   - Project (location) name
   - Name of target project (location) for ortho-rectification
   - Used as: input, location, name

3. **`target_mapset : str, required`**
   - Name of mapset (default: current search path)
   - Name of target mapset for ortho-rectification
   - Used as: input, mapset, name

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

i.ortho.target sets the image group target project (location) and
mapset.

---

## See Also

Related tools:
- [`i.ortho.photo`](https://grass.osgeo.org/grass-devel/manuals/i.ortho.photo.html)
- [`i.ortho.elev`](https://grass.osgeo.org/grass-devel/manuals/i.ortho.elev.html)
- [`i.ortho.camera`](https://grass.osgeo.org/grass-devel/manuals/i.ortho.camera.html)
- [`g.gui.photo2image`](https://grass.osgeo.org/grass-devel/manuals/g.gui.photo2image.html)
- [`g.gui.image2target`](https://grass.osgeo.org/grass-devel/manuals/g.gui.image2target.html)
- [`i.ortho.init`](https://grass.osgeo.org/grass-devel/manuals/i.ortho.init.html)
- [`i.ortho.rectify`](https://grass.osgeo.org/grass-devel/manuals/i.ortho.rectify.html)

---

## Resources

- [Official i.ortho.target manual](https://grass.osgeo.org/grass-devel/manuals/i.ortho.target.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/i.ortho.target.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
