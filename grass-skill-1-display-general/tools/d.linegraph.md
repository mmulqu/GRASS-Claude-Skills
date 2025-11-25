# d.linegraph

**Category**: display

## Description

Generates and displays simple line graphs in the active graphics monitor display frame.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.d_linegraph(x_file,y_file,directory=None,y_color=None,color_table=None,width=None,title_color="black",x_title="",y_title="",title="",y_range=None,y_tics=None,x_scale=None,y_scale=None,icon="basic/circle",point_size=5,secondary_color="black",secondary_width=0.1,flags=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`x_file : str, required`**
   - Name of data file for X axis of graph

2. **`y_file : str | list[str], required`**
   - Name of data file(s) for Y axis of graph

3. **`directory : str, optional`**
   - Path to files
   - Path to the directory where the input files are located

4. **`y_color : str | list[str], optional`**
   - Color for Y data
   - Used as: color

5. **`color_table : str, optional`**
   - Name of color table
   - Used as: input, colortable, style
   - Allowed values: aspect, aspectcolr, bcyr, bgyr, blues, byg, byr, celsius, corine, curvature, differences, elevation, etopo2, evi, fahrenheit, forest_cover, gdd, grass, greens, grey, grey.eq, grey.log, grey1.0, grey255, gyr, haxby, inferno, kelvin, magma, ndvi, ndwi, nlcd, oranges, plasma, population, population_dens, precipitation, precipitation_daily, precipitation_monthly, rainbow, ramp, random, reds, roygbiv, rstcurv, ryb, ryg, sepia, slope, soilmoisture, srtm, srtm_percent, srtm_plus, terrain, viridis, water, wave
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/d.linegraph.html#__tabbed_2_3) for all details)*

6. **`width : int | list[int] | str, optional`**
   - Width of the lines

7. **`title_color : str, optional`**
   - Color for axis, tics, numbers, and title
   - Used as: color
   - Default: black

8. **`x_title : str, optional`**
   - Title for X data

9. **`y_title : str, optional`**
   - Title for Y data

10. **`title : str, optional`**
   - Title for Graph

11. **`y_range : tuple[float, float] | list[float] | str, optional`**
   - Minimum and maximum value for Y axis (min,max)
   - Used as: min,max

12. **`y_tics : float | list[float] | str, optional`**
   - Tic values for the Y axis

13. **`x_scale : float, optional`**
   - Scale for X values

14. **`y_scale : float, optional`**
   - Scale for Y values

15. **`icon : str, optional`**
   - Symbol for point
   - Allowed values: basic/arrow, basic/arrow1, basic/arrow2, basic/arrow3, basic/box, basic/circle, basic/cross1, basic/cross2, basic/cross3, basic/diamond, basic/hexagon, basic/marker, basic/octagon, basic/pin, basic/pin_dot, basic/point, basic/pushpin, basic/star, basic/triangle, basic/x, demo/muchomurka, demo/smrk, extra/4pt_star, extra/adcp, extra/airport, extra/alpha_flag, extra/bridge, extra/dim_arrow, extra/dive_flag, extra/fiducial, extra/fish, extra/half-box, extra/half-circle, extra/offbox_ne, extra/offbox_nw, extra/offbox_se, extra/offbox_sw, extra/pentagon, extra/ping, extra/ring, extra/simple_zia, extra/target, geology/circle_cross, geology/half-arrow_left, geology/half-arrow_right, geology/strike_box, geology/strike_circle, geology/strike_cleavage, geology/strike_half-bowtie, geology/strike_line, geology/strike_parallel, geology/strike_triangle, legend/area, legend/area_curved, legend/line, legend/line_crooked, n_arrows/basic_compass, n_arrows/fancy_compass, n_arrows/n_arrow1a, n_arrows/n_arrow1b, n_arrows/n_arrow2, n_arrows/n_arrow3, n_arrows/n_arrow4, n_arrows/n_arrow5, n_arrows/n_arrow6, n_arrows/n_arrow7a, n_arrows/n_arrow7b, n_arrows/n_arrow8a, n_arrows/n_arrow8b, n_arrows/n_arrow9
   - Default: basic/circle

16. **`point_size : float, optional`**
   - Point size
   - Default: 5

17. **`secondary_color : str, optional`**
   - Color
   - Color for point symbol edge color
   - Used as: input, color, name

18. **`secondary_width : float | list[float] | str, optional`**
   - Width of point symbol lines
   - Default: 0.1

19. **`flags : str, optional`**
   - Allowed values: x, y, s, l
   - x
   - Scale only X labels, not values
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/d.linegraph.html#__tabbed_2_3) for all details)*

20. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

21. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

22. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 22 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/d.linegraph.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

d.linegraph is a module to draw simple x,y line graphs (plots) based
on numerical data contained in separate files.

The X and Y data files for the graph are essentially a column of numbers
in each file, with one input number per line. The program expects that
each X value will have a corresponding Y value, therefore the number of
lines in each data input file should be the same. Essentially, the X
data becomes the X axis reference to which the Y data is plotted as a
line. Therefore, the X data should be a monotonically increasing
progression of numbers (i.e. "1,2,3,..."; "0, 10, 100, 1000,...";
"...-5,-1,0,1,5..."). If multiple Y data files are used, the Y axis
scale will be based on the range of minimum and maximum values from all
Y files, then all Y data given will be graphed according to that Y
scale. Therefore, if multiple Y data inputs are used with dissimilar
units, the graph produced comparing the two will be deceptive.

If the directory option is provided, the paths to files can (and
should) be only relative paths to these files. While this is not
recommended for scripting, it can be advantageous when typing the paths
manually. For example when all files are stored in the directory /home/john/data , the user can provide the following in the command
line:

The user can specify the y_color option, the color_table option
or just leave the defaults to influence the color of the plotted lines.

Colors specified by y_color option are used for drawing the lines in
the graph. If multiple Y data files are used, an equal number of colors
may be used to control the colors of the lines. Colors will be assigned
to Y data in respect to the sequence of instantiation on the command
line. It can be one of GRASS named colors or the RGB values from
0-255 separated by colons (RRR:GGG:BBB).

Alternatively, the user can use the color_table option to specify
one of the GRASS predefined color tables.

By default, a series of colors will be chosen by the module if none are
provided upon invocation. The order of default colors is red, green,
violet, blue, orange, gray, brown, magenta, white, and indigo. The user
is advised not to rely on the order of default colors but to either use
the y_color or the color_table option to obtain predictable and
reproducible results.

The color to be used for titles, axis lines, tics, and scale numbers is
determined by the title_color option. The user can provide one of
the GRASS named colors (such as gray, white, or black) or use the
GRASS colon-separated format for RGB (RRR:GGG:BBB).

The title option specifies the text for the title of the graph. It
will be centered over the top of graph. The x_title option is a text
to describe data for X axis. It will be centered beneath the graph.
Default is no text unless there is a need for a unit descriptor
determined by the d.linegraph module, then string such as "in
hundreds" is generated. The y_title option is a text to describe
data for Y axis. It will be centered beneath the X data description.
Similarly, to the x_title option, default is no text unless there is
a need for an auto-generated description. In the case of graphs with
multiple lines (multiple inputs for Y axis), user may wish to use more
specific text placement using the d.text or v.label programs.

---

## See Also

Related tools:
- [`d.frame`](https://grass.osgeo.org/grass-devel/manuals/d.frame.html)
- [`d.text`](https://grass.osgeo.org/grass-devel/manuals/d.text.html)
- [`v.label`](https://grass.osgeo.org/grass-devel/manuals/v.label.html)
- [`d.graph`](https://grass.osgeo.org/grass-devel/manuals/d.graph.html)
- [`d.histogram`](https://grass.osgeo.org/grass-devel/manuals/d.histogram.html)

---

## Resources

- [Official d.linegraph manual](https://grass.osgeo.org/grass-devel/manuals/d.linegraph.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/d.linegraph.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
