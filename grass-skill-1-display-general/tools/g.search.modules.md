# g.search.modules

**Category**: general

## Description

Search in GRASS modules using keywords

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.g_search_modules(keyword=None,flags=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`keyword : str | list[str], optional`**
   - Keyword to be searched
   - List all modules if not given

2. **`flags : str, optional`**
   - Allowed values: a, n, m, k, c, g, j
   - a
   - Display only modules where all keywords are available (AND), default: OR
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/g.search.modules.html#__tabbed_2_3) for all details)*

3. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

4. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

5. **`superquiet : bool, optional`**
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

g.search.module searches for given keyword in GRASS modules name,
description, keywords and optionally manpages, too. Also installed
addons are considered in the search.

---

## See Also

Related tools:
- [`g.manual`](https://grass.osgeo.org/grass-devel/manuals/g.manual.html)

---

## Authors

Jachym Cepicky, OpenGeoLabs s.r.o., Czech Republic: original author Anika Bettge, mundialis, Germany: addon search added

---

## Resources

- [Official g.search.modules manual](https://grass.osgeo.org/grass-devel/manuals/g.search.modules.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/g.search.modules.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
