# v.to.3d

**Category**: vector

## Description

Performs transformation of 2D vector features to 3D.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.v_to_3d(input,layer="1",type="point,line,boundary,centroid",output,column=None,height=None,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
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

3. **`type : str | list[str], optional`**
   - Input feature type
   - Allowed values: point, line, boundary, centroid
   - Default: point,line,boundary,centroid

4. **`output : str, required`**
   - Name for output vector map
   - Used as: output, vector, name

5. **`column : str, optional`**
   - Name of attribute column used for height
   - Can be used for reverse transformation, to store height of points
   - Used as: input, dbcolumn, name

6. **`height : float, optional`**
   - Fixed height for 3D vector features

7. **`flags : str, optional`**
   - Allowed values: r, t
   - r
   - Reverse transformation; 3D vector features to 2D
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/v.to.3d.html#__tabbed_2_3) for all details)*

8. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

9. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

10. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

11. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 11 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/v.to.3d.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

The v.to.3d module is used to transform 2D vector features to 3D.
Height (z-coordinate) of 3D vector features can be specified by height parameter as fixed value or by column parameter.

The flag -r enables to perform reverse transformation, i.e.,
transform 3D vector to 2D by omitting z-coordinate. The height of input
3D features can be optionally stored in column .

---

## See Also

Related tools:
- [`v.transform`](https://grass.osgeo.org/grass-devel/manuals/v.transform.html)
- [`v.extrude`](https://grass.osgeo.org/grass-devel/manuals/v.extrude.html)
- [`v.drape`](https://grass.osgeo.org/grass-devel/manuals/v.drape.html)

---

## Resources

- [Official v.to.3d manual](https://grass.osgeo.org/grass-devel/manuals/v.to.3d.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/v.to.3d.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
