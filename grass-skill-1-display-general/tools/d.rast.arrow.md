# d.rast.arrow

**Category**: display

## Description

Draws arrows representing cell aspect direction for a raster map containing aspect data.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.d_rast_arrow(map,type="grass",color="green",grid_color="gray",null_color="black",unknown_color="red",skip=1,magnitude_map=None,scale=1.0,flags=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`map : str | np.ndarray, required`**
   - Name of raster aspect map to be displayed
   - Used as: input, raster, name

2. **`type : str, optional`**
   - Type of existing raster aspect map
   - Allowed values: grass, compass, drainage, agnps, answers, terraflow
   - Default: grass

3. **`color : str, optional`**
   - Color for drawing arrows
   - Either a standard color name or R:G:B triplet
   - Used as: input, color, name

4. **`grid_color : str, optional`**
   - Color for drawing drawing grid
   - Either a standard color name, R:G:B triplet, or "none"
   - Used as: input, color, name

5. **`null_color : str, optional`**
   - Color for drawing null values (X symbol)
   - Either a standard color name, R:G:B triplet, or "none"
   - Used as: input, color, name

6. **`unknown_color : str, optional`**
   - Color for showing unknown information (? symbol)
   - Either a standard color name, R:G:B triplet, or "none"
   - Used as: input, color, name

7. **`skip : int, optional`**
   - Draw arrow every Nth grid cell
   - Default: 1

8. **`magnitude_map : str | np.ndarray, optional`**
   - Raster map containing values used for arrow length
   - Used as: input, raster

9. **`scale : float, optional`**
   - Scale factor for arrows (magnitude map)
   - Default: 1.0

10. **`flags : str, optional`**
   - Allowed values: a
   - a
   - Align grids with raster cells

11. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

12. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

13. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 13 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/d.rast.arrow.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

d.rast.arrow is designed to help users better visualize surface water
flow direction, as indicated in an aspect raster map layer. There are
two ways to specify the aspect layer the program is to use. The first is
to display the aspect map layer on the graphics monitor before running d.rast.arrow . The second method involves setting the map parameter
to the name of the desired aspect map. This allows the arrows to be
drawn over any other maps already displayed on the graphics monitor.

d.rast.arrow will draw an arrow over each displayed cell to indicate
in which direction the cell slopes. If the aspect layer has a category
value denoting locations of "unknown" aspect, d.rast.arrow draws a
question mark over the displayed cells of that category. Cells
containing null data will be marked with an "X". You can disable drawing
of null data and unknown aspect values by setting its color to " none ".

When specifying the magnitude_map option, arrow lengths denoting
magnitude will be extracted from the cell values of the specified map.
In this case the tail of the arrow will be centered on the source cell.
You may adjust the overall scale using the scale option. d.rast.arrow will ignore NULL and negative magnitudes, and will warn
you if the debug level is set at 5 or higher. Be aware. If your
application uses negative values for magnitude, you can use r.mapcalc to prepare the magnitude map to suit your
needs (absolute value, inverted direction and so on).

---

## See Also

Related tools:
- [`d.frame`](https://grass.osgeo.org/grass-devel/manuals/d.frame.html)
- [`d.rast`](https://grass.osgeo.org/grass-devel/manuals/d.rast.html)
- [`d.rast.edit`](https://grass.osgeo.org/grass-devel/manuals/d.rast.edit.html)
- [`d.rast.num`](https://grass.osgeo.org/grass-devel/manuals/d.rast.num.html)
- [`g.region`](https://grass.osgeo.org/grass-devel/manuals/g.region.html)
- [`r.slope.aspect`](https://grass.osgeo.org/grass-devel/manuals/r.slope.aspect.html)
- [`r.watershed`](https://grass.osgeo.org/grass-devel/manuals/r.watershed.html)
- [`r.terraflow`](https://grass.osgeo.org/grass-devel/manuals/r.terraflow.html)

---

## Authors

Original author: Chris Rewerts, Agricultural Engineering, Purdue University
Magnitude and 360 arrow code: Hamish Bowman, Department of Marine Science,
University of Otago, New Zealand
Align grids with raster cells and Drainage aspect type: Huidae Cho

---

## Resources

- [Official d.rast.arrow manual](https://grass.osgeo.org/grass-devel/manuals/d.rast.arrow.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/d.rast.arrow.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
