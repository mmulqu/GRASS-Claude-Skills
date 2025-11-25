# r.semantic.label

**Category**: raster

## Description

Manages semantic label information assigned to a single raster map or to a list of raster maps.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_semantic_label(map,semantic_label=None,operation="add",verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`map : str | list[str], required`**
   - Name of raster map(s)
   - Used as: input, raster, name

2. **`semantic_label : str | list[str], optional`**
   - Name of semantic label identifier (example: S2_1)
   - Used as: name

3. **`operation : str, required`**
   - Operation to be performed
   - Allowed values: add, remove, print
   - Default: add

4. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

5. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

6. **`superquiet : bool, optional`**
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

r.semantic.label allows assigning a semantic label information to a
single raster map or to a list of specified raster maps. Semantic label
can be defined by semantic_label option. Already assigned semantic
label can be removed from a specified raster map by operation=remove . The module also allows printing detailed semantic
label information already assigned to a raster map by operation=print .

Either a single raster map or a list of raster maps can be given by map option.

---

## See Also

Related tools:
- [`i.band.library`](https://grass.osgeo.org/grass-devel/manuals/i.band.library.html)
- [`r.info`](https://grass.osgeo.org/grass-devel/manuals/r.info.html)
- [`r.support`](https://grass.osgeo.org/grass-devel/manuals/r.support.html)

---

## Authors

Martin Landa Development sponsored by mundialis GmbH & Co.
KG (for the openEO EU H2020 grant 776242)

---

## Resources

- [Official r.semantic.label manual](https://grass.osgeo.org/grass-devel/manuals/r.semantic.label.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.semantic.label.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
