# v.to.points

**Category**: vector

## Description

Creates points along input lines in new vector map with 2 layers.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.v_to_points(input,layer="1",type="point,line,boundary,centroid,face",output,use=None,dmax=100,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str, required`**
   - Name of input vector map
   - Or data source for direct OGR access
   - Used as: input, vector, name

2. **`layer : str, optional`**
   - Line layer number or name
   - Vector features can have category values in different layers. This number determines which layer to use. When used with direct OGR access this is the layer name.
   - Used as: input, layer

3. **`type : str | list[str], optional`**
   - Input feature type
   - Allowed values: point, line, boundary, centroid, area, face, kernel
   - Default: point,line,boundary,centroid,face

4. **`output : str, required`**
   - Name for output vector map
   - Used as: output, vector, name

5. **`use : str, optional`**
   - Use line nodes (start/end) or vertices only
   - Allowed values: node, start, end, vertex

6. **`dmax : float, optional`**
   - Maximum distance between points in map units or percentage with -p
   - Default: 100

7. **`flags : str, optional`**
   - Allowed values: i, p, r, t
   - i
   - Interpolate points between line vertices (only for use=vertex)
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/v.to.points.html#__tabbed_2_3) for all details)*

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


*Showing 10 of 11 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/v.to.points.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

v.to.points creates points along input 2D or 3D lines, boundaries and
faces. Point features including centroids and kernels are copied from
input vector map to the output. For details see notes about type parameter.

The output is a vector map with 2 layers. Layer 1 holds the category of
the input features; all points created along the same line have the same
category, equal to the category of that line. In layer 2 each point has
its unique category; other attributes stored in layer 2 are lcat - the
category of the input line and along - the distance from line's start.

By default only features with category are processed, see layer parameter for details.

---

## See Also

Related tools:
- [`v.segment`](https://grass.osgeo.org/grass-devel/manuals/v.segment.html)
- [`v.split`](https://grass.osgeo.org/grass-devel/manuals/v.split.html)
- [`v.to.rast`](https://grass.osgeo.org/grass-devel/manuals/v.to.rast.html)
- [`v.to.db`](https://grass.osgeo.org/grass-devel/manuals/v.to.db.html)

---

## Authors

Radim Blazek Updated to GRASS 7 by Martin Landa, Czech Technical University in
Prague, Czech Republic

---

## Resources

- [Official v.to.points manual](https://grass.osgeo.org/grass-devel/manuals/v.to.points.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/v.to.points.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
