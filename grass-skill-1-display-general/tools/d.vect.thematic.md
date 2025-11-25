# d.vect.thematic

**Category**: display

## Description

Displays a thematic vector map in the active graphics frame.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.d_vect_thematic(map,layer="1",column,breaks=None,algorithm=None,nclasses=None,colors,where=None,boundary_width=1,boundary_color="black",icon="basic/x",size=5,icon_line="legend/line",icon_area="legend/area",legend_title=None,legendfile=None,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`map : str, required`**
   - Name of vector map
   - Or data source for direct OGR access
   - Used as: input, vector, name

2. **`layer : str, optional`**
   - Layer number or name
   - Layer number. If -1, all layers are displayed.
   - Used as: input, layer

3. **`column : str, required`**
   - Name of attribute column to be classified
   - Used as: input, dbcolumn, name

4. **`breaks : str | list[str], optional`**
   - Class breaks, without minimum and maximum

5. **`algorithm : str, optional`**
   - Algorithm to use for classification
   - Allowed values: int, std, qua, equ, dis
   - int: simple intervals
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/d.vect.thematic.html#__tabbed_2_3) for all details)*

6. **`nclasses : int, optional`**
   - Number of classes to define

7. **`colors : str | list[str], required`**
   - Colors (one per class)
   - Used as: color

8. **`where : str, optional`**
   - WHERE conditions of SQL statement without 'where' keyword
   - Example: income < 1000 and population >= 10000
   - Used as: input, sql_query, sql_query

9. **`boundary_width : int, optional`**
   - Boundary width
   - Default: 1

10. **`boundary_color : str, optional`**
   - Boundary color
   - Either a standard color name, R:G:B triplet, or "none"
   - Used as: input, color, name

11. **`icon : str, optional`**
   - Point and centroid symbol
   - Allowed values: basic/arrow, basic/arrow1, basic/arrow2, basic/arrow3, basic/box, basic/circle, basic/cross1, basic/cross2, basic/cross3, basic/diamond, basic/hexagon, basic/marker, basic/octagon, basic/pin, basic/pin_dot, basic/point, basic/pushpin, basic/star, basic/triangle, basic/x, demo/muchomurka, demo/smrk, extra/4pt_star, extra/adcp, extra/airport, extra/alpha_flag, extra/bridge, extra/dim_arrow, extra/dive_flag, extra/fiducial, extra/fish, extra/half-box, extra/half-circle, extra/offbox_ne, extra/offbox_nw, extra/offbox_se, extra/offbox_sw, extra/pentagon, extra/ping, extra/ring, extra/simple_zia, extra/target, geology/circle_cross, geology/half-arrow_left, geology/half-arrow_right, geology/strike_box, geology/strike_circle, geology/strike_cleavage, geology/strike_half-bowtie, geology/strike_line, geology/strike_parallel, geology/strike_triangle, legend/area, legend/area_curved, legend/line, legend/line_crooked, n_arrows/basic_compass, n_arrows/fancy_compass, n_arrows/n_arrow1a, n_arrows/n_arrow1b, n_arrows/n_arrow2, n_arrows/n_arrow3, n_arrows/n_arrow4, n_arrows/n_arrow5, n_arrows/n_arrow6, n_arrows/n_arrow7a, n_arrows/n_arrow7b, n_arrows/n_arrow8a, n_arrows/n_arrow8b, n_arrows/n_arrow9
   - Default: basic/x

12. **`size : float, optional`**
   - Symbol size
   - Default: 5

13. **`icon_line : str, optional`**
   - Legend symbol for lines
   - Allowed values: basic/arrow, basic/arrow1, basic/arrow2, basic/arrow3, basic/box, basic/circle, basic/cross1, basic/cross2, basic/cross3, basic/diamond, basic/hexagon, basic/marker, basic/octagon, basic/pin, basic/pin_dot, basic/point, basic/pushpin, basic/star, basic/triangle, basic/x, demo/muchomurka, demo/smrk, extra/4pt_star, extra/adcp, extra/airport, extra/alpha_flag, extra/bridge, extra/dim_arrow, extra/dive_flag, extra/fiducial, extra/fish, extra/half-box, extra/half-circle, extra/offbox_ne, extra/offbox_nw, extra/offbox_se, extra/offbox_sw, extra/pentagon, extra/ping, extra/ring, extra/simple_zia, extra/target, geology/circle_cross, geology/half-arrow_left, geology/half-arrow_right, geology/strike_box, geology/strike_circle, geology/strike_cleavage, geology/strike_half-bowtie, geology/strike_line, geology/strike_parallel, geology/strike_triangle, legend/area, legend/area_curved, legend/line, legend/line_crooked, n_arrows/basic_compass, n_arrows/fancy_compass, n_arrows/n_arrow1a, n_arrows/n_arrow1b, n_arrows/n_arrow2, n_arrows/n_arrow3, n_arrows/n_arrow4, n_arrows/n_arrow5, n_arrows/n_arrow6, n_arrows/n_arrow7a, n_arrows/n_arrow7b, n_arrows/n_arrow8a, n_arrows/n_arrow8b, n_arrows/n_arrow9
   - Default: legend/line

14. **`icon_area : str, optional`**
   - Legend symbol for areas
   - Allowed values: basic/arrow, basic/arrow1, basic/arrow2, basic/arrow3, basic/box, basic/circle, basic/cross1, basic/cross2, basic/cross3, basic/diamond, basic/hexagon, basic/marker, basic/octagon, basic/pin, basic/pin_dot, basic/point, basic/pushpin, basic/star, basic/triangle, basic/x, demo/muchomurka, demo/smrk, extra/4pt_star, extra/adcp, extra/airport, extra/alpha_flag, extra/bridge, extra/dim_arrow, extra/dive_flag, extra/fiducial, extra/fish, extra/half-box, extra/half-circle, extra/offbox_ne, extra/offbox_nw, extra/offbox_se, extra/offbox_sw, extra/pentagon, extra/ping, extra/ring, extra/simple_zia, extra/target, geology/circle_cross, geology/half-arrow_left, geology/half-arrow_right, geology/strike_box, geology/strike_circle, geology/strike_cleavage, geology/strike_half-bowtie, geology/strike_line, geology/strike_parallel, geology/strike_triangle, legend/area, legend/area_curved, legend/line, legend/line_crooked, n_arrows/basic_compass, n_arrows/fancy_compass, n_arrows/n_arrow1a, n_arrows/n_arrow1b, n_arrows/n_arrow2, n_arrows/n_arrow3, n_arrows/n_arrow4, n_arrows/n_arrow5, n_arrows/n_arrow6, n_arrows/n_arrow7a, n_arrows/n_arrow7b, n_arrows/n_arrow8a, n_arrows/n_arrow8b, n_arrows/n_arrow9
   - Default: legend/area

15. **`legend_title : str, optional`**
   - Thematic map title

16. **`legendfile : str, optional`**
   - [DEPRECATED] Output legend file
   - Used as: output, file, name

17. **`flags : str, optional`**
   - Allowed values: l, n, e, s
   - l
   - Create legend information and send to stdout
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/d.vect.thematic.html#__tabbed_2_3) for all details)*

18. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

19. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

20. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

21. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 21 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/d.vect.thematic.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

d.vect.thematic draws thematic choropleth vector maps based on an
attribute column or an expression involving several columns. It takes a
list of class breaks (excluding the minimum and maximum values) and
a list of colors to apply to the classes (has to be the number of
class breaks + 1).

Instead of a list of class breaks, the user can also chose a
classification algorithm and a number of classes ( nbclasses ).
See the v.class for more information on these different
algorithms.

---

## See Also

Related tools:
- [`v.class`](https://grass.osgeo.org/grass-devel/manuals/v.class.html)
- [`d.legend.vect`](https://grass.osgeo.org/grass-devel/manuals/d.legend.vect.html)
- [`d.vect`](https://grass.osgeo.org/grass-devel/manuals/d.vect.html)
- [`d.graph`](https://grass.osgeo.org/grass-devel/manuals/d.graph.html)
- [`v.univar`](https://grass.osgeo.org/grass-devel/manuals/v.univar.html)

---

## Resources

- [Official d.vect.thematic manual](https://grass.osgeo.org/grass-devel/manuals/d.vect.thematic.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/d.vect.thematic.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
