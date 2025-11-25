# v.reclass

**Category**: vector

## Description

Changes vector category values for an existing vector map according to results of SQL queries or a value in attribute table column.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.v_reclass(input,layer="1",type="point,line,boundary,centroid",output,column=None,rules=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str, required`**
   - Name of input vector map
   - Or data source for direct OGR access
   - Used as: input, vector, name

2. **`layer : str, optional`**
   - Layer number or name
   - Vector features can have category values in different layers. This number determines which layer to use. When used with direct OGR access this is the layer name.
   - Used as: input, layer

3. **`type : str | list[str], optional`**
   - Input feature type
   - Allowed values: point, line, boundary, centroid
   - Default: point,line,boundary,centroid

4. **`output : str, required`**
   - Name for output vector map
   - Used as: output, vector, name

5. **`column : str, optional`**
   - The name of the column whose values are to be used as new categories
   - The source for the new key column must be type integer or string
   - Used as: input, dbcolumn, name

6. **`rules : str | io.StringIO, optional`**
   - Full path to the reclass rule file
   - Used as: input, file, name

7. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

8. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

9. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

10. **`superquiet : bool, optional`**
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

v.reclass allows user to create a new vector map based on the
reclassification of an existing vector map. It also allows the user to
change the key column away from the default of " cat " with the column option.

Rules file may contain on each row either pair:

(separated by space) or comment beginning with '#' (hash). Definition of
new category begins with keyword cat followed by the new category
value. Keyword where specifies SQL where condition.

---

## See Also

Related tools:
- [`v.dissolve`](https://grass.osgeo.org/grass-devel/manuals/v.dissolve.html)
- [`v.extract`](https://grass.osgeo.org/grass-devel/manuals/v.extract.html)

---

## Authors

R.L. Glenn, USDA, SCS, NHQ-CGIS from v.reclass to v.db.reclass and later to v.reclass in 5.7 rewritten
by Radim Blazek

---

## Resources

- [Official v.reclass manual](https://grass.osgeo.org/grass-devel/manuals/v.reclass.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/v.reclass.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
