# v.db.addtable

**Category**: vector

## Description

Creates and connects a new attribute table to a given layer of an existing vector map.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.v_db_addtable(map,table=None,layer=1,key="cat",columns=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`map : str, required`**
   - Name of vector map
   - Or data source for direct OGR access
   - Used as: input, vector, name

2. **`table : str, optional`**
   - Name of new attribute table (default: vector map name)

3. **`layer : int, optional`**
   - Layer number where to add new attribute table
   - Default: 1

4. **`key : str, optional`**
   - Name of key column
   - Must refer to an integer column
   - Used as: name

5. **`columns : str | list[str], optional`**
   - Name and type of the new column(s) ('name type [,name type, ...]')
   - Types depend on database backend, but all support VARCHAR(), INT, DOUBLE PRECISION and DATE. Example: 'label varchar(250), value integer'
   - Used as: name type

6. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

7. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

8. **`superquiet : bool, optional`**
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

v.db.addtable creates and adds a new attribute table to a given vector
map. It links the table to the specified layer of the vector map. If the
vector map is not yet linked to any table, new a database link is
established based on the MAPSET database settings (see db.connect ).

---

## See Also

Related tools:
- [`db.connect`](https://grass.osgeo.org/grass-devel/manuals/db.connect.html)
- [`db.droptable`](https://grass.osgeo.org/grass-devel/manuals/db.droptable.html)
- [`db.execute`](https://grass.osgeo.org/grass-devel/manuals/db.execute.html)
- [`v.db.connect`](https://grass.osgeo.org/grass-devel/manuals/v.db.connect.html)
- [`v.db.dropcolumn`](https://grass.osgeo.org/grass-devel/manuals/v.db.dropcolumn.html)
- [`v.db.droptable`](https://grass.osgeo.org/grass-devel/manuals/v.db.droptable.html)
- [`v.db.select`](https://grass.osgeo.org/grass-devel/manuals/v.db.select.html)
- [`v.db.update`](https://grass.osgeo.org/grass-devel/manuals/v.db.update.html)

---

## Resources

- [Official v.db.addtable manual](https://grass.osgeo.org/grass-devel/manuals/v.db.addtable.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/v.db.addtable.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
