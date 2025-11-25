# r.mask.status

**Category**: raster

## Description

Reports presence or absence of a raster mask Provides information about the presence of a 2D raster mask as text output or return code

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_mask_status(format="plain",flags=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`format : str, optional`**
   - Format for reporting
   - Allowed values: plain, json, shell, yaml
   - plain: Plain text output
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/r.mask.status.html#__tabbed_2_3) for all details)*

2. **`flags : str, optional`**
   - Allowed values: t
   - t
   - Return code 0 when mask present, 1 otherwise

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

The r.mask.status reports information about the 2D raster mask and its
status. The tool reports whether the mask is present or not. For both
active and inactive mask, the tool reports a full name of the raster
(name including the mapset) which represents or would represent the
mask. It can also report full name of the underlying raster if the mask
is reclassified from another raster. The tool can be used to check if
the mask is currently set ( present boolean in JSON), what is raster
name used to represent the mask ( name string in JSON), and whether the
raster is reclassifed from another ( is_reclass_of string or null in
JSON). YAML and shell script style outputs are following the JSON output
if possible. The plain text format outputs multi-line human-readable
information in natural language.

With the -t flag, no output is printed, instead a return code is
used to indicate presence or absence. The convention is the same same
the POSIX test utility, so r.mask.status returns 0 when the mask is
present and 1 otherwise.

---

## See Also

Related tools:
- [`r.mask`](https://grass.osgeo.org/grass-devel/manuals/r.mask.html)
- [`g.region`](https://grass.osgeo.org/grass-devel/manuals/g.region.html)

---

## Authors

Vaclav Petras, NC State University, Center for Geospatial Analytics

---

## Resources

- [Official r.mask.status manual](https://grass.osgeo.org/grass-devel/manuals/r.mask.status.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.mask.status.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
