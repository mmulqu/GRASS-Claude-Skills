# v.class

**Category**: vector

## Description

Classifies attribute data, e.g. for thematic mapping

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.v_class(map,layer="1",column,where=None,algorithm,nbclasses,separator="comma",format="plain",flags=None,verbose=None,quiet=None,superquiet=None)
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

3. **`column : str, required`**
   - Column name or expression
   - Used as: input, dbcolumn, name

4. **`where : str, optional`**
   - WHERE conditions of SQL statement without 'where' keyword
   - Example: income < 1000 and population >= 10000
   - Used as: input, sql_query, sql_query

5. **`algorithm : str, required`**
   - Algorithm to use for classification
   - Allowed values: int, std, qua, equ, dis
   - int: simple intervals
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/v.class.html#__tabbed_2_3) for all details)*

6. **`nbclasses : int, required`**
   - Number of classes to define
   - Allowed values: 2-

7. **`separator : str, optional`**
   - Field separator for printing output
   - Special characters: pipe, comma, space, tab, newline
   - Used as: input, separator, character

8. **`format : str, required`**
   - Output format
   - Used as: name
   - Allowed values: plain, csv, json, list
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/v.class.html#__tabbed_2_3) for all details)*

9. **`flags : str, optional`**
   - Allowed values: b
   - b
   - Print only class breaks (without min and max)

10. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

11. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

12. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 12 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/v.class.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

v.class classifies vector attribute data into classes, for example for
thematic mapping. Classification can be on a column or on an expression
including several columns, all in the table linked to the vector map.
The user indicates the number of classes desired and the algorithm to
use for classification. Several algorithms are implemented for
classification: equal interval, standard deviation, quantiles, equal
probabilities, and a discontinuities algorithm developed by Jean-Pierre
Grimmeau at the Free University of Brussels (ULB). It can be used to
pipe class breaks into thematic mapping modules such as d.vect.thematic (see example below);

---

## See Also

Related tools:
- [`v.univar`](https://grass.osgeo.org/grass-devel/manuals/v.univar.html)
- [`d.vect.thematic`](https://grass.osgeo.org/grass-devel/manuals/d.vect.thematic.html)

---

## Resources

- [Official v.class manual](https://grass.osgeo.org/grass-devel/manuals/v.class.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/v.class.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
