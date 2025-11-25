# d.northarrow

**Category**: display

## Description

Displays a north arrow on the graphics monitor.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.d_northarrow(style="1a",at="85.0,15.0",rotation=0,label="N",color="black",fill_color="black",text_color=None,width=0,font=None,fontsize=14,path=None,charset=None,flags=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`style : str, optional`**
   - North arrow style
   - Used as: input, northarrow
   - Allowed values: 1a, 1b, 2, 3, 4, 5, 6, 7a, 7b, 8a, 8b, 9, fancy_compass, basic_compass, arrow1, arrow2, arrow3, star
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/d.northarrow.html#__tabbed_2_3) for all details)*

2. **`at : tuple[float, float] | list[float] | str, optional`**
   - Screen coordinates of the rectangle's top-left corner
   - (0,0) is lower-left of the display frame
   - Used as: x,y
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/d.northarrow.html#__tabbed_2_3) for all details)*

3. **`rotation : float, optional`**
   - Rotation angle in degrees (counter-clockwise)
   - Default: 0

4. **`label : str, optional`**
   - Displayed letter on the top of arrow
   - Default: N

5. **`color : str, optional`**
   - Line color
   - Either a standard color name, R:G:B triplet, or "none"
   - Used as: input, color, name

6. **`fill_color : str, optional`**
   - Fill color
   - Either a standard color name, R:G:B triplet, or "none"
   - Used as: input, color, name

7. **`text_color : str, optional`**
   - Text color
   - Either a standard color name or R:G:B triplet
   - Used as: input, color, name

8. **`width : float, optional`**
   - Line width
   - Default: 0

9. **`font : str, optional`**
   - Font name

10. **`fontsize : float, optional`**
   - Font size
   - Allowed values: 1-360
   - Default: 14

11. **`path : str, optional`**
   - Path to font file
   - Used as: input, file, name

12. **`charset : str, optional`**
   - Text encoding (only applicable to TrueType fonts)

13. **`flags : str, optional`**
   - Allowed values: t, w, r
   - t
   - Draw the symbol without text
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/d.northarrow.html#__tabbed_2_3) for all details)*

14. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

15. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

16. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 16 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/d.northarrow.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

d.northarrow displays a north arrow symbol at the given screen
coordinates. If no coordinates are given it will draw the north arrow in
the bottom right of the display. It can draw the north arrow in a number
of styles (see the wiki
page for
details). With certain styles of north arrow label 'N' is displayed by
default, and can be changed with option label , for example for
different languages. The label can be hidden with -t flag.

North arrow can be rotated, for example to align with true north, not
grid north. The angle in degrees counter-clockwise (or radians with -r flag) can be specified with option rotation . Label is rotated
together with the arrow, unless flag -w is specified.

---

## See Also

Related tools:
- [`d.barscale`](https://grass.osgeo.org/grass-devel/manuals/d.barscale.html)
- [`d.graph`](https://grass.osgeo.org/grass-devel/manuals/d.graph.html)
- [`d.grid`](https://grass.osgeo.org/grass-devel/manuals/d.grid.html)
- [`d.legend`](https://grass.osgeo.org/grass-devel/manuals/d.legend.html)

---

## Authors

Hamish Bowman, Department of Geology, University of Otago, New
Zealand Improvements as part of GSoC 2016 by Adam Laza, CTU in Prague

---

## Resources

- [Official d.northarrow manual](https://grass.osgeo.org/grass-devel/manuals/d.northarrow.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/d.northarrow.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
