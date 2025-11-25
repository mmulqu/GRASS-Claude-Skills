# db.drivers

**Category**: database

## Description

Lists all database drivers.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.db_drivers(flags=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`flags : str, optional`**
   - Allowed values: f, p
   - f
   - Full output
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/db.drivers.html#__tabbed_2_3) for all details)*

2. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

3. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

4. **`superquiet : bool, optional`**
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

db.drivers lists all database drivers (DBMI backends).

---

## See Also

Related tools:
- [`db.connect`](https://grass.osgeo.org/grass-devel/manuals/db.connect.html)
- [`db.describe`](https://grass.osgeo.org/grass-devel/manuals/db.describe.html)
- [`db.droptable`](https://grass.osgeo.org/grass-devel/manuals/db.droptable.html)
- [`db.execute`](https://grass.osgeo.org/grass-devel/manuals/db.execute.html)
- [`db.login`](https://grass.osgeo.org/grass-devel/manuals/db.login.html)
- [`db.tables`](https://grass.osgeo.org/grass-devel/manuals/db.tables.html)

---

## Resources

- [Official db.drivers manual](https://grass.osgeo.org/grass-devel/manuals/db.drivers.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/db.drivers.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
