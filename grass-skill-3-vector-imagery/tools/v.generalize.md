# v.generalize

**Category**: vector

## Description

Performs vector based generalization.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.v_generalize(input,layer="-1",type="line,boundary,area",output,error=None,method,threshold,look_ahead=7,reduction=50,slide=0.5,angle_thresh=3,degree_thresh=0,closeness_thresh=0,betweeness_thresh=0,alpha=1.0,beta=1.0,iterations=1,cats=None,where=None,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
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
   - Allowed values: line, boundary, area
   - Default: line,boundary,area

4. **`output : str, required`**
   - Name for output vector map
   - Used as: output, vector, name

5. **`error : str, optional`**
   - Error map with failed generalizations
   - Lines and boundaries causing errors (collapsed to a point or topology errors)
   - Used as: output, vector, name

6. **`method : str, required`**
   - Generalization algorithm
   - Allowed values: douglas, douglas_reduction, lang, reduction, reumann, boyle, sliding_averaging, distance_weighting, chaiken, hermite, snakes, network, displacement
   - douglas: Douglas-Peucker Algorithm
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/v.generalize.html#__tabbed_2_3) for all details)*

7. **`threshold : float, required`**
   - Maximal tolerance value
   - Allowed values: 0-1000000000

8. **`look_ahead : int, optional`**
   - Look-ahead parameter
   - Default: 7

9. **`reduction : float, optional`**
   - Percentage of the points in the output of 'douglas_reduction' algorithm
   - Allowed values: 0-100
   - Default: 50

10. **`slide : float, optional`**
   - Slide of computed point toward the original point
   - Allowed values: 0-1
   - Default: 0.5

11. **`angle_thresh : float, optional`**
   - Minimum angle between two consecutive segments in Hermite method
   - Allowed values: 0-180
   - Default: 3

12. **`degree_thresh : int, optional`**
   - Degree threshold in network generalization
   - Default: 0

13. **`closeness_thresh : float, optional`**
   - Closeness threshold in network generalization
   - Allowed values: 0-1
   - Default: 0

14. **`betweeness_thresh : float, optional`**
   - Betweeness threshold in network generalization
   - Default: 0

15. **`alpha : float, optional`**
   - Snakes alpha parameter
   - Default: 1.0

16. **`beta : float, optional`**
   - Snakes beta parameter
   - Default: 1.0

17. **`iterations : int, optional`**
   - Number of iterations
   - Default: 1

18. **`cats : str, optional`**
   - Category values
   - Example: 1,3,7-9,13
   - Used as: input, cats, range

19. **`where : str, optional`**
   - WHERE conditions of SQL statement without 'where' keyword
   - Example: income < 1000 and population >= 10000
   - Used as: input, sql_query, sql_query

20. **`flags : str, optional`**
   - Allowed values: l, t
   - l
   - Disable loop support
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/v.generalize.html#__tabbed_2_3) for all details)*

21. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

22. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

23. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

24. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 24 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/v.generalize.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

v.generalize is a module for the generalization of GRASS vector maps.
This module consists of algorithms for line simplification, line
smoothing, network generalization and displacement (new methods may be
added later).

The cats and where options are used only if a layer > 0 is
specified, otherwise, those options are ignored. Be aware that the
default is layer=-1 , meaning that all layers are processed, ignoring
the cats and where options.

If type=area is selected, boundaries of selected areas will be
generalized, and the options cats , where , and layer will be
used to select areas.

---

## See Also

Related tools:
- [`v.clean`](https://grass.osgeo.org/grass-devel/manuals/v.clean.html)
- [`v.dissolve`](https://grass.osgeo.org/grass-devel/manuals/v.dissolve.html)

---

## Authors

Daniel Bundala, Google Summer of Code 2007, Student Wolf Bergenheim, Mentor Partial rewrite: Markus Metz

---

## Resources

- [Official v.generalize manual](https://grass.osgeo.org/grass-devel/manuals/v.generalize.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/v.generalize.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
