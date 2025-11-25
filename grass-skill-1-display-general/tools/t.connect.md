# t.connect

**Category**: temporal

## Description

Prints/sets general temporal GIS database connection for current mapset.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.t_connect(driver="sqlite",database="$GISDBASE/$LOCATION_NAME/$MAPSET/tgis/sqlite.db",flags=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`driver : str, optional`**
   - Name of database driver
   - Used as: input, dbdriver, name
   - Allowed values: sqlite, pg

2. **`database : str, optional`**
   - Name of database
   - Used as: input, dbname, name
   - Default: $GISDBASE/$LOCATION_NAME/$MAPSET/tgis/sqlite.db

3. **`flags : str, optional`**
   - Allowed values: p, c, d, g
   - p
   - Print current connection parameters and exit
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/t.connect.html#__tabbed_2_3) for all details)*

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

t.connect allows the user to set the temporal database connection. The
default setting is that the temporal database of type sqlite3 is
located in the current mapset directory.

The -p flag will display the current temporal database connection
parameters.

The -pg flag will display the current temporal database connection
parameters using shell style.

The -c flag will silently check if the temporal database connection
parameters have been set, and if not will set them to use GRASS's
default values.

---

## Resources

- [Official t.connect manual](https://grass.osgeo.org/grass-devel/manuals/t.connect.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/t.connect.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
