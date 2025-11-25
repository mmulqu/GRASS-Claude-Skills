# v.db.droptable

**Category**: vector

## Description

Removes existing attribute table of a vector map.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.v_db_droptable(map,table=None,layer="1",flags=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`map : str, required`**
   - Name of vector map
   - Or data source for direct OGR access
   - Used as: input, vector, name

2. **`table : str, optional`**
   - Table name (default: vector map name)
   - Used as: input, dbtable, name

3. **`layer : str, optional`**
   - Layer number or name
   - Vector features can have category values in different layers. This number determines which layer to use. When used with direct OGR access this is the layer name.
   - Used as: input, layer

4. **`flags : str, optional`**
   - Allowed values: f
   - f
   - Force removal (required for actual deletion of table)

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

v.db.droptable removes an existing attribute table from a given vector
map linked at given layer. If the -f force flag is not given then
nothing is removed.

---

## See Also

Related tools:
- [`db.connect`](https://grass.osgeo.org/grass-devel/manuals/db.connect.html)
- [`db.execute`](https://grass.osgeo.org/grass-devel/manuals/db.execute.html)
- [`v.db.addtable`](https://grass.osgeo.org/grass-devel/manuals/v.db.addtable.html)
- [`v.db.connect`](https://grass.osgeo.org/grass-devel/manuals/v.db.connect.html)
- [`v.db.dropcolumn`](https://grass.osgeo.org/grass-devel/manuals/v.db.dropcolumn.html)
- [`v.db.select`](https://grass.osgeo.org/grass-devel/manuals/v.db.select.html)
- [`v.db.update`](https://grass.osgeo.org/grass-devel/manuals/v.db.update.html)

---

## Resources

- [Official v.db.droptable manual](https://grass.osgeo.org/grass-devel/manuals/v.db.droptable.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/v.db.droptable.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
