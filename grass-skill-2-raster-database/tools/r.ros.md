# r.ros

**Category**: raster

## Description

Generates rate of spread raster maps. Generates three, or four raster map layers showing the base (perpendicular) rate of spread (ROS), the maximum (forward) ROS, the direction of the maximum ROS, and optionally the maximum potential spotting distance for fire spread simulation.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_ros(model,moisture_1h=None,moisture_10h=None,moisture_100h=None,moisture_live,velocity=None,direction=None,slope=None,aspect=None,elevation=None,base_ros,max_ros,direction_ros,spotting_distance=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`model : str | np.ndarray, required`**
   - Raster map containing fuel models
   - Name of an existing raster map layer in the user's current mapset search path containing the standard fuel models defined by the USDA Forest Service. Valid values are 1-13; other numbers are recognized as barriers by r.ros.
   - Used as: input, raster, name

2. **`moisture_1h : str | np.ndarray, optional`**
   - Raster map containing the 1-hour fuel moisture (%)
   - Name of an existing raster map layer in the user's current mapset search path containing the 1-hour (<.25") fuel moisture (percentage content multiplied by 100).
   - Used as: input, raster, name

3. **`moisture_10h : str | np.ndarray, optional`**
   - Raster map containing the 10-hour fuel moisture (%)
   - Name of an existing raster map layer in the user's current mapset search path containing the 10-hour (.25-1") fuel moisture (percentage content multiplied by 100).
   - Used as: input, raster, name

4. **`moisture_100h : str | np.ndarray, optional`**
   - Raster map containing the 100-hour fuel moisture (%)
   - Name of an existing raster map layer in the user's current mapset search path containing the 100-hour (1-3") fuel moisture (percentage content multiplied by 100).
   - Used as: input, raster, name

5. **`moisture_live : str | np.ndarray, required`**
   - Raster map containing live fuel moisture (%)
   - Name of an existing raster map layer in the user's current mapset search path containing live (herbaceous) fuel moisture (percentage content multiplied by 100).
   - Used as: input, raster, name

6. **`velocity : str | np.ndarray, optional`**
   - Raster map containing midflame wind velocities (ft/min)
   - Name of an existing raster map layer in the user's current mapset search path containing wind velocities at half of the average flame height (feet/minute).
   - Used as: input, raster, name

7. **`direction : str | np.ndarray, optional`**
   - Name of raster map containing wind directions (degree)
   - Name of an existing raster map layer in the user's current mapset search path containing wind direction, clockwise from north (degree).
   - Used as: input, raster, name

8. **`slope : str | np.ndarray, optional`**
   - Name of raster map containing slope (degree)
   - Name of an existing raster map layer in the user's current mapset search path containing topographic slope (degree).
   - Used as: input, raster, name

9. **`aspect : str | np.ndarray, optional`**
   - Raster map containing aspect (degree, CCW from E)
   - Name of an existing raster map layer in the user's current mapset search path containing topographic aspect, counterclockwise from east (GRASS convention) in degrees.
   - Used as: input, raster, name

10. **`elevation : str | np.ndarray, optional`**
   - Raster map containing elevation (m, required for spotting)
   - Name of an existing raster map layer in the user's current mapset search path containing elevation (meters). Option is required from spotting distance computation (when spotting_distance option is provided)
   - Used as: input, raster, name

11. **`base_ros : str | type(np.ndarray) | type(np.array) | type(gs.array.array), required`**
   - Output raster map containing base ROS (cm/min)
   - Base (perpendicular) rate of spread (ROS)
   - Used as: output, raster, name

12. **`max_ros : str | type(np.ndarray) | type(np.array) | type(gs.array.array), required`**
   - Output raster map containing maximal ROS (cm/min)
   - The maximum (forward) rate of spread (ROS)
   - Used as: output, raster, name

13. **`direction_ros : str | type(np.ndarray) | type(np.array) | type(gs.array.array), required`**
   - Output raster map containing directions of maximal ROS (degree)
   - The direction of the maximal (forward) rate of spread (ROS)
   - Used as: output, raster, name

14. **`spotting_distance : str | type(np.ndarray) | type(np.array) | type(gs.array.array), optional`**
   - Output raster map containing maximal spotting distance (m)
   - The maximal potential spotting distance (requires elevation raster map to be provided).
   - Used as: output, raster, name

15. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

16. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

17. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

18. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 18 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/r.ros.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | np.ndarray | tuple[np.ndarray] | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned. If an array type (e.g., np.ndarray) is used for one of the raster outputs, the result will be an array and will have the shape corresponding to the computational region. If an array type is used for more than one raster output, the result will be a tuple of arrays.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

r.ros is part of the wildfire simulation toolset. Preparational steps
for the fire simulation are the calculation of the rate of spread (ROS)
with r.ros , and the creating of spread map with r.spread .
Eventually, the fire path(s) based on starting point(s) are calculated
with r.spreadpath .

r.ros is used for fire (wildfire) modeling. The input is fuel model
and moisture and the outputs are rate of spread (ROS) values. The module
generates the base ROS value, maximum ROS value, direction of the
maximum ROS, and optionally the maximum potential spotting distance of
wildfire for each raster cell in the current geographic region. These
three or four raster map layers serve as inputs for the r.spread module which is the next step in fire
simulation.

The r.ros module and two related modules r.spread ,
and r.spreadpath can be used not only for wildfire
modeling but also generally to simulate other events where spread of
something is involved and elliptical spread is appropriate.

The calculation of the two ROS values for each raster cell is based on
the Fortran code by Pat Andrews (1983) of the Northern Forest Fire
Laboratory, USDA Forest Service. The direction of the maximum ROS
results from the vector addition of the forward ROS in wind direction
and that in upslope direction. The spotting distance, if required, will
be calculated by a separate function, spot_dist(), which is based on
Lathrop and Xu (in preparation), Chase (1984) and Rothermel (1991). More
information on r.ros and r.spread can be found in Xu
(1994).

The output parameter is a basename (prefix) for all generated raster
maps and each map gets a unique suffix:

So, if the output parameter is blackforest_ros , r.ros creates blackforest_ros.base , blackforest_ros.max , blackforest_ros.maxdir ,
and (optionally) blackforest_ros.spotdist raster maps.

If only one or two of the options moisture_1h , moisture_10h , and moisture_100h are given, the module will assign values to the
missing option using the formula:

However, at least one of them should be given.

Options velocity and direction must be both given or both
omitted. If none is given, the module will assume a no-wind condition.

Options slope and aspect must be also given together. If none is
given, the module will assume a topographically flat condition. Option elevation must be given if -s (spotting) flag is used.

---

## See Also

Related tools:
- [`g.region`](https://grass.osgeo.org/grass-devel/manuals/g.region.html)
- [`r.slope.aspect`](https://grass.osgeo.org/grass-devel/manuals/r.slope.aspect.html)
- [`r.spread`](https://grass.osgeo.org/grass-devel/manuals/r.spread.html)
- [`r.spreadpath`](https://grass.osgeo.org/grass-devel/manuals/r.spreadpath.html)

---

## Resources

- [Official r.ros manual](https://grass.osgeo.org/grass-devel/manuals/r.ros.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.ros.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
