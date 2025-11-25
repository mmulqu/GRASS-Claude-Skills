# v.profile

**Category**: vector

## Description

Vector map profiling tool

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.v_profile(input,type="point,line",where=None,layer="1",output="-",separator="pipe",dp=2,buffer=10,map_output=None,coordinates=None,profile_map=None,profile_where=None,profile_layer=1,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str, required`**
   - Name of input vector map
   - Or data source for direct OGR access
   - Used as: input, vector, name

2. **`type : str | list[str], optional`**
   - Input feature type
   - Allowed values: point, line
   - Default: point,line

3. **`where : str, optional`**
   - WHERE conditions of SQL statement without 'where' keyword
   - Example: income < 1000 and population >= 10000
   - Used as: input, sql_query, sql_query

4. **`layer : str, optional`**
   - Layer number or name
   - Use features only from specified layer
   - Used as: input, layer

5. **`output : str, optional`**
   - Path to output text file or - for stdout
   - Used as: output
   - Default: -

6. **`separator : str, optional`**
   - Field separator
   - Special characters: pipe, comma, space, tab, newline
   - Used as: input, separator, character

7. **`dp : int, optional`**
   - Number of significant digits
   - Allowed values: 0-32
   - Default: 2

8. **`buffer : float, required`**
   - Buffer (tolerance) for points in map units
   - How far points can be from sampling line
   - Default: 10

9. **`map_output : str, optional`**
   - Name for profile line and buffer output map
   - Profile line and buffer around it will be written
   - Used as: output, vector, name

10. **`coordinates : list[tuple[float, float]] | tuple[float, float] | list[float] | str, optional`**
   - Coordinates for profiling line nodes
   - Specify profiling line vertices and nodes
   - Used as: input, coords, east,north

11. **`profile_map : str, optional`**
   - Profiling line map
   - Vector map containing profiling line
   - Used as: input, vector, name

12. **`profile_where : str, optional`**
   - WHERE conditions for input profile line map
   - Use to select only one line from profiling line map
   - Used as: sql_query

13. **`profile_layer : int, optional`**
   - Profiling line map layer
   - Default: 1

14. **`flags : str, optional`**
   - Allowed values: c, z
   - c
   - Do not print column names
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/v.profile.html#__tabbed_2_3) for all details)*

15. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

16. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

17. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

18. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 18 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/v.profile.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

v.profile prints out distance and attributes of points/lines along a
profiling line. Distance is calculated from the first profiling line
coordinate pair or from the beginning of vector line. The buffer (tolerance) parameter sets how far point can be located
from a profiling line and still be included in the output data set. The output map option can be used to visually check which points are
profiled. The buffer (tolerance) setting does not affect lines. Lines
are sampled at their crossing point with profiling line.

By default Z values are printed if input vector is a 3D map. It can be
disabled with the -z flag. The profiling line can be provided as N,E coordinate pairs or from an
input vector map. As a profiling line must be a single line, the user
should use the profile_where parameter to select a single line from a
profile input map if it contains multiple vector features.

---

## See Also

Related tools:
- [`r.profile`](https://grass.osgeo.org/grass-devel/manuals/r.profile.html)

---

## Resources

- [Official v.profile manual](https://grass.osgeo.org/grass-devel/manuals/v.profile.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/v.profile.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
