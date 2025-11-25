# v.split

**Category**: vector

## Description

Splits vector lines to shorter segments.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.v_split(input,layer="-1",output,length=None,units="map",vertices=None,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
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

4. **`length : float, optional`**
   - Maximum segment length

5. **`units : str, optional`**
   - Length units
   - Allowed values: map, meters, kilometers, feet, surveyfeet, miles, nautmiles
   - Default: map

6. **`vertices : int, optional`**
   - Maximum number of vertices in segment

7. **`flags : str, optional`**
   - Allowed values: n, f
   - n
   - Add new vertices, but do not split
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/v.split.html#__tabbed_2_3) for all details)*

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


*Showing 10 of 11 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/v.split.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

v.split splits vector lines into shorter segments using a maximal
distance between nodes. The resulting length of all segments is expected
to be equal and not higher than the given length parameter.

---

## See Also

Related tools:
- [`v.edit`](https://grass.osgeo.org/grass-devel/manuals/v.edit.html)
- [`v.build.polylines`](https://grass.osgeo.org/grass-devel/manuals/v.build.polylines.html)
- [`v.to.points`](https://grass.osgeo.org/grass-devel/manuals/v.to.points.html)
- [`v.segment`](https://grass.osgeo.org/grass-devel/manuals/v.segment.html)

---

## Resources

- [Official v.split manual](https://grass.osgeo.org/grass-devel/manuals/v.split.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/v.split.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
