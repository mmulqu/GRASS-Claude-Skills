# v.in.region

**Category**: vector

## Description

Creates a vector polygon from the current region extent.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.v_in_region(output,type="area",cat=1,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`output : str, required`**
   - Name for output vector map
   - Used as: output, vector, name

2. **`type : str, optional`**
   - Select type: line or area
   - Allowed values: line, area
   - Default: area

3. **`cat : int, optional`**
   - Category value
   - Used as: input, cats
   - Default: 1

4. **`flags : str, optional`**
   - Allowed values: d
   - d
   - Densify lines using region resolution

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

v.in.region creates a new vector map from current region extent.

If the output of v.in.region is to be used for raster reprojection,
the -d flag should be used after setting the region to the raster
map to be reprojected with r.proj .

---

## See Also

Related tools:
- [`g.region`](https://grass.osgeo.org/grass-devel/manuals/g.region.html)
- [`r.proj`](https://grass.osgeo.org/grass-devel/manuals/r.proj.html)
- [`v.info`](https://grass.osgeo.org/grass-devel/manuals/v.info.html)

---

## Resources

- [Official v.in.region manual](https://grass.osgeo.org/grass-devel/manuals/v.in.region.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/v.in.region.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
