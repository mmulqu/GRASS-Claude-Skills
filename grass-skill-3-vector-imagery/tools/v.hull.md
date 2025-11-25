# v.hull

**Category**: vector

## Description

Produces a 2D/3D convex hull for a given vector map.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.v_hull(input,layer="-1",output,cats=None,where=None,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
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

4. **`cats : str, optional`**
   - Category values
   - Example: 1,3,7-9,13
   - Used as: input, cats, range

5. **`where : str, optional`**
   - WHERE conditions of SQL statement without 'where' keyword
   - Example: income < 1000 and population >= 10000
   - Used as: input, sql_query, sql_query

6. **`flags : str, optional`**
   - Allowed values: r, f
   - r
   - Limit to current region
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/v.hull.html#__tabbed_2_3) for all details)*

7. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

8. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

9. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

10. **`superquiet : bool, optional`**
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

v.hull computes the convex hull of a vector map and outputs the convex
hull polygon as a vector area map. The convex hull, or convex envelope,
for an object or a set of objects is the minimal convex set containing
the given objects. This module creates a vector polygon containing all
vector points or lines of the input map.

In the case of 3D input points, the hull will be a 3D hull as well,
unless the user specifies the -f flag. The 3D hull will be composed
of triangular faces.

Fig: Convex hull polygon created with v.hull

---

## See Also

Related tools:
- [`v.delaunay`](https://grass.osgeo.org/grass-devel/manuals/v.delaunay.html)

---

## Authors

Andrea Aime, Modena, Italy Markus Neteler, ITC-irst (update to 5.7) Benjamin Ducke, CAU Kiel (3D hull support) Martin Landa, CTU in Prague, Czech Republic (vector lines support)

---

## Resources

- [Official v.hull manual](https://grass.osgeo.org/grass-devel/manuals/v.hull.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/v.hull.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
