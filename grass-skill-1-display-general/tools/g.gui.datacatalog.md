# g.gui.datacatalog

**Category**: general

## Description

Tool for browsing, modifying and managing GRASS maps.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.g_gui_datacatalog(verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

2. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

3. **`superquiet : bool, optional`**
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

The Data Catalog is a wxGUI component for browsing,
modifying and managing GRASS maps.

Data Catalog allows you to:

Note that projects are called locations at some places and in old
documentation.

Figure: Data Catalog integrated in wxGUI.

---

## See Also

Related tools:

---

## Authors

Anna Petrasova, NCSU GeoForAll Laboratory Tereza Fiedlerova, OSGeoREL, Czech Technical University in Prague, Czech
Republic

---

## Resources

- [Official g.gui.datacatalog manual](https://grass.osgeo.org/grass-devel/manuals/g.gui.datacatalog.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/g.gui.datacatalog.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
