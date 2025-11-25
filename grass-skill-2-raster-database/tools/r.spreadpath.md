# r.spreadpath

**Category**: raster

## Description

Recursively traces the least cost path backwards to cells from which the cumulative cost was determined.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_spreadpath(x_input,y_input,coordinates=None,output,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`x_input : str | np.ndarray, required`**
   - Name of raster map containing back-path easting information
   - Used as: input, raster, name

2. **`y_input : str | np.ndarray, required`**
   - Name of raster map containing back-path northing information
   - Used as: input, raster, name

3. **`coordinates : list[tuple[float, float]] | tuple[float, float] | list[float] | str, optional`**
   - The map E and N grid coordinates of starting points
   - Used as: input, coords, east,north

4. **`output : str | type(np.ndarray) | type(np.array) | type(gs.array.array), required`**
   - Name for output raster map
   - Used as: output, raster, name

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

result : grass.tools.support.ToolResult | np.ndarray | tuple[np.ndarray] | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned. If an array type (e.g., np.ndarray) is used for one of the raster outputs, the result will be an array and will have the shape corresponding to the computational region. If an array type is used for more than one raster output, the result will be a tuple of arrays.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

r.spreadpath is part of the wildfire simulation toolset. Preparational
steps for the fire simulation are the calculation of the rate of spread
(ROS) with r.ros , and the creating of spread map with r.spread .
Eventually, the fire path(s) based on starting point(s) are calculated
with r.spreadpath .

r.spreadpath recursively traces the least cost path backwards to the
origin, given backlink information input map layers and target locations
from where paths are to be traced. The backlink information map layers
record each cell's backlink UTM northing (the y_input) and easting (the
x_input) coordinates from which the cell's cumulative cost was
determined.

The backlink inputs can be generated from another GRASS raster program r.spread . One of the major applications of r.spreadpath along with r.spread is to accurately find the least cost corridors and/or paths
on a raster setting. More information on r.spread and r.spreadpath can be found in Xu (1994).

---

## See Also

Related tools:
- [`r.spread`](https://grass.osgeo.org/grass-devel/manuals/r.spread.html)
- [`r.ros`](https://grass.osgeo.org/grass-devel/manuals/r.ros.html)

---

## Authors

Jianping Xu and Richard G. Lathrop, Jr., Center for Remote Sensing and
Spatial Analysis, Rutgers University.

---

## Resources

- [Official r.spreadpath manual](https://grass.osgeo.org/grass-devel/manuals/r.spreadpath.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.spreadpath.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
