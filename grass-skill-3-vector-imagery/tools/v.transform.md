# v.transform

**Category**: vector

## Description

Performs an affine transformation (shift, scale and rotate) on vector map.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.v_transform(input,layer="-1",output,xshift=0.0,yshift=0.0,zshift=0.0,xscale=1.0,yscale=1.0,zscale=1.0,zrotation=0.0,columns=None,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str, required`**
   - Name of input vector map
   - Or data source for direct OGR access
   - Used as: input, vector, name

2. **`layer : str, optional`**
   - Layer number or name ('-1' for all layers)
   - A single vector map can be connected to multiple database tables. This number determines which table to use. When used with direct OGR access this is the layer name.
   - Used as: input, layer

3. **`output : str, required`**
   - Name for output vector map
   - Used as: output, vector, name

4. **`xshift : float, optional`**
   - Shifting value for x coordinates
   - Default: 0.0

5. **`yshift : float, optional`**
   - Shifting value for y coordinates
   - Default: 0.0

6. **`zshift : float, optional`**
   - Shifting value for z coordinates
   - Default: 0.0

7. **`xscale : float, optional`**
   - Scaling factor for x coordinates
   - Default: 1.0

8. **`yscale : float, optional`**
   - Scaling factor for y coordinates
   - Default: 1.0

9. **`zscale : float, optional`**
   - Scaling factor for z coordinates
   - Default: 1.0

10. **`zrotation : float, optional`**
   - Rotation around z axis in degrees (counter-clockwise)
   - Default: 0.0

11. **`columns : str | list[str], optional`**
   - Name of attribute column(s) used as transformation parameters
   - Format: parameter:column, e.g. xshift:xs,yshift:ys,zrot:zr
   - Used as: input, dbcolumn, name

12. **`flags : str, optional`**
   - Allowed values: t, w, x, y, a, b
   - t
   - Shift all z values to bottom=0
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/v.transform.html#__tabbed_2_3) for all details)*

13. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

14. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

15. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

16. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 16 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/v.transform.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

v.transform performs an affine transformation (translate and rotate)
of a vector map. An affine transform includes one or several linear
transformations (scaling, rotation) and translation (shifting). Several
linear transformations can be combined in a single operation. The
command can be used to georeference unreferenced vector maps or to
modify existing geocoded maps.

---

## See Also

Related tools:
- [`m.transform`](https://grass.osgeo.org/grass-devel/manuals/m.transform.html)
- [`i.rectify`](https://grass.osgeo.org/grass-devel/manuals/i.rectify.html)
- [`v.rectify`](https://grass.osgeo.org/grass-devel/manuals/v.rectify.html)
- [`r.region`](https://grass.osgeo.org/grass-devel/manuals/r.region.html)

---

## Authors

Radim Blazek, ITC-irst, Trento, Italy, Column support added by Martin Landa, FBK-irst (formerly ITC-irst),
Trento, Italy (2007/09)

---

## Resources

- [Official v.transform manual](https://grass.osgeo.org/grass-devel/manuals/v.transform.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/v.transform.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
