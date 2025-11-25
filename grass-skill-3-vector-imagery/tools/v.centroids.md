# v.centroids

**Category**: vector

## Description

Adds missing centroids to closed boundaries.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.v_centroids(input,output,option="add",layer="1",cat=1,step=1,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str, required`**
   - Name of input vector map
   - Or data source for direct OGR access
   - Used as: input, vector, name

2. **`output : str, required`**
   - Name for output vector map
   - Used as: output, vector, name

3. **`option : str, optional`**
   - Action to be taken
   - Allowed values: add
   - Default: add

4. **`layer : str, optional`**
   - Layer number or name
   - Vector features can have category values in different layers. This number determines which layer to use. When used with direct OGR access this is the layer name.
   - Used as: input, layer

5. **`cat : int, optional`**
   - Category number starting value
   - Used as: input, cats
   - Default: 1

6. **`step : int, optional`**
   - Category increment
   - Default: 1

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

In GRASS, a centroid is a point within a closed ring of boundaries.
A vector area is defined as composite entity consisting of a set of
closed boundaries and a centroid. The attribute information associated
with this area is linked to the centroid. The v.centroids module adds
centroids to closed boundaries in the input file and assigns a
category number to them. The starting value as well as the increment
size may be set using optional parameters.

Multiple attributes may be linked to a single vector entity through
numbered fields referred to as layers. Refer to v.category for more
details, as v.centroids is simply a frontend to that module.

The boundary itself is often stored without any category reference as it
can mark the border between two adjacent areas. Thus it would be
ambiguous as to which feature the attribute would belong. In some cases
it may, for example, represent a road between two parcels of land. In
this case it is entirely appropriate for the boundary to contain
category information.

---

## See Also

Related tools:
- [`v.category`](https://grass.osgeo.org/grass-devel/manuals/v.category.html)

---

## Authors

module: M. Hamish Bowman, Dept. Marine Science, Otago University, New
Zealand help page: Trevor Wiens

---

## Resources

- [Official v.centroids manual](https://grass.osgeo.org/grass-devel/manuals/v.centroids.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/v.centroids.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
