# db.login

**Category**: database

## Description

Sets user/password for DB driver/database.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.db_login(driver="sqlite",database="$GISDBASE/$LOCATION_NAME/$MAPSET/sqlite/sqlite.db",user=None,password=None,host=None,port=None,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`driver : str, required`**
   - Name of database driver
   - Used as: input, dbdriver, name
   - Allowed values: dbf, odbc, ogr, pg, sqlite

2. **`database : str, required`**
   - Name of database
   - Used as: input, dbname, name
   - Default: $GISDBASE/$LOCATION_NAME/$MAPSET/sqlite/sqlite.db

3. **`user : str, optional`**
   - Username

4. **`password : str, optional`**
   - Password

5. **`host : str, optional`**
   - Hostname
   - Relevant only for pg and mysql driver

6. **`port : str, optional`**
   - Port
   - Relevant only for pg and mysql driver

7. **`flags : str, optional`**
   - Allowed values: p
   - p
   - Print connection settings and exit

8. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

9. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

10. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

11. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 11 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/db.login.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

db.login sets login parameters such an user name and optionally also a
password, a hostname or a port for the connection to the selected database through the DB driver .

---

## Note

Options host and port are related to only SQL database backends
like PostgreSQL , MySQL or ODBC .

Note that the passwords are stored in a hidden, unencrypted file in
the user account, specifically

Only the file owner can access this file.

---

## See Also

Related tools:
- [`db.connect`](https://grass.osgeo.org/grass-devel/manuals/db.connect.html)
- [`db.test`](https://grass.osgeo.org/grass-devel/manuals/db.test.html)
- [`db.tables`](https://grass.osgeo.org/grass-devel/manuals/db.tables.html)

---

## Resources

- [Official db.login manual](https://grass.osgeo.org/grass-devel/manuals/db.login.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/db.login.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
