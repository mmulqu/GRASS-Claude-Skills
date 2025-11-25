# r.sunhours

**Category**: raster

## Description

Calculates solar elevation, solar azimuth, and sun hours. Solar elevation: the angle between the direction of the geometric center of the sun's apparent disk and the (idealized) horizon. Solar azimuth: the angle from due north in clockwise direction.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_sunhours(elevation=None,azimuth=None,sunhour=None,year,month=None,day,hour=12,minute=0,second=0,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`elevation : str | type(np.ndarray) | type(np.array) | type(gs.array.array), optional`**
   - Output raster map with solar elevation angle
   - Name for output raster map
   - Used as: output, raster, name

2. **`azimuth : str | type(np.ndarray) | type(np.array) | type(gs.array.array), optional`**
   - Output raster map with solar azimuth angle
   - Name for output raster map
   - Used as: output, raster, name

3. **`sunhour : str | type(np.ndarray) | type(np.array) | type(gs.array.array), optional`**
   - Output raster map with sunshine hours
   - Sunshine hours require SOLPOS use and Greenwich standard time
   - Used as: output, raster, name

4. **`year : int, required`**
   - Year
   - Allowed values: 1950-2050

5. **`month : int, optional`**
   - Month
   - If not given, day is interpreted as day of the year
   - Allowed values: 1-12

6. **`day : int, required`**
   - Day
   - Allowed values: 1-366

7. **`hour : int, optional`**
   - Hour
   - Allowed values: 0-24
   - Default: 12

8. **`minute : int, optional`**
   - Minutes
   - Allowed values: 0-60
   - Default: 0

9. **`second : int, optional`**
   - Seconds
   - Allowed values: 0-60
   - Default: 0

10. **`flags : str, optional`**
   - Allowed values: t, s
   - t
   - Time is local sidereal time, not Greenwich standard time
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/r.sunhours.html#__tabbed_2_3) for all details)*

11. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

12. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

13. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

14. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 14 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/r.sunhours.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | np.ndarray | tuple[np.ndarray] | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned. If an array type (e.g., np.ndarray) is used for one of the raster outputs, the result will be an array and will have the shape corresponding to the computational region. If an array type is used for more than one raster output, the result will be a tuple of arrays.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

r.sunhours calculates sun elevation and sun azimuth angles for the
given time of day and each grid cell in the current region.
Additionally, the photoperiod (sunshine hours on flat terrain) can be
calculated.

Sun elevation, height, height angle, or solar altitude angle is the
angle in degrees between the horizon and a line that points from the
site towards the centre of the sun.

The sun azimuth angle is here defined as the azimuth angle in degrees of
the sun from due north in a clockwise direction.

The time used here is defined such that 12:00 (high noon) is the time
when the sun has reached its highest point in the sky at the current
site, unless the -t flag is used in which case time is interpreted as
Greenwich standard time.

If a sunhour output map is specified, the module calculates sunshine
hours for the given day. This option requires both Greenwhich standard
time and the use of the SOLPOS algorithm by NREL.

---

## See Also

Related tools:
- [`g.region`](https://grass.osgeo.org/grass-devel/manuals/g.region.html)
- [`r.sun`](https://grass.osgeo.org/grass-devel/manuals/r.sun.html)
- [`r.sunmask`](https://grass.osgeo.org/grass-devel/manuals/r.sunmask.html)

---

## Resources

- [Official r.sunhours manual](https://grass.osgeo.org/grass-devel/manuals/r.sunhours.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.sunhours.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
