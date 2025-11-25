# d.polar

**Category**: display

## Description

Draws polar diagram of angle map such as aspect or flow directions

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.d_polar(map,undef=None,output=None,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`map : str | np.ndarray, required`**
   - Name of raster angle map
   - Used as: input, raster, name

2. **`undef : float, optional`**
   - Pixel value to be interpreted as undefined (different from NULL)

3. **`output : str, optional`**
   - Name for optional EPS output file
   - Used as: output, file, name

4. **`flags : str, optional`**
   - Allowed values: x
   - x
   - Plot using Xgraph

5. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

6. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

7. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

8. **`superquiet : bool, optional`**
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

d.polar calculates and displays a polar diagram of an angle raster map
such as aspect, wind direction, or flow. The input angle map orientation
must be counter-clockwise (CCW) from east, and the angle map units must
be degrees. This refers to the standard orientation of GRASS (e.g., see r.slope.aspect ).

The radius of the outer circle is defined by the total number of pixels
in the map. If the polar diagram does not reach the outer circle, no
data (NULL) pixels were found in the map.

The vector in the diagram indicates a prevailing direction, its length
the strength of such direction. In case all angle vectors are oriented
along the same direction, the length for the vector is maximal (in fact
it is equal to length of the most populated bin of the underlying
histogram).

As a side effect, the quality of the angle map can be derived from the
diagram. Strong spikes may indicate an over-representation of the
related angle(s) which happens in particular if integer maps are used.

---

## See Also

Related tools:
- [`d.graph`](https://grass.osgeo.org/grass-devel/manuals/d.graph.html)
- [`d.histogram`](https://grass.osgeo.org/grass-devel/manuals/d.histogram.html)
- [`d.rast.arrow`](https://grass.osgeo.org/grass-devel/manuals/d.rast.arrow.html)
- [`r.slope.aspect`](https://grass.osgeo.org/grass-devel/manuals/r.slope.aspect.html)

---

## Authors

Markus Neteler, ITC-irst, Italy Bruno Caprile, ITC-irst, Italy Hamish Bowman, Otago University, New Zealand

---

## Resources

- [Official d.polar manual](https://grass.osgeo.org/grass-devel/manuals/d.polar.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/d.polar.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
