# db.test

**Category**: database

## Description

Test database driver, database must exist and set by db.connect.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.db_test(test,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`test : str, required`**
   - Test name
   - Allowed values: test1

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

db.test tests database driver and database server running set of SQL
queries. Database must exist and connection must be set by db.connect .

---

## See Also

Related tools:
- [`db.connect`](https://grass.osgeo.org/grass-devel/manuals/db.connect.html)
- [`db.describe`](https://grass.osgeo.org/grass-devel/manuals/db.describe.html)
- [`db.drivers`](https://grass.osgeo.org/grass-devel/manuals/db.drivers.html)

---

## Resources

- [Official db.test manual](https://grass.osgeo.org/grass-devel/manuals/db.test.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/db.test.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
