# v.db.renamecolumn

**Category**: vector

## Description

Renames a column in the attribute table connected to a given vector map.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.v_db_renamecolumn(map,layer="1",column,verbose=None,quiet=None,superquiet=None)
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

3. **`column : tuple[str, str] | list[str] | str, required`**
   - Old and new name of the column (old,new)
   - Used as: oldcol,newcol

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

v.db.renamecolumn renames a column in the attribute table connected to
a given vector map. It automatically checks the connection for the
specified layer.

---

## See Also

Related tools:
- [`db.execute`](https://grass.osgeo.org/grass-devel/manuals/db.execute.html)
- [`v.db.addcolumn`](https://grass.osgeo.org/grass-devel/manuals/v.db.addcolumn.html)
- [`v.db.addtable`](https://grass.osgeo.org/grass-devel/manuals/v.db.addtable.html)
- [`v.db.connect`](https://grass.osgeo.org/grass-devel/manuals/v.db.connect.html)
- [`v.db.dropcolumn`](https://grass.osgeo.org/grass-devel/manuals/v.db.dropcolumn.html)
- [`v.db.droptable`](https://grass.osgeo.org/grass-devel/manuals/v.db.droptable.html)
- [`v.db.select`](https://grass.osgeo.org/grass-devel/manuals/v.db.select.html)
- [`v.db.update`](https://grass.osgeo.org/grass-devel/manuals/v.db.update.html)

---

## Resources

- [Official v.db.renamecolumn manual](https://grass.osgeo.org/grass-devel/manuals/v.db.renamecolumn.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/v.db.renamecolumn.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
