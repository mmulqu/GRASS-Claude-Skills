# v.to.lines

**Category**: vector

## Description

Converts vector polygons or points to lines.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.v_to_lines(input,output,method="delaunay",overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str, required`**
   - Name of input vector map
   - Or data source for direct OGR access
   - Used as: input, vector, name

2. **`output : str, required`**
   - Name for output vector map
   - Used as: output, vector, name

3. **`method : str, optional`**
   - Method used for point interpolation
   - Allowed values: delaunay
   - Default: delaunay

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

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

v.to.lines converts vector polygons (boundaries) to lines as well as
vector points to lines via triangulations.

---

## See Also

Related tools:
- [`v.category`](https://grass.osgeo.org/grass-devel/manuals/v.category.html)
- [`v.delaunay`](https://grass.osgeo.org/grass-devel/manuals/v.delaunay.html)
- [`v.edit`](https://grass.osgeo.org/grass-devel/manuals/v.edit.html)
- [`v.in.lines`](https://grass.osgeo.org/grass-devel/manuals/v.in.lines.html)
- [`v.to.points`](https://grass.osgeo.org/grass-devel/manuals/v.to.points.html)
- [`v.type`](https://grass.osgeo.org/grass-devel/manuals/v.type.html)

---

## Resources

- [Official v.to.lines manual](https://grass.osgeo.org/grass-devel/manuals/v.to.lines.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/v.to.lines.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
