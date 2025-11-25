# d.histogram

**Category**: display

## Description

Displays a histogram in the form of a pie or bar chart for a user-specified raster map.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.d_histogram(map,style="bar",color="black",bgcolor="white",nsteps=255,flags=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`map : str | np.ndarray, required`**
   - Raster map for which histogram will be displayed
   - Used as: input, raster, name

2. **`style : str, optional`**
   - Indicate if a pie or bar chart is desired
   - Allowed values: pie, bar
   - Default: bar

3. **`color : str, optional`**
   - Color for text and axes
   - Either a standard color name or R:G:B triplet
   - Used as: input, color, name

4. **`bgcolor : str, optional`**
   - Background color
   - Either a standard color name, R:G:B triplet, or "none"
   - Used as: input, color, name

5. **`nsteps : int, optional`**
   - Number of steps to divide the data range into (fp maps only)
   - Default: 255

6. **`flags : str, optional`**
   - Allowed values: n, c
   - n
   - Display information for null cells
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/d.histogram.html#__tabbed_2_3) for all details)*

7. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

8. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

9. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

d.histogram displays the category-value distribution for a
user-specified raster map layer, in the form of a bar chart or a pie
chart. The display will be displayed in the active display frame on the
graphics monitor, using the colors in the raster map layer's color
table. The program determines the raster map's category value
distribution by counting cells.

---

## See Also

Related tools:
- [`d.colortable`](https://grass.osgeo.org/grass-devel/manuals/d.colortable.html)
- [`d.frame`](https://grass.osgeo.org/grass-devel/manuals/d.frame.html)
- [`d.graph`](https://grass.osgeo.org/grass-devel/manuals/d.graph.html)
- [`d.linegraph`](https://grass.osgeo.org/grass-devel/manuals/d.linegraph.html)
- [`d.mon`](https://grass.osgeo.org/grass-devel/manuals/d.mon.html)
- [`d.polar`](https://grass.osgeo.org/grass-devel/manuals/d.polar.html)
- [`g.region`](https://grass.osgeo.org/grass-devel/manuals/g.region.html)
- [`r.stats`](https://grass.osgeo.org/grass-devel/manuals/r.stats.html)

---

## Resources

- [Official d.histogram manual](https://grass.osgeo.org/grass-devel/manuals/d.histogram.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/d.histogram.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
