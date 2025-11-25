# v.info

**Category**: vector

## Description

Outputs basic information about a vector map.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.v_info(map,layer="1",format=None,flags=None,verbose=None,quiet=None,superquiet=None)
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

3. **`format : str, optional`**
   - Output format
   - Used as: name
   - Allowed values: plain, shell, json
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/v.info.html#__tabbed_2_3) for all details)*

4. **`flags : str, optional`**
   - Allowed values: c, h, e, g, t
   - c
   - Print attribute table columns instead of info
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/v.info.html#__tabbed_2_3) for all details)*

5. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

6. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

7. **`superquiet : bool, optional`**
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

The v.info tool reports basic information about a
vector map, including its topology status.

When the attribute database connection is defined, the
information about it is included in the JSON and shell outputs.
If the connection is not defined for the given layer,
no fields related to attribute database are included in the output
except num_dblinks . To work with multiple layers within one vector map or
attribute tables connected to other layer than the first layer,
use v.info together with the v.db.connect tool.

If the vector map is connected to one or more attribute tables, the -c flag can be used to obtain the names and types of the attribute columns.
The columns are always printed for the attribute table linked to the layer
specified as a parameter. If the given layer is not connected to attribute table
database, the tools produces and error.
The current attribute database connections can be displayed or configured using v.db.connect .

If the topology information is unavailable (i.e., the vector map cannot be
opened at level 2), the spatial extent and number of features must be
calculated on the fly, which may take some time with large amounts of data.

Flags -g , -e , -t can be used to retrieve only a subset of
information. Use one or more of these flags together with the format set to
"json" or "shell". For example, you can retrieve non-spatial metadata with
the -g flag without calculating the spatial extent and number of features
when they are unavailable (see above).
Providing all three of these flags is the same as not providing any.

---

## See Also

Related tools:
- [`v.db.connect`](https://grass.osgeo.org/grass-devel/manuals/v.db.connect.html)
- [`v.category`](https://grass.osgeo.org/grass-devel/manuals/v.category.html)
- [`r.info`](https://grass.osgeo.org/grass-devel/manuals/r.info.html)
- [`r3.info`](https://grass.osgeo.org/grass-devel/manuals/r3.info.html)
- [`t.info`](https://grass.osgeo.org/grass-devel/manuals/t.info.html)

---

## Authors

Original author CERL Updated to GRASS 6 by Radim Blazek, ITC-Irst, Trento, Italy Level 1 support by Markus Metz Updated to GRASS 7 by Martin Landa, CTU in Prague, Czech Republic

---

## Resources

- [Official v.info manual](https://grass.osgeo.org/grass-devel/manuals/v.info.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/v.info.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
