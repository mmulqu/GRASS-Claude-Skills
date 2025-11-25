# v.delaunay

**Category**: vector

## Description

Creates a Delaunay triangulation from an input vector map containing points or centroids.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.v_delaunay(input,layer="-1",output,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
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

4. **`flags : str, optional`**
   - Allowed values: r, l
   - r
   - Use only points in current region
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/v.delaunay.html#__tabbed_2_3) for all details)*

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

v.delaunay uses an existing vector points map ( input ) to create a
Delaunay triangulation vector map ( output ).

Delaunay triangulation example (red-yellow points are the data points
from which the triangulation was generated):



---

## See Also

Related tools:
- [`v.voronoi`](https://grass.osgeo.org/grass-devel/manuals/v.voronoi.html)
- [`v.hull`](https://grass.osgeo.org/grass-devel/manuals/v.hull.html)

---

## Authors

Martin Pavlovsky, Google Summer of Code 2008, Student Paul Kelly, Mentor Based on "dct" by Geoff Leach, Department of Computer Science, RMIT.

---

## Resources

- [Official v.delaunay manual](https://grass.osgeo.org/grass-devel/manuals/v.delaunay.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/v.delaunay.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
