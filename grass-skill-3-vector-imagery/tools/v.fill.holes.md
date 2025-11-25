# v.fill.holes

**Category**: vector

## Description

Fill holes in areas by keeping only outer boundaries

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.v_fill_holes(input,layer="1",cats=None,where=None,output,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str, required`**
   - Name of input vector map
   - Or data source for direct OGR access
   - Used as: input, vector, name

2. **`layer : str, optional`**
   - Layer number or name
   - Vector features can have category values in different layers. This number determines which layer to use. When used with direct OGR access this is the layer name.
   - Used as: input, layer

3. **`cats : str, optional`**
   - Category values
   - Example: 1,3,7-9,13
   - Used as: input, cats, range

4. **`where : str, optional`**
   - WHERE conditions of SQL statement without 'where' keyword
   - Example: income < 1000 and population >= 10000
   - Used as: input, sql_query, sql_query

5. **`output : str, required`**
   - Name for output vector map
   - Used as: output, vector, name

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

v.fill.holes fills empty spaces inside areas, specifically it
preserves areas with centroids while areas without centroids, which
typically represent holes, are removed. v.fill.holes goes over all
areas in a vector map and it preserves only outer boundaries of each
area while removing inner boundaries which are considered holes. The
holes become part of the area which contained them. No boundaries of
these holes are preserved.

Figure: Holes inside areas are removed. (a) Original areas with holes
and (b) the same areas but with holes filled.

In case areas have empty space in between them, i.e., there are holes in
the overall coverage, but not in the areas themselves, v.fill.holes can't assign this empty space to either of these areas because it does
not know which area this empty space should belong to. If the space
needs to be filled, this can be resolved by merging the areas around the
empty space into one by dissolving their common boundaries. This turns
the empty space into a hole inside one single area which turns the
situation into a case of one area with a hole.

Figure: Empty space in between two areas does not belong to either
area, so it is filled only after the boundaries between areas are
dissolved, i.e., areas merged into one. (a) Original areas with space in
between, (b) one area with a hole after dissolving the common boundary,
and (c) hole filled.

Strictly speaking, in the GRASS topological model, an area is a closed
boundary (or a series of connected closed boundaries) which may have a
centroid. If it has a centroid, it is rendered as a filled area in
displays and this is what is usually considered an area from the user
perspective. These are the areas where v.fill.holes preserves the
associated outer boundary (or boundaries). Other closed boundaries,
i.e., those without a centroid, are not carried over to the output. All
other features are removed including points and lines.

If a specific layer is selected, attributes for that layer are preserved
for the areas based on the category or categories associated with each
area. By default, layer number 1 is selected. In case there are
attribute tables associated with other layers or attributes associated
with categories of other features than areas with centroids, this
attribute data is not carried over to the output just like the
corresponding geometries.

---

## Resources

- [Official v.fill.holes manual](https://grass.osgeo.org/grass-devel/manuals/v.fill.holes.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/v.fill.holes.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
