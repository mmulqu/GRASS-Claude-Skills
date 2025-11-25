# d.vect

**Category**: display

## Description

Displays user-specified vector map in the active graphics frame.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.d_vect(map,layer="1",display="shape",type="point,line,area,face",cats=None,where=None,color="0:29:57",fill_color="0:103:204",rgb_column=None,zcolor=None,width=0,width_column=None,width_scale=1,icon="basic/x",size=5,size_column=None,rotation_column=None,icon_area="legend/area",icon_line="legend/line",legend_label=None,label_layer="1",attribute_column=None,label_color="red",label_bgcolor="none",label_bcolor="none",label_size=8,font=None,encoding=None,xref="left",yref="center",minreg=None,maxreg=None,flags=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`map : str, required`**
   - Name of vector map
   - Or data source for direct OGR access
   - Used as: input, vector, name

2. **`layer : str, optional`**
   - Layer number or name ('-1' for all layers)
   - A single vector map can be connected to multiple database tables. This number determines which table to use. When used with direct OGR access this is the layer name.
   - Used as: input, layer

3. **`display : str | list[str], required`**
   - Display
   - Allowed values: shape, cat, topo, vert, dir, zcoor
   - shape: Display geometry of features
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/d.vect.html#__tabbed_2_3) for all details)*

4. **`type : str | list[str], optional`**
   - Input feature type
   - Allowed values: point, line, boundary, centroid, area, face
   - Default: point,line,area,face

5. **`cats : str, optional`**
   - Category values
   - Example: 1,3,7-9,13
   - Used as: input, cats, range

6. **`where : str, optional`**
   - WHERE conditions of SQL statement without 'where' keyword
   - Example: income < 1000 and population >= 10000
   - Used as: input, sql_query, sql_query

7. **`color : str, optional`**
   - Feature color
   - Either a standard color name, R:G:B triplet, or "none"
   - Used as: input, color, name

8. **`fill_color : str, optional`**
   - Area fill color
   - Either a standard color name, R:G:B triplet, or "none"
   - Used as: input, color, name

9. **`rgb_column : str, optional`**
   - Colorize features according to color definition column
   - Color definition in R:G:B form
   - Used as: input, dbcolumn, name

10. **`zcolor : str, optional`**
   - Colorize point or area features according to z-coordinate
   - Used as: input, colortable, style
   - Allowed values: aspect, aspectcolr, bcyr, bgyr, blues, byg, byr, celsius, corine, curvature, differences, elevation, etopo2, evi, fahrenheit, forest_cover, gdd, grass, greens, grey, grey.eq, grey.log, grey1.0, grey255, gyr, haxby, inferno, kelvin, magma, ndvi, ndwi, nlcd, oranges, plasma, population, population_dens, precipitation, precipitation_daily, precipitation_monthly, rainbow, ramp, random, reds, roygbiv, rstcurv, ryb, ryg, sepia, slope, soilmoisture, srtm, srtm_percent, srtm_plus, terrain, viridis, water, wave
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/d.vect.html#__tabbed_2_3) for all details)*

11. **`width : int, optional`**
   - Line width
   - Default: 0

12. **`width_column : str, optional`**
   - Name of numeric column containing line width
   - These values will be scaled by width_scale
   - Used as: input, dbcolumn, name

13. **`width_scale : float, optional`**
   - Scale factor for width_column
   - Default: 1

14. **`icon : str, optional`**
   - Point and centroid symbol
   - Allowed values: basic/arrow, basic/arrow1, basic/arrow2, basic/arrow3, basic/box, basic/circle, basic/cross1, basic/cross2, basic/cross3, basic/diamond, basic/hexagon, basic/marker, basic/octagon, basic/pin, basic/pin_dot, basic/point, basic/pushpin, basic/star, basic/triangle, basic/x, demo/muchomurka, demo/smrk, extra/4pt_star, extra/adcp, extra/airport, extra/alpha_flag, extra/bridge, extra/dim_arrow, extra/dive_flag, extra/fiducial, extra/fish, extra/half-box, extra/half-circle, extra/offbox_ne, extra/offbox_nw, extra/offbox_se, extra/offbox_sw, extra/pentagon, extra/ping, extra/ring, extra/simple_zia, extra/target, geology/circle_cross, geology/half-arrow_left, geology/half-arrow_right, geology/strike_box, geology/strike_circle, geology/strike_cleavage, geology/strike_half-bowtie, geology/strike_line, geology/strike_parallel, geology/strike_triangle, legend/area, legend/area_curved, legend/line, legend/line_crooked, n_arrows/basic_compass, n_arrows/fancy_compass, n_arrows/n_arrow1a, n_arrows/n_arrow1b, n_arrows/n_arrow2, n_arrows/n_arrow3, n_arrows/n_arrow4, n_arrows/n_arrow5, n_arrows/n_arrow6, n_arrows/n_arrow7a, n_arrows/n_arrow7b, n_arrows/n_arrow8a, n_arrows/n_arrow8b, n_arrows/n_arrow9
   - Default: basic/x

15. **`size : float, optional`**
   - Symbol size
   - When used with the size_column option this becomes the scale factor
   - Default: 5

16. **`size_column : str, optional`**
   - Name of numeric column containing symbol size
   - Used as: input, dbcolumn, name

17. **`rotation_column : str, optional`**
   - Name of numeric column containing symbol rotation angle
   - Measured in degrees CCW from east
   - Used as: input, dbcolumn, name

18. **`icon_area : str, optional`**
   - Area/boundary symbol for legend
   - Allowed values: basic/arrow, basic/arrow1, basic/arrow2, basic/arrow3, basic/box, basic/circle, basic/cross1, basic/cross2, basic/cross3, basic/diamond, basic/hexagon, basic/marker, basic/octagon, basic/pin, basic/pin_dot, basic/point, basic/pushpin, basic/star, basic/triangle, basic/x, demo/muchomurka, demo/smrk, extra/4pt_star, extra/adcp, extra/airport, extra/alpha_flag, extra/bridge, extra/dim_arrow, extra/dive_flag, extra/fiducial, extra/fish, extra/half-box, extra/half-circle, extra/offbox_ne, extra/offbox_nw, extra/offbox_se, extra/offbox_sw, extra/pentagon, extra/ping, extra/ring, extra/simple_zia, extra/target, geology/circle_cross, geology/half-arrow_left, geology/half-arrow_right, geology/strike_box, geology/strike_circle, geology/strike_cleavage, geology/strike_half-bowtie, geology/strike_line, geology/strike_parallel, geology/strike_triangle, legend/area, legend/area_curved, legend/line, legend/line_crooked, n_arrows/basic_compass, n_arrows/fancy_compass, n_arrows/n_arrow1a, n_arrows/n_arrow1b, n_arrows/n_arrow2, n_arrows/n_arrow3, n_arrows/n_arrow4, n_arrows/n_arrow5, n_arrows/n_arrow6, n_arrows/n_arrow7a, n_arrows/n_arrow7b, n_arrows/n_arrow8a, n_arrows/n_arrow8b, n_arrows/n_arrow9
   - Default: legend/area

19. **`icon_line : str, optional`**
   - Line symbol for legend
   - Allowed values: basic/arrow, basic/arrow1, basic/arrow2, basic/arrow3, basic/box, basic/circle, basic/cross1, basic/cross2, basic/cross3, basic/diamond, basic/hexagon, basic/marker, basic/octagon, basic/pin, basic/pin_dot, basic/point, basic/pushpin, basic/star, basic/triangle, basic/x, demo/muchomurka, demo/smrk, extra/4pt_star, extra/adcp, extra/airport, extra/alpha_flag, extra/bridge, extra/dim_arrow, extra/dive_flag, extra/fiducial, extra/fish, extra/half-box, extra/half-circle, extra/offbox_ne, extra/offbox_nw, extra/offbox_se, extra/offbox_sw, extra/pentagon, extra/ping, extra/ring, extra/simple_zia, extra/target, geology/circle_cross, geology/half-arrow_left, geology/half-arrow_right, geology/strike_box, geology/strike_circle, geology/strike_cleavage, geology/strike_half-bowtie, geology/strike_line, geology/strike_parallel, geology/strike_triangle, legend/area, legend/area_curved, legend/line, legend/line_crooked, n_arrows/basic_compass, n_arrows/fancy_compass, n_arrows/n_arrow1a, n_arrows/n_arrow1b, n_arrows/n_arrow2, n_arrows/n_arrow3, n_arrows/n_arrow4, n_arrows/n_arrow5, n_arrows/n_arrow6, n_arrows/n_arrow7a, n_arrows/n_arrow7b, n_arrows/n_arrow8a, n_arrows/n_arrow8b, n_arrows/n_arrow9
   - Default: legend/line

20. **`legend_label : str, optional`**
   - Label to display after symbol in vector legend

21. **`label_layer : str, optional`**
   - Layer number for labels (default: the given layer number)
   - Vector features can have category values in different layers. This number determines which layer to use. When used with direct OGR access this is the layer name.
   - Used as: input, layer

22. **`attribute_column : str, optional`**
   - Name of column to be displayed as a label
   - Used as: input, dbcolumn, name

23. **`label_color : str, optional`**
   - Label color
   - Either a standard color name or R:G:B triplet
   - Used as: input, color, name

24. **`label_bgcolor : str, optional`**
   - Label background color
   - Either a standard color name, R:G:B triplet, or "none"
   - Used as: input, color, name

25. **`label_bcolor : str, optional`**
   - Label border color
   - Either a standard color name, R:G:B triplet, or "none"
   - Used as: input, color, name

26. **`label_size : int, optional`**
   - Label size (pixels)
   - Default: 8

27. **`font : str, optional`**
   - Font name

28. **`encoding : str, optional`**
   - Text encoding

29. **`xref : str, optional`**
   - Label horizontal justification
   - Allowed values: left, center, right
   - Default: left

30. **`yref : str, optional`**
   - Label vertical justification
   - Allowed values: top, center, bottom
   - Default: center

31. **`minreg : float, optional`**
   - Minimum region size (average from height and width) when map is displayed

32. **`maxreg : float, optional`**
   - Maximum region size (average from height and width) when map is displayed

33. **`flags : str, optional`**
   - Allowed values: c, i, r, s
   - c
   - Random colors according to category number (or layer number if 'layer=-1' is given)
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/d.vect.html#__tabbed_2_3) for all details)*

34. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

35. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

36. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 36 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/d.vect.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

d.vect displays vector maps in the active frame on the graphics
monitor.

---

## See Also

Related tools:
- [`v.colors`](https://grass.osgeo.org/grass-devel/manuals/v.colors.html)
- [`d.erase`](https://grass.osgeo.org/grass-devel/manuals/d.erase.html)
- [`d.rast`](https://grass.osgeo.org/grass-devel/manuals/d.rast.html)
- [`v.colors`](https://grass.osgeo.org/grass-devel/manuals/v.colors.html)
- [`v.db.addcolumn`](https://grass.osgeo.org/grass-devel/manuals/v.db.addcolumn.html)
- [`v.db.update`](https://grass.osgeo.org/grass-devel/manuals/v.db.update.html)

---

## Authors

CERL Radim Blazek, ITC-Irst, Trento, Italy Support for color tables by Martin Landa, Czech Technical University in
Prague (8/2011) and many other GRASS developers

---

## Resources

- [Official d.vect manual](https://grass.osgeo.org/grass-devel/manuals/d.vect.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/d.vect.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
