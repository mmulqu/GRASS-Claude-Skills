# t.vect.univar

**Category**: temporal

## Description

Calculates univariate statistics of attributes for each registered vector map of a space time vector dataset

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.t_vect_univar(input,output=None,layer="1",column,twhere=None,where=None,type="point",separator="pipe",flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str, required`**
   - Name of the input space time vector dataset
   - Used as: input, stvds, name

2. **`output : str, optional`**
   - Name for output file
   - Used as: output, file, name

3. **`layer : str, optional`**
   - Layer number or name
   - Vector features can have category values in different layers. This number determines which layer to use. When used with direct OGR access this is the layer name.
   - Used as: input, layer

4. **`column : str, required`**
   - Name of attribute column
   - Used as: input, dbcolumn, name

5. **`twhere : str, optional`**
   - WHERE conditions of SQL statement without 'where' keyword used in the temporal GIS framework
   - Example: start_time > '2001-01-01 12:30:00'
   - Used as: sql_query

6. **`where : str, optional`**
   - WHERE conditions of SQL statement without 'where' keyword
   - Example: income < 1000 and population >= 10000
   - Used as: input, sql_query, sql_query

7. **`type : str, optional`**
   - Input feature type
   - Allowed values: point, line, boundary, centroid, area
   - Default: point

8. **`separator : str, optional`**
   - Field separator character between the output columns
   - Special characters: pipe, comma, space, tab, newline
   - Used as: input, separator, character

9. **`flags : str, optional`**
   - Allowed values: e, u
   - e
   - Calculate extended statistics
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/t.vect.univar.html#__tabbed_2_3) for all details)*

10. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

11. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

12. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

13. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 13 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/t.vect.univar.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

The module t.vect.univar computes univariate statistics of a space
time vector dataset based on a single attribute row.

---

## See Also

Related tools:
- [`t.create`](https://grass.osgeo.org/grass-devel/manuals/t.create.html)
- [`t.info`](https://grass.osgeo.org/grass-devel/manuals/t.info.html)

---

## Resources

- [Official t.vect.univar manual](https://grass.osgeo.org/grass-devel/manuals/t.vect.univar.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/t.vect.univar.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
