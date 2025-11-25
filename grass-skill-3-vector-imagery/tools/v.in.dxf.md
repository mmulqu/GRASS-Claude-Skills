# v.in.dxf

**Category**: vector

## Description

Converts file in DXF format to GRASS vector map.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.v_in_dxf(input,output,layers=None,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str | io.StringIO, required`**
   - Path to input DXF file
   - Used as: input, file, name

2. **`output : str, required`**
   - Name for output vector map
   - Used as: output, vector, name

3. **`layers : str | list[str], optional`**
   - List of DXF layers to import (default: all)

4. **`flags : str, optional`**
   - Allowed values: e, t, b, f, l, i, 1
   - e
   - Ignore the map extent of DXF file
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/v.in.dxf.html#__tabbed_2_3) for all details)*

5. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

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

v.in.dxf converts DXF format CAD files to GRASS vector format. The
following graphical objects (DXF entities) are supported:

Table and column names are changed to lowercase characters for easier
SQL usage (lowercase table/column names avoid the need to quote them if
the attribute table is stored in a SQL DBMS such as PostgreSQL).

The "layer" column will contain the name(s) of the DXF input layer(s).
The DXF entity type string will be stored in the "entity" column as
uppercase.

The "handle" column can be used to store small bits of data associated
with any entity in the DXF file (i.e., entity handle or unique object
identifiers in the layer). The entity handle is a "text string of up to
16 hexadecimal digits", which is a 64-bit integer (currently not
supported by GRASS database drivers). For text type entities, the text
value will be stored in the "label" column of the GRASS vector output
map. Neither the "handle" nor "label" column is mandatory.

---

## See Also

Related tools:
- [`v.out.dxf`](https://grass.osgeo.org/grass-devel/manuals/v.out.dxf.html)
- [`v.in.ogr`](https://grass.osgeo.org/grass-devel/manuals/v.in.ogr.html)
- [`v.out.ogr`](https://grass.osgeo.org/grass-devel/manuals/v.out.ogr.html)

---

## Authors

Original written by Chuck Ehlschlaeger, 6/1989 Revised by Dave Gerdes, 12/1989 US Army Construction Engineering Research Lab
Updated for GRASS 6 and 3D support. Huidae Cho, 3/2006 With minor additions by Benjamin Ducke (Oxford Archaeology), 4/2009

---

## Resources

- [Official v.in.dxf manual](https://grass.osgeo.org/grass-devel/manuals/v.in.dxf.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/v.in.dxf.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
