# d.grid

**Category**: display

## Description

Overlays a user-specified grid in the active display frame on the graphics monitor.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.d_grid(size,origin="0,0",direction="both",width=None,color="gray",border_color="black",text_color="gray",bgcolor="none",fontsize=9,flags=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`size : str, required`**
   - Size of grid to be drawn (in map units)
   - 0 for north-south resolution of the current region. In map units or DDD:MM:SS format. Example: "1000" or "0:10"
   - Used as: value

2. **`origin : tuple[float, float] | list[float] | str, optional`**
   - Lines of the grid pass through this coordinate
   - Used as: input, coords, east,north
   - Default: 0,0

3. **`direction : str, optional`**
   - Draw only east-west lines, north-south lines, or both
   - Allowed values: both, east-west, north-south
   - Default: both

4. **`width : float, optional`**
   - Grid line width

5. **`color : str, optional`**
   - Grid color
   - Either a standard color name or R:G:B triplet
   - Used as: input, color, name

6. **`border_color : str, optional`**
   - Border color
   - Either a standard color name or R:G:B triplet
   - Used as: input, color, name

7. **`text_color : str, optional`**
   - Text color
   - Either a standard color name or R:G:B triplet
   - Used as: input, color, name

8. **`bgcolor : str, optional`**
   - Background color
   - Either a standard color name, R:G:B triplet, or "none"
   - Used as: input, color, name

9. **`fontsize : int, optional`**
   - Font size for gridline coordinate labels
   - Allowed values: 1-72
   - Default: 9

10. **`flags : str, optional`**
   - Allowed values: a, g, w, c, d, f, n, b, t
   - a
   - Align the origin to the east-north corner of the current region
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/d.grid.html#__tabbed_2_3) for all details)*

11. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

12. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

13. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 13 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/d.grid.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

d.grid overlays a grid of user-defined size and color in the active
display frame on the graphics monitor. The grid can be created as a
standard rectangular grid or a geographic grid.

If the user provides a -g flag a geographic (projected) grid will be
drawn. With the -g flag the size argument accepts both decimal
degrees and colon separated ddd ss coordinates (eg. 00:30:00 for
half of a degree). A geographic grid cannot be drawn for a latitude/longitude or XY projection.

Colors may be standard named GRASS colors (red, green, aqua, etc.) or a
numerical R:G:B triplet, where component values range from 0-255. Grid
color can be set with option color . Options text_color and bgcolor set the color of the text and its background.

The grid drawing may be turned off by using the -n flag. The border drawing may be turned off by using the -b flag. The coordinate text may be turned off by using the -t flag.

To draw grid lines at different intervals, e.g. at high latitudes, you
can run the module twice, once with direction = east-west at one
interval size , and again with direction = north-south at another
interval size .

---

## See Also

Related tools:
- [`d.barscale`](https://grass.osgeo.org/grass-devel/manuals/d.barscale.html)
- [`d.legend`](https://grass.osgeo.org/grass-devel/manuals/d.legend.html)
- [`d.geodesic`](https://grass.osgeo.org/grass-devel/manuals/d.geodesic.html)
- [`d.rhumbline`](https://grass.osgeo.org/grass-devel/manuals/d.rhumbline.html)
- [`d.erase`](https://grass.osgeo.org/grass-devel/manuals/d.erase.html)
- [`d.frame`](https://grass.osgeo.org/grass-devel/manuals/d.frame.html)
- [`d.rast`](https://grass.osgeo.org/grass-devel/manuals/d.rast.html)
- [`v.mkgrid`](https://grass.osgeo.org/grass-devel/manuals/v.mkgrid.html)

---

## Authors

James Westervelt, U.S. Army Construction Engineering Research
Laboratory Geogrid support: Bob Covill Border support: Markus Neteler Text and RGB support: Hamish Bowman Background color implemented as part of GSoC 2016 by Adam Laza, CTU in
Prague

---

## Resources

- [Official d.grid manual](https://grass.osgeo.org/grass-devel/manuals/d.grid.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/d.grid.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
