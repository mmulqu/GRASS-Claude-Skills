# v.timestamp

**Category**: vector

## Description

Modifies a timestamp for a vector map. Print/add/remove a timestamp for a vector map.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.v_timestamp(map,layer="1",date=None,verbose=None,quiet=None,superquiet=None)
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

3. **`date : str, optional`**
   - Datetime, datetime1/datetime2, or 'none' to remove
   - Format: '15 jan 1994' (absolute) or '2 years' (relative)
   - Used as: timestamp

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

This command has 2 modes of operation. If no date argument is
supplied, then the current timestamp for the vector map is printed. If a
date argument is specified, then the timestamp for the vector map is set
to the specified date(s). See examples below.

See TIMESTAMP FORMAT description for
details.

---

## See Also

Related tools:
- [`v.info`](https://grass.osgeo.org/grass-devel/manuals/v.info.html)
- [`r.timestamp`](https://grass.osgeo.org/grass-devel/manuals/r.timestamp.html)
- [`r3.timestamp`](https://grass.osgeo.org/grass-devel/manuals/r3.timestamp.html)

---

## Resources

- [Official v.timestamp manual](https://grass.osgeo.org/grass-devel/manuals/v.timestamp.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/v.timestamp.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
