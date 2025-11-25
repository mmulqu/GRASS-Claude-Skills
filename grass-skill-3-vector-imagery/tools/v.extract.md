# v.extract

**Category**: vector

## Description

Selects vector features from an existing vector map and creates a new vector map containing only the selected features.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.v_extract(input,layer="1",type="point,line,boundary,centroid,area,face",cats=None,where=None,output,file=None,random=None,new=-1,dissolve_column=None,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
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
   - Types to be extracted
   - Input feature type
   - Allowed values: point, line, boundary, centroid, area, face

4. **`cats : str, optional`**
   - Category values
   - Example: 1,3,7-9,13
   - Used as: input, cats, range

5. **`where : str, optional`**
   - WHERE conditions of SQL statement without 'where' keyword
   - Example: income < 1000 and population >= 10000
   - Used as: input, sql_query, sql_query

6. **`output : str, required`**
   - Name for output vector map
   - Used as: output, vector, name

7. **`file : str | io.StringIO, optional`**
   - Input text file with category numbers/number ranges to be extracted
   - If '-' given reads from standard input
   - Used as: input, file, name

8. **`random : int, optional`**
   - Number of random categories matching vector objects to extract
   - Number must be smaller than unique cat count in layer

9. **`new : int, optional`**
   - Desired new category value (enter -1 to keep original categories)
   - If new >= 0, attributes is not copied
   - Default: -1

10. **`dissolve_column : str, optional`**
   - Name of attribute column for dissolving areas
   - Preserves category values
   - Used as: input, dbcolumn, name

11. **`flags : str, optional`**
   - Allowed values: d, t, r
   - d
   - Dissolve common boundaries (default is no)
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/v.extract.html#__tabbed_2_3) for all details)*

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


*Showing 10 of 15 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/v.extract.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

v.extract allows a user to select vector objects from an existing
vector map and creates a new map containing only the selected objects.
Database tables can be queried with SQL statements, if a connection is
established. Dissolving (optional) is based on the output categories. If
2 adjacent areas have the same output category, the boundary is removed.

If cats , file , random or where options are not
specified, all features of given type and layer are extracted.
Categories are not changed in that case.

---

## See Also

Related tools:
- [`v.category`](https://grass.osgeo.org/grass-devel/manuals/v.category.html)
- [`v.dissolve`](https://grass.osgeo.org/grass-devel/manuals/v.dissolve.html)
- [`v.reclass`](https://grass.osgeo.org/grass-devel/manuals/v.reclass.html)

---

## Authors

R.L. Glenn, USDA, SCS, NHQ-CGIS GRASS 6 port by Radim Blazek

---

## Resources

- [Official v.extract manual](https://grass.osgeo.org/grass-devel/manuals/v.extract.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/v.extract.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
