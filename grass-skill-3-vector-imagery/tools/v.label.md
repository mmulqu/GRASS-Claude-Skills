# v.label

**Category**: vector

## Description

Creates paint labels for a vector map from attached attributes.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.v_label(labels=None,map,column,type="point,line,boundary,centroid",layer="1",where=None,xoffset=0,yoffset=0,reference="center",font="standard",size=100,space=None,fontsize=None,color="black",rotation=0,width=1,highlight_color="none",highlight_width=0,bgcolor="none",border="none",opaque="yes",flags=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`labels : str, optional`**
   - Name for new paint-label file
   - If not given the name of the input map is used
   - Used as: name

2. **`map : str, required`**
   - Name of vector map
   - Or data source for direct OGR access
   - Used as: input, vector, name

3. **`column : str, required`**
   - Name of attribute column to be used for labels
   - Used as: input, dbcolumn, name

4. **`type : str | list[str], optional`**
   - Input feature type
   - Allowed values: point, line, boundary, centroid
   - Default: point,line,boundary,centroid

5. **`layer : str, optional`**
   - Layer number or name
   - Vector features can have category values in different layers. This number determines which layer to use. When used with direct OGR access this is the layer name.
   - Used as: input, layer

6. **`where : str, optional`**
   - WHERE conditions of SQL statement without 'where' keyword
   - Example: income < 1000 and population >= 10000
   - Used as: input, sql_query, sql_query

7. **`xoffset : float, optional`**
   - Offset label in x-direction
   - Default: 0

8. **`yoffset : float, optional`**
   - Offset label in y-direction
   - Default: 0

9. **`reference : str | list[str], optional`**
   - Reference position
   - Allowed values: center, left, right, upper, lower
   - Default: center

10. **`font : str, optional`**
   - Font name
   - Default: standard

11. **`size : float, optional`**
   - Label size (in map-units)
   - Default: 100

12. **`space : float, optional`**
   - Space between letters for curled labels (in map-units)

13. **`fontsize : int, optional`**
   - Label size (in points)
   - Allowed values: 1-1000

14. **`color : str, optional`**
   - Text color
   - Either a standard color name or R:G:B triplet
   - Used as: input, color, name

15. **`rotation : float, optional`**
   - Rotation angle in degrees (counter-clockwise)
   - Used as: angle
   - Allowed values: 0-360

16. **`width : float, optional`**
   - Border width
   - Allowed values: 0-25
   - Default: 1

17. **`highlight_color : str, optional`**
   - Highlight color for text
   - Either a standard color name, R:G:B triplet, or "none"
   - Used as: input, color, name

18. **`highlight_width : float, optional`**
   - Width of highlight coloring
   - Default: 0

19. **`bgcolor : str, optional`**
   - Background color
   - Either a standard color name, R:G:B triplet, or "none"
   - Used as: input, color, name

20. **`border : str, optional`**
   - Border color
   - Either a standard color name, R:G:B triplet, or "none"
   - Used as: input, color, name

21. **`opaque : str, optional`**
   - Opaque to vector (only relevant if background color is selected)
   - Used as: yes|no
   - Allowed values: yes, no

22. **`flags : str, optional`**
   - Allowed values: a, c
   - a
   - Rotate labels to align with lines
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/v.label.html#__tabbed_2_3) for all details)*

23. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

24. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

25. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 25 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/v.label.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

v.label makes a label-file from a GRASS vector map with labels created
from attributes in the attached table. If no label file name is given,
the name of the source map is used.

---

## See Also

Related tools:
- [`d.labels`](https://grass.osgeo.org/grass-devel/manuals/d.labels.html)
- [`ps.map`](https://grass.osgeo.org/grass-devel/manuals/ps.map.html)

---

## Authors

Philip Verhagen (original s.label) Radim Blazek (GRASS 6 port) Hamish Bowman (enhancements)

---

## Resources

- [Official v.label manual](https://grass.osgeo.org/grass-devel/manuals/v.label.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/v.label.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
