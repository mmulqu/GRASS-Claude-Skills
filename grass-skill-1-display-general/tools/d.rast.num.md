# d.rast.num

**Category**: display

## Description

Overlays cell category values on a raster map displayed in the active graphics frame.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.d_rast_num(map,text_color="black",grid_color="gray",precision=1,font=None,path=None,charset=None,flags=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`map : str | np.ndarray, required`**
   - Name of raster map
   - Used as: input, raster, name

2. **`text_color : str, optional`**
   - Text color
   - Either a standard color name or R:G:B triplet
   - Used as: input, color, name

3. **`grid_color : str, optional`**
   - Grid color
   - Either a standard color name, R:G:B triplet, or "none"
   - Used as: input, color, name

4. **`precision : int, optional`**
   - Number of significant digits (floating point only)
   - Allowed values: 0, 1, 2, 3, 4, 5, 6, 7, 8, 9
   - Default: 1

5. **`font : str, optional`**
   - Font name

6. **`path : str, optional`**
   - Path to font file
   - Used as: file, name

7. **`charset : str, optional`**
   - Text encoding (only applicable to TrueType fonts)

8. **`flags : str, optional`**
   - Allowed values: a, f
   - a
   - Align grids with raster cells
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/d.rast.num.html#__tabbed_2_3) for all details)*

9. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

10. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

11. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 11 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/d.rast.num.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

d.rast.num overlays cell category values onto a raster map layer
displayed on the user's graphics monitor. Category values will be
displayed in the text color given and scaled to fit within a single
cell. A grid outlining each map cell will also be overlain in a
user-specified color, unless it has been set to "none".

If no grid color is given the default will be used. If no map layer is
specified, the program will use whatever raster map layer is currently
displayed in the active frame on the graphics monitor.

If the -f flag is given the displayed number will take on the color
of the base map in that cell.

---

## See Also

Related tools:
- [`d.frame`](https://grass.osgeo.org/grass-devel/manuals/d.frame.html)
- [`d.grid`](https://grass.osgeo.org/grass-devel/manuals/d.grid.html)
- [`d.rast`](https://grass.osgeo.org/grass-devel/manuals/d.rast.html)
- [`d.rast.arrow`](https://grass.osgeo.org/grass-devel/manuals/d.rast.arrow.html)
- [`d.rast.edit`](https://grass.osgeo.org/grass-devel/manuals/d.rast.edit.html)
- [`g.region`](https://grass.osgeo.org/grass-devel/manuals/g.region.html)
- [`r.slope.aspect`](https://grass.osgeo.org/grass-devel/manuals/r.slope.aspect.html)

---

## Authors

Raghavan Srinivasan, and Chris Rewerts, Agricultural Engineering, Purdue University

---

## Resources

- [Official d.rast.num manual](https://grass.osgeo.org/grass-devel/manuals/d.rast.num.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/d.rast.num.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
