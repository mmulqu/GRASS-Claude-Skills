# r.spread

**Category**: raster

## Description

Simulates elliptically anisotropic spread. Generates a raster map of the cumulative time of spread, given raster maps containing the rates of spread (ROS), the ROS directions and the spread origins. It optionally produces raster maps to contain backlink UTM coordinates for tracing spread paths. Usable for fire spread simulations.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_spread(base_ros,max_ros,direction_ros,start,spotting_distance=None,wind_speed=None,fuel_moisture=None,least_size=None,comp_dens=None,init_time="0",lag=None,backdrop=None,output,x_output=None,y_output=None,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`base_ros : str | np.ndarray, required`**
   - Raster map containing base ROS (cm/min)
   - Name of an existing raster map layer in the user's current mapset search path containing the ROS values in the directions perpendicular to maximum ROSes' (cm/minute). These ROSes are also the ones without the effect of directional factors.
   - Used as: input, raster

2. **`max_ros : str | np.ndarray, required`**
   - Raster map containing maximal ROS (cm/min)
   - Name of an existing raster map layer in the user's current mapset search path containing the maximum ROS values (cm/minute).
   - Used as: input, raster

3. **`direction_ros : str | np.ndarray, required`**
   - Raster map containing directions of maximal ROS (degree)
   - Name of an existing raster map layer in the user's current mapset search path containing directions of the maximum ROSes, clockwise from north (degree).
   - Used as: input, raster

4. **`start : str | np.ndarray, required`**
   - Raster map containing starting sources
   - Name of an existing raster map layer in the user's current mapset search path containing starting locations of the spread phenomenon. Any positive integers in this map are recognized as starting sources (seeds).
   - Used as: input, raster

5. **`spotting_distance : str | np.ndarray, optional`**
   - Raster map containing maximal spotting distance (m, required with -s)
   - Name of an existing raster map layer in the user's current mapset search path containing the maximum potential spotting distances (meters).
   - Used as: input, raster

6. **`wind_speed : str | np.ndarray, optional`**
   - Raster map containing midflame wind speed (ft/min, required with -s)
   - Name of an existing raster map layer in the user's current mapset search path containing wind velocities at half of the average flame height (feet/minute).
   - Used as: input, raster

7. **`fuel_moisture : str | np.ndarray, optional`**
   - Raster map containing fine fuel moisture of the cell receiving a spotting firebrand (%, required with -s)
   - Name of an existing raster map layer in the user's current mapset search path containing the 1-hour (<.25") fuel moisture (percentage content multiplied by 100).
   - Used as: input, raster

8. **`least_size : str, optional`**
   - Basic sampling window size needed to meet certain accuracy (3)
   - An odd integer ranging 3 - 15 indicating the basic sampling window size within which all cells will be considered to see whether they will be reached by the current spread cell. The default number is 3 which means a 3x3 window.
   - Used as: odd int

9. **`comp_dens : str, optional`**
   - Sampling density for additional computing (range: 0.0 - 1.0 (0.5))
   - A decimal number ranging 0.0 - 1.0 indicating additional sampling cells will be considered to see whether they will be reached by the current spread cell. The closer to 1.0 the decimal number is, the longer the program will run and the higher the simulation accuracy will be. The default number is 0.5.
   - Used as: decimal

10. **`init_time : str, optional`**
   - Initial time for current simulation (0) (min)
   - A non-negative number specifying the initial time for the current spread simulation (minutes). This is useful when multiple phase simulation is conducted. The default time is 0.
   - Used as: int (>= 0)

11. **`lag : str, optional`**
   - Simulating time duration LAG (fill the region) (min)
   - A non-negative integer specifying the simulating duration time lag (minutes). The default is infinite, but the program will terminate when the current geographic region/mask has been filled. It also controls the computational time, the shorter the time lag, the faster the program will run.
   - Used as: int (>= 0)

12. **`backdrop : str | np.ndarray, optional`**
   - Name of raster map as a display backdrop
   - Name of an existing raster map layer in the user's current mapset search path to be used as the background on which the "live" movement will be shown.
   - Used as: input, raster

13. **`output : str | type(np.ndarray) | type(np.array) | type(gs.array.array), required`**
   - Raster map to contain output spread time (min)
   - Name of the new raster map layer to contain the results of the cumulative spread time needed for a phenomenon to reach each cell from the starting sources (minutes).
   - Used as: output, raster

14. **`x_output : str | type(np.ndarray) | type(np.array) | type(gs.array.array), optional`**
   - Name of raster map to contain X back coordinates
   - Name of the new raster map layer to contain the results of backlink information in UTM easting coordinates for each cell.
   - Used as: output, raster

15. **`y_output : str | type(np.ndarray) | type(np.array) | type(gs.array.array), optional`**
   - Name of raster map to contain Y back coordinates
   - Name of the new raster map layer to contain the results of backlink information in UTM northing coordinates for each cell.
   - Used as: output, raster

16. **`flags : str, optional`**
   - Allowed values: s, i
   - s
   - Consider spotting effect (for wildfires)
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/r.spread.html#__tabbed_2_3) for all details)*

17. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

18. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

19. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

20. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 20 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/r.spread.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | np.ndarray | tuple[np.ndarray] | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned. If an array type (e.g., np.ndarray) is used for one of the raster outputs, the result will be an array and will have the shape corresponding to the computational region. If an array type is used for more than one raster output, the result will be a tuple of arrays.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

r.spread is part of the wildfire simulation toolset. Preparational
steps for the fire simulation are the calculation of the rate of spread
(ROS) with r.ros , and the creating of spread map with r.spread .
Eventually, the fire path(s) based on starting point(s) are calculated
with r.spreadpath .

Spread phenomena usually show uneven movement over space. Such
unevenness is due to two reasons:

The anisotropy of spread occurs when any of the determining factors have
directional components. For example, wind and topography cause
anisotropic spread of wildfires.

One of the simplest spatial heterogeneous and anisotropic spread is
elliptical spread, in which, each local spread shape can be thought as
an ellipse. In a raster setting, cell centers are foci of the spread
ellipses, and the spread phenomenon moves fastest toward apogees and
slowest to perigees. The sizes and shapes of spread ellipses may vary
cell by cell. So the overall spread shape is commonly not an ellipse.

r.spread simulates elliptically anisotropic spread phenomena, given
three raster map layers about ROS (base ROS, maximum ROS and direction
of the maximum ROS) plus a raster map layer showing the starting
sources. These ROS layers define unique ellipses for all cell locations
in the current computational region as if each cell center was a
potential spread origin. For some wildfire spread, these ROS layers can
be generated by another GRASS raster program r.ros. The actual locations
reached by a spread event are constrained by the actual spread origins
and the elapsed spread time.

r.spread optionally produces raster maps to contain backlink UTM
coordinates for each raster cell of the spread time map. The spread
paths can be accurately traced based on the backlink information by r.spreadpath module.

Part of the spotting function in r.spread is based on Chase (1984) and
Rothermel (1983). More information on r.spread , r.ros and r.spreadpath can be found in Xu (1994).

Options spot_dist , w_speed and f_mois must all be given if the -s (spotting) flag is used.

---

## See Also

Related tools:
- [`r.cost`](https://grass.osgeo.org/grass-devel/manuals/r.cost.html)
- [`r.mask`](https://grass.osgeo.org/grass-devel/manuals/r.mask.html)
- [`r.ros`](https://grass.osgeo.org/grass-devel/manuals/r.ros.html)
- [`r.spreadpath`](https://grass.osgeo.org/grass-devel/manuals/r.spreadpath.html)

---

## Authors

Jianping Xu and Richard G. Lathrop, Jr., Center for Remote Sensing and
Spatial Analysis, Rutgers University.

---

## Resources

- [Official r.spread manual](https://grass.osgeo.org/grass-devel/manuals/r.spread.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.spread.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
