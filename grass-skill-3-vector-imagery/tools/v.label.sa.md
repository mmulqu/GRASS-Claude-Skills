# v.label.sa

**Category**: vector

## Description

Create optimally placed labels for vector map(s)

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.v_label_sa(map,type="point,line,area",layer="1",column,labels,font,size=100,isize=10,charset="UTF-8",color="black",hcolor="none",hwidth=0,background="none",opaque="yes",border="none",width=0,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`map : str, required`**
   - Name of vector map
   - Or data source for direct OGR access
   - Used as: input, vector, name

2. **`type : str | list[str], optional`**
   - Input feature type
   - Allowed values: point, line, area
   - Default: point,line,area

3. **`layer : str, optional`**
   - Layer number or name
   - Vector features can have category values in different layers. This number determines which layer to use. When used with direct OGR access this is the layer name.
   - Used as: input, layer

4. **`column : str, required`**
   - Name of attribute column to be used for labels

5. **`labels : str, required`**
   - Name for new paint-label file
   - Used as: name

6. **`font : str, required`**
   - Name of TrueType font (as listed in the fontcap)

7. **`size : float, optional`**
   - Label size (in map-units)
   - Default: 100

8. **`isize : float, optional`**
   - Icon size of point features (in map-units)
   - Default: 10

9. **`charset : str, optional`**
   - Character encoding (default: UTF-8)
   - Default: UTF-8

10. **`color : str, optional`**
   - Text color
   - Allowed values: aqua, black, blue, brown, cyan, gray, green, grey, indigo, magenta, orange, purple, red, violet, white, yellow
   - Default: black

11. **`hcolor : str, optional`**
   - Highlight color for text
   - Allowed values: none, aqua, black, blue, brown, cyan, gray, green, grey, indigo, magenta, orange, purple, red, violet, white, yellow
   - Default: none

12. **`hwidth : float, optional`**
   - Width of highlight coloring
   - Default: 0

13. **`background : str, optional`**
   - Background color
   - Allowed values: none, aqua, black, blue, brown, cyan, gray, green, grey, indigo, magenta, orange, purple, red, violet, white, yellow
   - Default: none

14. **`opaque : str, optional`**
   - Opaque to vector (only relevant if background color is selected)
   - Used as: yes|no
   - Allowed values: yes, no

15. **`border : str, optional`**
   - Border color
   - Allowed values: none, aqua, black, blue, brown, cyan, gray, green, grey, indigo, magenta, orange, purple, red, violet, white, yellow
   - Default: none

16. **`width : float, optional`**
   - Border width (only for ps.map output)
   - Default: 0

17. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

18. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

19. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 19 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/v.label.sa.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

v.label.sa makes a label-file from a GRASS vector map with labels
created from attributes in the attached table. The labels are placed in
as optimal place as possible. The label file has the same syntax as the
one created by v.label

---

## See Also

Related tools:
- [`v.label`](https://grass.osgeo.org/grass-devel/manuals/v.label.html)
- [`d.labels`](https://grass.osgeo.org/grass-devel/manuals/d.labels.html)
- [`ps.map`](https://grass.osgeo.org/grass-devel/manuals/ps.map.html)

---

## Resources

- [Official v.label.sa manual](https://grass.osgeo.org/grass-devel/manuals/v.label.sa.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/v.label.sa.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
