# v.normal

**Category**: vector

## Description

Tests for normality for vector points.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.v_normal(map,layer="1",tests,column,flags=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`map : str, required`**
   - Name of vector map
   - Or data source for direct OGR access
   - Used as: input, vector, name

2. **`layer : str, optional`**
   - Layer number or name
   - Vector features can have category values in different layers. This number determines which layer to use. When used with direct OGR access this is the layer name.
   - Used as: input, layer

3. **`tests : str | list[str], required`**
   - Lists of tests (1-15)
   - E.g. 1,3-8,13
   - Used as: range

4. **`column : str, required`**
   - Name of attribute column
   - Used as: input, dbcolumn, name

5. **`flags : str, optional`**
   - Allowed values: r, l
   - r
   - Use only points in current region
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/v.normal.html#__tabbed_2_3) for all details)*

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

v.normal computes tests of normality on vector points.

---

## See Also

Related tools:
- [`v.univar`](https://grass.osgeo.org/grass-devel/manuals/v.univar.html)

---

## Authors

James Darrell McCauley \<darrell@mccauley-usa.com> , when he was at: Agricultural
Engineering Purdue
University

---

## Resources

- [Official v.normal manual](https://grass.osgeo.org/grass-devel/manuals/v.normal.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/v.normal.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
