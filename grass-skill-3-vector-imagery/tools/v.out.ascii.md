# v.out.ascii

**Category**: vector

## Description

Exports a vector map to a GRASS ASCII vector representation. By default only features with category are exported. To export all features use 'layer=-1'.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.v_out_ascii(input,layer="1",type="point,line,boundary,centroid,area,face,kernel",output=None,columns=None,cats=None,where=None,format="point",separator="pipe",precision=8,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str, required`**
   - Name of input vector map
   - Or data source for direct OGR access
   - Used as: input, vector, name

2. **`layer : str, optional`**
   - Layer number or name ('-1' for all layers)
   - A single vector map can be connected to multiple database tables. This number determines which table to use. When used with direct OGR access this is the layer name.
   - Used as: input, layer

3. **`type : str | list[str], optional`**
   - Input feature type
   - Allowed values: point, line, boundary, centroid, area, face, kernel
   - Default: point,line,boundary,centroid,area,face,kernel

4. **`output : str, optional`**
   - Name for output ASCII file or ASCII vector name if '-o' is defined
   - If not given or '-' then standard output
   - Used as: output, file, name

5. **`columns : str | list[str], optional`**
   - Name of attribute column(s) to be exported (point mode)
   - "*" for all columns
   - Used as: input, dbcolumn, name

6. **`cats : str, optional`**
   - Category values
   - Example: 1,3,7-9,13
   - Used as: input, cats, range

7. **`where : str, optional`**
   - WHERE conditions of SQL statement without 'where' keyword
   - Example: income < 1000 and population >= 10000
   - Used as: input, sql_query, sql_query

8. **`format : str, required`**
   - Output format
   - Allowed values: point, standard, wkt
   - point: Simple point format (point per row)
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/v.out.ascii.html#__tabbed_2_3) for all details)*

9. **`separator : str, optional`**
   - Field separator
   - Field separator (points mode)
   - Used as: input, separator, character

10. **`precision : int, optional`**
   - Number of significant digits (floating point only)
   - Allowed values: 0-32
   - Default: 8

11. **`flags : str, optional`**
   - Allowed values: o, c, r
   - o
   - Create old (version 4) ASCII file
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/v.out.ascii.html#__tabbed_2_3) for all details)*

12. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

13. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

14. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

15. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 15 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/v.out.ascii.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

v.out.ascii converts a GRASS vector map in binary format to a GRASS
vector map in ASCII format . Using flag -o v.out.ascii output will be in old (version 4) ASCII format.

If the output parameter is not given then the data is sent to
standard output.

---

## See Also

Related tools:
- [`v.category`](https://grass.osgeo.org/grass-devel/manuals/v.category.html)
- [`v.in.ascii`](https://grass.osgeo.org/grass-devel/manuals/v.in.ascii.html)
- [`v.to.points`](https://grass.osgeo.org/grass-devel/manuals/v.to.points.html)

---

## Authors

Michael Higgins, U.S. Army Construction Engineering Research
Laboratory James Westervelt, U.S. Army Construction Engineering Research
Laboratory Radim Blazek, ITC-Irst, Trento, Italy Attribute selection added by Martin Landa, Czech Technical University in
Prague, Czech Republic (2008/12)

---

## Resources

- [Official v.out.ascii manual](https://grass.osgeo.org/grass-devel/manuals/v.out.ascii.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/v.out.ascii.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
