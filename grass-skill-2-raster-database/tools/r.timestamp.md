# r.timestamp

**Category**: raster

## Description

Modifies a timestamp for a raster map. Print/add/remove a timestamp for a raster map.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_timestamp(map,date=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`map : str | np.ndarray, required`**
   - Name of raster map
   - Used as: input, raster, name

2. **`date : str, optional`**
   - Datetime, datetime1/datetime2, or 'none' to remove
   - Format: '15 jan 1994' (absolute) or '2 years' (relative)
   - Used as: timestamp

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

r.timestamp has two modes of operation. If no date argument is
supplied, then the current timestamp for the raster map is printed. If a
date argument is specified, then the timestamp for the raster map is set
to the specified date(s). See examples below.

---

## See Also

Related tools:
- [`r.info`](https://grass.osgeo.org/grass-devel/manuals/r.info.html)
- [`r3.timestamp`](https://grass.osgeo.org/grass-devel/manuals/r3.timestamp.html)
- [`v.timestamp`](https://grass.osgeo.org/grass-devel/manuals/v.timestamp.html)

---

## Resources

- [Official r.timestamp manual](https://grass.osgeo.org/grass-devel/manuals/r.timestamp.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.timestamp.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
