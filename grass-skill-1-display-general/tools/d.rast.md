# d.rast

**Category**: display

## Description

Displays user-specified raster map in the active graphics frame.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.d_rast(map,values=None,bgcolor="white",flags=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`map : str | np.ndarray, required`**
   - Name of raster map to be displayed
   - Used as: input, raster, name

2. **`values : str | list[str], optional`**
   - List of categories or values to be displayed
   - Used as: value[-value]

3. **`bgcolor : str, optional`**
   - Background color (for null)
   - Either a standard color name or R:G:B triplet
   - Used as: input, color, color

4. **`flags : str, optional`**
   - Allowed values: n, i
   - n
   - Make null cells opaque
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/d.rast.html#__tabbed_2_3) for all details)*

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

d.rast displays the specified raster map in the active display frame
on the graphics monitor.

---

## See Also

Related tools:
- [`d.rast.arrow`](https://grass.osgeo.org/grass-devel/manuals/d.rast.arrow.html)
- [`d.rast.num`](https://grass.osgeo.org/grass-devel/manuals/d.rast.num.html)
- [`d.rast.leg`](https://grass.osgeo.org/grass-devel/manuals/d.rast.leg.html)
- [`d.legend`](https://grass.osgeo.org/grass-devel/manuals/d.legend.html)
- [`d.mon`](https://grass.osgeo.org/grass-devel/manuals/d.mon.html)
- [`d.erase`](https://grass.osgeo.org/grass-devel/manuals/d.erase.html)
- [`d.vect`](https://grass.osgeo.org/grass-devel/manuals/d.vect.html)

---

## Resources

- [Official d.rast manual](https://grass.osgeo.org/grass-devel/manuals/d.rast.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/d.rast.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
