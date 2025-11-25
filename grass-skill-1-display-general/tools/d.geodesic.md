# d.geodesic

**Category**: display

## Description

Displays a geodesic line, tracing the shortest distance between two geographic points along a great circle, in a longitude/latitude data set.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.d_geodesic(coordinates,line_color="black",text_color=None,units="meters",verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`coordinates : tuple[float, float, float, float] | list[float] | str, required`**
   - Starting and ending coordinates
   - Used as: input, coords, lon1,lat1,lon2,lat2

2. **`line_color : str, optional`**
   - Line color
   - Either a standard color name or R:G:B triplet
   - Used as: input, color, name

3. **`text_color : str, optional`**
   - Text color
   - Either a standard color name or R:G:B triplet
   - Used as: input, color, name

4. **`units : str, optional`**
   - Units
   - Units
   - Allowed values: meters, kilometers, feet, miles

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

d.geodesic displays a geodesic line in the active frame on the user's
graphics monitor. This is also known as the great circle line and traces
the shortest distance between two user-specified points on the curved
surface of a longitude/latitude data set. The two coordinate locations
named must fall within the boundaries of the user's current geographic
region.

---

## See Also

Related tools:
- [`d.rhumbline`](https://grass.osgeo.org/grass-devel/manuals/d.rhumbline.html)
- [`d.grid`](https://grass.osgeo.org/grass-devel/manuals/d.grid.html)
- [`m.measure`](https://grass.osgeo.org/grass-devel/manuals/m.measure.html)

---

## Resources

- [Official d.geodesic manual](https://grass.osgeo.org/grass-devel/manuals/d.geodesic.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/d.geodesic.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
