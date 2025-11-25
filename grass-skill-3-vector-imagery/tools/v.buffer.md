# v.buffer

**Category**: vector

## Description

Creates a buffer around vector features of given type.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.v_buffer(input,layer="-1",cats=None,where=None,type="point,line,area",output,distance=None,minordistance=None,angle=0,column=None,scale=1.0,tolerance=None,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
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

3. **`cats : str, optional`**
   - Category values
   - Example: 1,3,7-9,13
   - Used as: input, cats, range

4. **`where : str, optional`**
   - WHERE conditions of SQL statement without 'where' keyword
   - Example: income < 1000 and population >= 10000
   - Used as: input, sql_query, sql_query

5. **`type : str | list[str], optional`**
   - Input feature type
   - Allowed values: point, line, boundary, centroid, area
   - Default: point,line,area

6. **`output : str, required`**
   - Name for output vector map
   - Used as: output, vector, name

7. **`distance : float, optional`**
   - Buffer distance along major axis in map units

8. **`minordistance : float, optional`**
   - Buffer distance along minor axis in map units

9. **`angle : float, optional`**
   - Angle of major axis in degrees
   - Default: 0

10. **`column : str, optional`**
   - Name of column to use for buffer distances
   - Used as: input, dbcolumn, name

11. **`scale : float, optional`**
   - Scaling factor for attribute column values
   - Default: 1.0

12. **`tolerance : float, optional`**
   - Maximum distance between theoretical arc and polygon segments as multiple of buffer (default 0.01)

13. **`flags : str, optional`**
   - Allowed values: s, c, t
   - s
   - Make outside corners straight
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/v.buffer.html#__tabbed_2_3) for all details)*

14. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

15. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

16. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

17. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 17 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/v.buffer.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

v.buffer creates a buffer around features of given type , which
have a category in the given layer . The tolerance controls the
number of vector segments being generated (the smaller the value, the
more vector segments are generated).

---

## See Also

Related tools:
- [`r.buffer`](https://grass.osgeo.org/grass-devel/manuals/r.buffer.html)
- [`v.parallel`](https://grass.osgeo.org/grass-devel/manuals/v.parallel.html)
- [`v.extract`](https://grass.osgeo.org/grass-devel/manuals/v.extract.html)
- [`v.type`](https://grass.osgeo.org/grass-devel/manuals/v.type.html)
- [`v.patch`](https://grass.osgeo.org/grass-devel/manuals/v.patch.html)
- [`v.db.connect`](https://grass.osgeo.org/grass-devel/manuals/v.db.connect.html)

---

## Authors

Radim Blazek Rewritten by Rosen Matev (with support through the Google Summer of Code
program 2008) Rewritten by Markus Metz (2011, 2012)

---

## Resources

- [Official v.buffer manual](https://grass.osgeo.org/grass-devel/manuals/v.buffer.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/v.buffer.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
