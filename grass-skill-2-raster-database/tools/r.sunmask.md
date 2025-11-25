# r.sunmask

**Category**: raster

## Description

Calculates cast shadow areas from sun position and elevation raster map. Either exact sun position (A) is specified, or date/time to calculate the sun position (B) by r.sunmask itself.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_sunmask(elevation,output=None,altitude=None,azimuth=None,year=None,month=None,day=None,hour=None,minute=None,second=0,timezone=None,east=None,north=None,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`elevation : str | np.ndarray, required`**
   - Name of input elevation raster map
   - Used as: input, raster, name

2. **`output : str | type(np.ndarray) | type(np.array) | type(gs.array.array), optional`**
   - Name for output raster map
   - Used as: output, raster, name

3. **`altitude : float, optional`**
   - Altitude of the sun in degrees above the horizon (A)
   - Allowed values: 0-89.999

4. **`azimuth : float, optional`**
   - Azimuth of the sun in degrees from north (A)
   - Allowed values: 0-360

5. **`year : int, optional`**
   - Year (B)
   - Allowed values: 1950-2050

6. **`month : int, optional`**
   - Month (B)
   - Allowed values: 0-12

7. **`day : int, optional`**
   - Day (B)
   - Allowed values: 0-31

8. **`hour : int, optional`**
   - Hour (B)
   - Allowed values: 0-24

9. **`minute : int, optional`**
   - Minutes (B)
   - Allowed values: 0-60

10. **`second : int, optional`**
   - Seconds (B)
   - Allowed values: 0-60
   - Default: 0

11. **`timezone : int, optional`**
   - Timezone
   - East positive, offset from GMT, also use to adjust daylight savings

12. **`east : str, optional`**
   - Easting coordinate (point of interest)
   - Default: map center
   - Used as: value

13. **`north : str, optional`**
   - Northing coordinate (point of interest)
   - Default: map center
   - Used as: value

14. **`flags : str, optional`**
   - Allowed values: z, s, g
   - z
   - Do not ignore zero elevation
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/r.sunmask.html#__tabbed_2_3) for all details)*

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


*Showing 10 of 18 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/r.sunmask.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | np.ndarray | tuple[np.ndarray] | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned. If an array type (e.g., np.ndarray) is used for one of the raster outputs, the result will be an array and will have the shape corresponding to the computational region. If an array type is used for more than one raster output, the result will be a tuple of arrays.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

r.sunmask creates an output map layer based on an input elevation
raster map layer and the position of the sun. The output map layer
contains the cast shadow areas resulting from sunlight and elevation.
The user can either specify the sun position directly or the module
calculates it from given location and date/time parameters using the
SOLPOS (Solar and Moon Position Algorithm) developed by the National
Renewable Energy Laboratory (NREL). SOLPOS
operates in two modes, either

must be used.

The module performs sunset/sunrise checks and refraction correction for
sun position calculation. Local coordinate systems are internally
transformed to latitude/longitude for the SOLPOS algorithm. Elevation is
not taken into account for sunset/sunrise calculations.

The solar zenith angle ("sun angle above horizon") is defined as the
angle between the horizon and the vertical (directly overhead or
zenith). Its values can range from 90°, when the sun is directly
overhead, to 0°, when the sun is on the horizon. Values lower than 0°
indicate that the sun is below the horizon.

The solar azimuth angle ("sun azimuth") defines the direction of the
sun. It is the angle between north and the projection of the sun's rays
onto the horizontal plane. This angle is measured in a clockwise
direction and can vary between 0° and 360°. Specifically, an azimuth of
0° means the sun is in the north, 90° in the east, 180° in the south and
270° in the west.

---

## See Also

Related tools:
- [`g.region`](https://grass.osgeo.org/grass-devel/manuals/g.region.html)
- [`r.sun`](https://grass.osgeo.org/grass-devel/manuals/r.sun.html)
- [`r.sunhours`](https://grass.osgeo.org/grass-devel/manuals/r.sunhours.html)
- [`r.slope.aspect`](https://grass.osgeo.org/grass-devel/manuals/r.slope.aspect.html)

---

## Authors

Janne Soimasuo, Finland, 1994 update to FP by Huidae Cho, 2001 SOLPOS algorithm feature added by Markus Neteler, 2001

---

## Resources

- [Official r.sunmask manual](https://grass.osgeo.org/grass-devel/manuals/r.sunmask.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.sunmask.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
