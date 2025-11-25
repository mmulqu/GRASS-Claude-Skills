# v.type

**Category**: vector

## Description

Changes type of vector features.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.v_type(input,layer="-1",output,from_type="line",to_type="boundary",overwrite=None,verbose=None,quiet=None,superquiet=None)
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

4. **`from_type : str, required`**
   - Feature type to convert from
   - Allowed values: point, line, boundary, centroid, face, kernel
   - Default: line

5. **`to_type : str, required`**
   - Feature type to convert to
   - Allowed values: point, line, boundary, centroid, face, kernel
   - Default: boundary

6. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

7. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

8. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

9. **`superquiet : bool, optional`**
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

v.type changes the type of geometry primitives.

The following vector object types are defined in GRASS:

Lines and boundaries can be composed of multiple vertices.

Area topology also holds information about isles. These isles are
located within that area, not touching the boundaries of the outer area.
Isles are holes inside the area, and can consist of one or more areas.
They are used internally to maintain correct topology for areas.

---

## See Also

Related tools:
- [`v.centroids`](https://grass.osgeo.org/grass-devel/manuals/v.centroids.html)
- [`v.to.points`](https://grass.osgeo.org/grass-devel/manuals/v.to.points.html)

---

## Resources

- [Official v.type manual](https://grass.osgeo.org/grass-devel/manuals/v.type.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/v.type.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
