# i.ortho.elev

**Category**: imagery

## Description

Select or modify the target elevation model.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.i_ortho_elev(group,project=None,mapset=None,elevation=None,math_expression=None,units=None,null_value=None,flags=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`group : str, required`**
   - Name of imagery group for ortho-rectification
   - Used as: input, group, name

2. **`project : str, optional`**
   - Project (location) name
   - Name of the target project (location)
   - Used as: input, location, name

3. **`mapset : str, optional`**
   - Name of mapset (default: current search path)
   - Name of the target mapset
   - Used as: input, mapset, name

4. **`elevation : str | np.ndarray, optional`**
   - Name of elevation map to use for ortho-rectification
   - Used as: input, raster, name

5. **`math_expression : str, optional`**
   - Math expression to convert to real elevation
   - Used as: string

6. **`units : str, optional`**
   - Unit of the elevation map
   - Allowed values: miles, feet, meters, kilometers, acres, hectares

7. **`null_value : str, optional`**
   - No data value
   - Used as: string

8. **`flags : str, optional`**
   - Allowed values: p
   - p
   - Print currently selected elevation map and exit

9. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

10. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

11. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 11 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/i.ortho.elev.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

i.ortho.elev is used to select or modify the target elevation model
for orthorectification of imagery. This elevation model is essential for
both the computation of photo-to-target parameters and for the actual
orthorectification of imagery group files. The elevation model selected
should cover the entire area of the image group to be orthorectified.
Optionally, scaled elevation data can be converted to real elevation
values specifying a mathematical expression.

---

## See Also

Related tools:
- [`i.ortho.photo`](https://grass.osgeo.org/grass-devel/manuals/i.ortho.photo.html)
- [`i.ortho.camera`](https://grass.osgeo.org/grass-devel/manuals/i.ortho.camera.html)
- [`g.gui.photo2image`](https://grass.osgeo.org/grass-devel/manuals/g.gui.photo2image.html)
- [`g.gui.image2target`](https://grass.osgeo.org/grass-devel/manuals/g.gui.image2target.html)
- [`i.ortho.init`](https://grass.osgeo.org/grass-devel/manuals/i.ortho.init.html)
- [`i.rectify`](https://grass.osgeo.org/grass-devel/manuals/i.rectify.html)

---

## Authors

Mike Baba, DBA Systems, Inc. Bugfixes and enhancements for GRASS GIS 7 by Markus Metz

---

## Resources

- [Official i.ortho.elev manual](https://grass.osgeo.org/grass-devel/manuals/i.ortho.elev.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/i.ortho.elev.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
