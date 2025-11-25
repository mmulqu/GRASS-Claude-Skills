# d.rast.leg

**Category**: display

## Description

Displays a raster map and its legend on a graphics window

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.d_rast_leg(map,lines=None,raster=None,flags=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`map : str | np.ndarray, required`**
   - Name of raster map to display
   - Used as: input, raster, name

2. **`lines : int, optional`**
   - Number of lines to appear in the legend

3. **`raster : str | np.ndarray, optional`**
   - Name of input raster map to generate legend from
   - Used as: input, raster, name

4. **`flags : str, optional`**
   - Allowed values: f, n, s
   - f
   - Flip legend
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/d.rast.leg.html#__tabbed_2_3) for all details)*

5. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

6. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

7. **`superquiet : bool, optional`**
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

d.rast.leg shows a raster map along with its legend. It first clears
the entire screen, then divides it into a main (left) and a minor
(right) frames, and displays a raster map in the main frame and the map
legend in the minor frame. The main frame remains active when the
program finishes.

---

## See Also

Related tools:
- [`d.legend`](https://grass.osgeo.org/grass-devel/manuals/d.legend.html)
- [`d.erase`](https://grass.osgeo.org/grass-devel/manuals/d.erase.html)
- [`d.rast`](https://grass.osgeo.org/grass-devel/manuals/d.rast.html)

---

## Authors

Jianping Xu, Scott Madry, Rutgers University Markus Neteler

---

## Resources

- [Official d.rast.leg manual](https://grass.osgeo.org/grass-devel/manuals/d.rast.leg.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/d.rast.leg.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
