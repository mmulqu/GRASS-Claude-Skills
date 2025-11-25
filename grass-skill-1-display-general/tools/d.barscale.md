# d.barscale

**Category**: display

## Description

Displays a barscale on the graphics monitor.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.d_barscale(style="classic",at="0.0,10.0",length=0,units=None,label=None,segment=10,color="black",bgcolor="white",text_position="right",width_scale=1,font=None,fontsize=12,path=None,charset=None,flags=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`style : str, optional`**
   - Type of barscale to draw
   - Used as: input, barscale
   - Allowed values: classic, line, solid, hollow, full_checker, part_checker, mixed_checker, tail_checker, up_ticks, down_ticks, both_ticks, arrow_ends
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/d.barscale.html#__tabbed_2_3) for all details)*

2. **`at : tuple[float, float] | list[float] | str, optional`**
   - Screen coordinates of the rectangle's top-left corner
   - (0,0) is lower-left of the display frame
   - Used as: x,y
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/d.barscale.html#__tabbed_2_3) for all details)*

3. **`length : int, optional`**
   - Length of barscale in map units
   - Used as: integer
   - Allowed values: 0-

4. **`units : str, optional`**
   - Barscale units to display
   - Allowed values: meters,  kilometers,  feet,  miles

5. **`label : str, optional`**
   - Custom label of unit

6. **`segment : int, optional`**
   - Number of segments
   - Allowed values: 1-100
   - Default: 10

7. **`color : str, optional`**
   - Bar scale and text color
   - Either a standard color name or R:G:B triplet
   - Used as: input, color, name

8. **`bgcolor : str, optional`**
   - Background color (drawn behind the bar)
   - Either a standard color name, R:G:B triplet, or "none"
   - Used as: input, color, name

9. **`text_position : str, optional`**
   - Text position
   - Allowed values: under, over, left, right
   - Default: right

10. **`width_scale : float, optional`**
   - Scale factor to change bar width
   - Allowed values: 0.5-100
   - Default: 1

11. **`font : str, optional`**
   - Font name

12. **`fontsize : float, optional`**
   - Font size
   - Allowed values: 1-360
   - Default: 12

13. **`path : str, optional`**
   - Path to font file
   - Used as: input, file, name

14. **`charset : str, optional`**
   - Text encoding (only applicable to TrueType fonts)

15. **`flags : str, optional`**
   - Allowed values: f, t, n
   - f
   - Use feet/miles instead of meters
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/d.barscale.html#__tabbed_2_3) for all details)*

16. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

17. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

18. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 18 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/d.barscale.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

d.barscale displays a barscale on the graphics monitor at the given
screen coordinates. If no coordinates are given it will draw the
barscale in the bottom left of the display.

The barscale can drawn in a number of styles (see style parameter
for their previews).

---

## Note

d.barscale will not work with Lat/Lon coordinate reference system as
the horizontal scale distance changes with latitude. Try d.grid instead.

---

## See Also

Related tools:
- [`d.graph`](https://grass.osgeo.org/grass-devel/manuals/d.graph.html)
- [`d.grid`](https://grass.osgeo.org/grass-devel/manuals/d.grid.html)
- [`d.legend`](https://grass.osgeo.org/grass-devel/manuals/d.legend.html)
- [`d.northarrow`](https://grass.osgeo.org/grass-devel/manuals/d.northarrow.html)
- [`g.region`](https://grass.osgeo.org/grass-devel/manuals/g.region.html)

---

## Authors

Unknown, from USACE/CERL. Major rewrite for GRASS 7 by Hamish Bowman

---

## Resources

- [Official d.barscale manual](https://grass.osgeo.org/grass-devel/manuals/d.barscale.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/d.barscale.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
