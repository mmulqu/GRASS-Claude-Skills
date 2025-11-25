# r.viewshed

**Category**: raster

## Description

Computes the viewshed of a point on an elevation raster map. Default format: NULL (invisible), vertical angle wrt viewpoint (visible).

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_viewshed(input,output,coordinates,observer_elevation=1.75,target_elevation=0.0,max_distance=-1,direction_range=None,refraction_coeff=0.14286,memory=500,directory=None,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str | np.ndarray, required`**
   - Name of input elevation raster map
   - Used as: input, raster, name

2. **`output : str | type(np.ndarray) | type(np.array) | type(gs.array.array), required`**
   - Name for output raster map
   - Used as: output, raster, name

3. **`coordinates : tuple[float, float] | list[float] | str, required`**
   - Coordinates of viewing position
   - Used as: input, coords, east,north

4. **`observer_elevation : float, optional`**
   - Viewing elevation above the ground
   - Used as: value
   - Default: 1.75

5. **`target_elevation : float, optional`**
   - Offset for target elevation above the ground
   - Used as: value
   - Default: 0.0

6. **`max_distance : float, optional`**
   - Maximum visibility radius. By default infinity (-1)
   - Used as: value
   - Default: -1

7. **`direction_range : tuple[float, float] | list[float] | str, optional`**
   - Minimum and maximum horizontal angle limiting viewshed (0 is East, counterclockwise)
   - Used as: min,max
   - Allowed values: 0-360

8. **`refraction_coeff : float, optional`**
   - Refraction coefficient
   - Allowed values: 0.0-1.0
   - Default: 0.14286

9. **`memory : int, optional`**
   - Amount of memory to use in MB
   - Used as: value
   - Default: 500

10. **`directory : str, optional`**
   - Directory to hold temporary files (they can be large)

11. **`flags : str, optional`**
   - Allowed values: c, r, b, e
   - c
   - Consider the curvature of the earth (current ellipsoid)
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/r.viewshed.html#__tabbed_2_3) for all details)*

12. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

13. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

14. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

15. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 15 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/r.viewshed.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | np.ndarray | tuple[np.ndarray] | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned. If an array type (e.g., np.ndarray) is used for one of the raster outputs, the result will be an array and will have the shape corresponding to the computational region. If an array type is used for more than one raster output, the result will be a tuple of arrays.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

r.viewshed is a module that computes the viewshed of a point on a
raster terrain. That is, given an elevation raster, and the location of
an observer, it generates a raster output map showing which cells are
visible from the given location. The algorithm underlying r.viewshed minimizes both the CPU operations and the transfer of data between main
memory and disk; as a result r.viewshed runs fast on very large
rasters.

---

## See Also

Related tools:
- [`r.mapcalc`](https://grass.osgeo.org/grass-devel/manuals/r.mapcalc.html)

---

## Authors

Laura Toma (Bowdoin College): ltoma@bowdoin.edu
Yi Zhuang (Carnegie-Mellon University): yzhuang@andrew.cmu.edu
William Richard (Bowdoin College): willster3021@gmail.com
Markus Metz

---

## Resources

- [Official r.viewshed manual](https://grass.osgeo.org/grass-devel/manuals/r.viewshed.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.viewshed.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
