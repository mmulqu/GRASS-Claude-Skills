# d.legend

**Category**: display

## Description

Displays a legend for a 2D or 3D raster map in the active frame of the graphics monitor.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.d_legend(raster=None,raster_3d=None,title=None,title_fontsize=None,lines=0,thin=1,units=None,labelnum=5,label_values=None,label_step=None,digits=None,at=None,use=None,range=None,color="black",font=None,fontsize=None,path=None,charset=None,border_color="black",bgcolor="white",flags=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`raster : str | np.ndarray, optional`**
   - Name of raster map
   - Used as: input, raster, name

2. **`raster_3d : str, optional`**
   - Name of 3D raster map
   - Used as: input, raster_3d, name

3. **`title : str, optional`**
   - Legend title

4. **`title_fontsize : float, optional`**
   - Title font size
   - Default: Same as fontsize
   - Allowed values: 1-360

5. **`lines : int, optional`**
   - Number of text lines (useful for truncating long legends)
   - Allowed values: 0-1000
   - Default: 0

6. **`thin : int, optional`**
   - Thinning factor (thin=10 gives cats 0,10,20...)
   - Allowed values: 1-1000
   - Default: 1

7. **`units : str, optional`**
   - Units to display after labels (e.g. meters)

8. **`labelnum : int, optional`**
   - Number of text labels for smooth gradient legend
   - Allowed values: 2-100
   - Default: 5

9. **`label_values : float | list[float] | str, optional`**
   - Specific values to draw ticks

10. **`label_step : float, optional`**
   - Display label every step

11. **`digits : int, optional`**
   - Number of digits after decimal point
   - Allowed values: 0-6

12. **`at : tuple[float, float, float, float] | list[float] | str, optional`**
   - Size and placement as percentage of screen coordinates (0,0 is lower left)
   - bottom,top,left,right
   - Used as: bottom,top,left,right

13. **`use : float | list[float] | str, optional`**
   - List of discrete category numbers/values for legend

14. **`range : tuple[float, float] | list[float] | str, optional`**
   - Use a subset of the map range for the legend (min,max)
   - Used as: min,max

15. **`color : str, optional`**
   - Text color
   - Either a standard color name or R:G:B triplet
   - Used as: input, color, name

16. **`font : str, optional`**
   - Font name

17. **`fontsize : float, optional`**
   - Font size
   - Default: Auto-scaled
   - Allowed values: 1-360

18. **`path : str, optional`**
   - Path to font file
   - Used as: file, name

19. **`charset : str, optional`**
   - Text encoding (only applicable to TrueType fonts)

20. **`border_color : str, optional`**
   - Border color
   - Either a standard color name, R:G:B triplet, or "none"
   - Used as: input, color, name

21. **`bgcolor : str, optional`**
   - Background color
   - Either a standard color name, R:G:B triplet, or "none"
   - Used as: input, color, name

22. **`flags : str, optional`**
   - Allowed values: v, c, t, n, s, f, d, b, l
   - v
   - Do not show category labels
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/d.legend.html#__tabbed_2_3) for all details)*

23. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

24. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

25. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 25 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/d.legend.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

d.legend displays a legend for a user-specified raster map or 3D
raster map layer in the active frame on the graphics monitor.

The legend's default size is based on the dimensions of the active
frame, specifically its height. d.legend will only obscure those
portions of the active frame that directly underlie the legend.

---

## See Also

Related tools:
- [`d.barscale`](https://grass.osgeo.org/grass-devel/manuals/d.barscale.html)
- [`d.colortable`](https://grass.osgeo.org/grass-devel/manuals/d.colortable.html)
- [`d.font`](https://grass.osgeo.org/grass-devel/manuals/d.font.html)
- [`d.grid`](https://grass.osgeo.org/grass-devel/manuals/d.grid.html)
- [`d.rast`](https://grass.osgeo.org/grass-devel/manuals/d.rast.html)
- [`d.rast.leg`](https://grass.osgeo.org/grass-devel/manuals/d.rast.leg.html)
- [`d.text`](https://grass.osgeo.org/grass-devel/manuals/d.text.html)
- [`d.vect.thematic`](https://grass.osgeo.org/grass-devel/manuals/d.vect.thematic.html)
- [`r.reclass`](https://grass.osgeo.org/grass-devel/manuals/r.reclass.html)
- [`r.stats`](https://grass.osgeo.org/grass-devel/manuals/r.stats.html)
- [`r3.stats`](https://grass.osgeo.org/grass-devel/manuals/r3.stats.html)

---

## Authors

Bill Brown, U.S. Army Construction Engineering Research Laboratories Late 2002: Rewrite of much of the code. Hamish Bowman, Otago University,
New Zealand Additional improvements from various authors

---

## Resources

- [Official d.legend manual](https://grass.osgeo.org/grass-devel/manuals/d.legend.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/d.legend.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
