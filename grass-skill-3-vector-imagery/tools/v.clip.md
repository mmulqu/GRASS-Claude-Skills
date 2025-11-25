# v.clip

**Category**: vector

## Description

Extracts features of input map which overlay features of clip map.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.v_clip(input,clip,output,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str, required`**
   - Name of vector map to be clipped
   - Or data source for direct OGR access
   - Used as: input, vector, name

2. **`clip : str, required`**
   - Name of clip vector map
   - Or data source for direct OGR access
   - Used as: input, vector, name

3. **`output : str, required`**
   - Name for output vector map
   - Used as: output, vector, name

4. **`flags : str, optional`**
   - Allowed values: d, r
   - d
   - Do not dissolve clip map
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/v.clip.html#__tabbed_2_3) for all details)*

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

v.clip module enables extracting those features of input vector map,
which overlay features of clip map, as well as their storing in a new
vector map.

In default, boundaries of clip map are dissolved before clipping.
Alternatively, flag -d can be ticked to retain the boundaries of
clip map. Flag -r facilitates clipping by current computational
region.

It is possible to clip vector maps consisting of points, lines, areas or
combinations of these. However, the current version does not fully
support clipping of mixed geometry containing points. In such a case,
the output map will only store clipped lines and/or areas.

---

## See Also

Related tools:
- [`v.overlay`](https://grass.osgeo.org/grass-devel/manuals/v.overlay.html)
- [`v.select`](https://grass.osgeo.org/grass-devel/manuals/v.select.html)
- [`v.dissolve`](https://grass.osgeo.org/grass-devel/manuals/v.dissolve.html)
- [`v.in.region`](https://grass.osgeo.org/grass-devel/manuals/v.in.region.html)

---

## Resources

- [Official v.clip manual](https://grass.osgeo.org/grass-devel/manuals/v.clip.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/v.clip.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
