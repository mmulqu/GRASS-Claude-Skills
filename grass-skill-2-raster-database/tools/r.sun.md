# r.sun

**Category**: raster

## Description

Solar irradiance and irradiation model. Computes direct (beam), diffuse and reflected solar irradiation raster maps for given day, latitude, surface and atmospheric conditions. Solar parameters (e.g. sunrise, sunset times, declination, extraterrestrial irradiance, daylight length) are saved in the map history file. Alternatively, a local time can be specified to compute solar incidence angle and/or irradiance raster maps. The shadowing effect of the topography is optionally incorporated.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_sun(elevation,aspect=None,aspect_value=270,slope=None,slope_value=0.0,linke=None,linke_value=3.0,albedo=None,albedo_value=0.2,lat=None,long=None,coeff_bh=None,coeff_dh=None,horizon_basename=None,horizon_step=None,incidout=None,beam_rad=None,diff_rad=None,refl_rad=None,glob_rad=None,insol_time=None,day,step=0.5,declination=None,solar_constant=1367,time=None,nprocs=1,distance_step=1.0,npartitions=1,civil_time=None,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`elevation : str | np.ndarray, required`**
   - Name of the input elevation raster map [meters]
   - Used as: input, raster

2. **`aspect : str | np.ndarray, optional`**
   - Name of the input aspect map (terrain aspect or azimuth of the solar panel) [decimal degrees]
   - Used as: input, raster

3. **`aspect_value : float, optional`**
   - A single value of the orientation (aspect), 270 is south
   - Default: 270

4. **`slope : str | np.ndarray, optional`**
   - Name of the input slope raster map (terrain slope or solar panel inclination) [decimal degrees]
   - Used as: input, raster

5. **`slope_value : float, optional`**
   - A single value of inclination (slope)
   - Default: 0.0

6. **`linke : str | np.ndarray, optional`**
   - Name of the Linke atmospheric turbidity coefficient input raster map [-]
   - Used as: input, raster

7. **`linke_value : float, optional`**
   - A single value of the Linke atmospheric turbidity coefficient [-]
   - Default: 3.0

8. **`albedo : str | np.ndarray, optional`**
   - Name of the ground albedo coefficient input raster map [-]
   - Used as: input, raster

9. **`albedo_value : float, optional`**
   - A single value of the ground albedo coefficient [-]
   - Default: 0.2

10. **`lat : str | np.ndarray, optional`**
   - Name of input raster map containing latitudes [decimal degrees]
   - Used as: input, raster

11. **`long : str | np.ndarray, optional`**
   - Name of input raster map containing longitudes [decimal degrees]
   - Used as: input, raster

12. **`coeff_bh : str | np.ndarray, optional`**
   - Name of real-sky beam radiation coefficient (thick cloud) input raster map [0-1]
   - Used as: input, raster

13. **`coeff_dh : str | np.ndarray, optional`**
   - Name of real-sky diffuse radiation coefficient (haze) input raster map [0-1]
   - Used as: input, raster

14. **`horizon_basename : str | np.ndarray, optional`**
   - The horizon information input map basename
   - Used as: input, raster, basename

15. **`horizon_step : float, optional`**
   - Angle step size for multidirectional horizon [degrees]

16. **`incidout : str | type(np.ndarray) | type(np.array) | type(gs.array.array), optional`**
   - Output incidence angle raster map (mode 1 only)
   - Used as: output, raster

17. **`beam_rad : str | type(np.ndarray) | type(np.array) | type(gs.array.array), optional`**
   - Output beam irradiance [W.m-2] (mode 1) or irradiation raster map [Wh.m-2.day-1] (mode 2)
   - Used as: output, raster

18. **`diff_rad : str | type(np.ndarray) | type(np.array) | type(gs.array.array), optional`**
   - Output diffuse irradiance [W.m-2] (mode 1) or irradiation raster map [Wh.m-2.day-1] (mode 2)
   - Used as: output, raster

19. **`refl_rad : str | type(np.ndarray) | type(np.array) | type(gs.array.array), optional`**
   - Output ground reflected irradiance [W.m-2] (mode 1) or irradiation raster map [Wh.m-2.day-1] (mode 2)
   - Used as: output, raster

20. **`glob_rad : str | type(np.ndarray) | type(np.array) | type(gs.array.array), optional`**
   - Output global (total) irradiance/irradiation [W.m-2] (mode 1) or irradiance/irradiation raster map [Wh.m-2.day-1] (mode 2)
   - Used as: output, raster

21. **`insol_time : str | type(np.ndarray) | type(np.array) | type(gs.array.array), optional`**
   - Output insolation time raster map [h] (mode 2 only)
   - Used as: output, raster

22. **`day : int, required`**
   - No. of day of the year (1-365)
   - Allowed values: 1-365

23. **`step : float, optional`**
   - Time step when computing all-day radiation sums [decimal hours]
   - Default: 0.5

24. **`declination : float, optional`**
   - Declination value (overriding the internally computed value) [radians]

25. **`solar_constant : float, optional`**
   - Solar constant [W/m^2]
   - Default: 1367

26. **`time : float, optional`**
   - Local (solar) time (to be set for mode 1 only) [decimal hours]
   - Allowed values: 0-24

27. **`nprocs : int, optional`**
   - Number of threads which will be used for parallel computing
   - Allowed values: 1-1000
   - Default: 1

28. **`distance_step : float, optional`**
   - Sampling distance step coefficient (0.5-1.5)
   - Default: 1.0

29. **`npartitions : int, optional`**
   - Read the input files in this number of chunks
   - Default: 1

30. **`civil_time : float, optional`**
   - Civil time zone value, if none, the time will be local solar time

31. **`flags : str, optional`**
   - Allowed values: p, m
   - p
   - Do not incorporate the shadowing effect of terrain
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/r.sun.html#__tabbed_2_3) for all details)*

32. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

33. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

34. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

35. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 35 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/r.sun.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | np.ndarray | tuple[np.ndarray] | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned. If an array type (e.g., np.ndarray) is used for one of the raster outputs, the result will be an array and will have the shape corresponding to the computational region. If an array type is used for more than one raster output, the result will be a tuple of arrays.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

r.sun computes beam (direct), diffuse and ground reflected solar
irradiation raster maps for given day, latitude, surface and atmospheric
conditions. Solar parameters (e.g. time of sunrise and sunset,
declination, extraterrestrial irradiance, daylight length) are stored in
the resultant maps' history files. Alternatively, the local time can be
specified to compute solar incidence angle and/or irradiance raster
maps. The shadowing effect of the topography is incorporated by default.
This can be done either internally by calculation of the shadowing
effect directly from the digital elevation model or by specifying raster
maps of the horizon height which is much faster. These horizon raster
maps can be calculated using r.horizon .

For latitude-longitude coordinates it requires that the elevation map is
in meters. The rules are:

The solar geometry of the model is based on the works of Krcho (1990),
later improved by Jenco (1992). The equations describing Sun -- Earth
position as well as an interaction of the solar radiation with
atmosphere were originally based on the formulas suggested by Kitler and
Mikler (1986). This component was considerably updated by the results
and suggestions of the working group co-ordinated by Scharmer and Greif
(2000) (this algorithm might be replaced by SOLPOS algorithm-library
included in GRASS within r.sunmask command). The model
computes all three components of global radiation (beam, diffuse and
reflected) for the clear sky conditions, i.e. not taking into
consideration the spatial and temporal variation of clouds. The extent
and spatial resolution of the modelled area, as well as integration over
time, are limited only by the memory and data storage resources. The
model is built to fulfil user needs in various fields of science
(hydrology, climatology, ecology and environmental sciences,
photovoltaics, engineering, etc.) for continental, regional up to the
landscape scales.

The model considers a shadowing effect of the local topography unless
switched off with the -p flag. r.sun works in two modes: In the
first mode it calculates for the set local time a solar incidence angle
[degrees] and solar irradiance values [W.m-2]. In the second mode
daily sums of solar radiation [Wh.m-2.day-1] are computed within a set
day. By a scripting the two modes can be used separately or in a
combination to provide estimates for any desired time interval. The
model accounts for sky obstruction by local relief features. Several
solar parameters are saved in the resultant maps' history files, which
may be viewed with the r.info command.

The solar incidence angle raster map incidout is computed specifying
elevation raster map elevation , aspect raster map aspect , slope
steepness raster map slope, given the day day and local time time .
There is no need to define latitude for projects with known and defined
coordinate system (check it with the g.proj command). If
you have undefined projection, (x,y) system, etc. then the latitude can
be defined explicitly for large areas by input raster map lat_in with
interpolated latitude values. All input raster maps must be floating
point (FCELL) raster maps. Null data in maps are excluded from the
computation (and also speeding-up the computation), so each output
raster map will contain null data in cells according to all input raster
maps. The user can use r.null command to create/reset null
file for your input raster maps. The specified day day is the number of the day of the general year
where January 1 is day no.1 and December 31 is 365. Time time must be
a local (solar) time (i.e. NOT a zone time, e.g. GMT, CET) in decimal
system, e.g. 7.5 (= 7h 30m A.M.), 16.1 = 4h 6m P.M..

The solar declination parameter is an option to override the value
computed by the internal routine for the day of the year. The value of
geographical latitude can be set as a constant for the whole computed
region or, as an option, a grid representing spatially distributed
values over a large region. The geographical latitude must be also in
decimal system with positive values for northern hemisphere and negative
for southern one. In similar principle the Linke turbidity factor
( linke , lin ) and ground albedo ( albedo , alb ) can be set.

Besides clear-sky radiations, the user can compute a real-sky radiation
(beam, diffuse) using coeff_bh and coeff_dh input raster maps
defining the fraction of the respective clear-sky radiations reduced by
atmospheric factors (e.g. cloudiness). The value is between 0-1. Usually
these coefficients can be obtained from a long-terms meteorological
measurements provided as raster maps with spatial distribution of these
coefficients separately for beam and diffuse radiation (see Suri and
Hofierka, 2004, section 3.2).

The solar irradiation or irradiance raster maps beam_rad , diff_rad , refl_rad are computed for a given day day, latitude lat_in ,
elevation elevation , slope slope and aspect aspect raster maps.
For convenience, the output raster given as glob_rad will output the
sum of the three radiation components. The program uses the Linke
atmosphere turbidity factor and ground albedo coefficient. A default,
single value of Linke factor is lin =3.0 and is near the annual average
for rural-city areas. The Linke factor for an absolutely clear
atmosphere is lin =1.0. See notes below to learn more about this
factor. The incidence solar angle is the angle between horizon and solar
beam vector.

The solar radiation maps for a given day are computed by integrating the
relevant irradiance between sunrise and sunset times for that day. The
user can set a finer or coarser time step used for all-day radiation
calculations with the step option. The default value of step is 0.5
hour. Larger steps (e.g. 1.0-2.0) can speed-up calculations but produce
less reliable (and more jagged) results. As the sun moves through
approx. 15° of the sky in an hour, the default step of half an hour
will produce 7.5° steps in the data. For relatively smooth output with
the sun placed for every degree of movement in the sky you should set
the step to 4 minutes or less. step =0.05 is equivalent to every 3
minutes. Of course setting the time step to be very fine proportionally
increases the module's running time.

The output units are in Wh per squared meter per given day
[Wh/(m*m)/day]. The incidence angle and irradiance/irradiation maps
are computed with the shadowing influence of relief by default. It is
also possible for them to be computed without this influence using the
planar flag ( -p ). In mountainous areas this can lead to very different
results! The user should be aware that taking into account the shadowing
effect of relief can slow down the speed of computation, especially when
the sun altitude is low.

When considering the shadowing effect, speed and precision of
computation can be controlled by the distance_step parameter, which
defines the sampling density at which the visibility of a grid cell is
computed in the direction of a path of the solar flow. It also defines
the method by which the obstacle's altitude is computed. When choosing a distance_step less than 1.0 (i.e. sampling points will be computed at distance_step * cellsize distance), r.sun takes the altitude from
the nearest grid point. Values above 1.0 will use the maximum altitude
value found in the nearest 4 surrounding grid points. The default value distance_step =1.0 should give reasonable results for most cases (e.g.
on DEM). The distance_step value defines a multiplying coefficient for
sampling distance. This basic sampling distance equals to the arithmetic
average of both cell sizes. The reasonable values are in the range
0.5-1.5. The values below 0.5 will decrease and values above 1.0 will
increase the computing speed. Values greater than 2.0 may produce
estimates with lower accuracy in highly dissected relief. The fully
shadowed areas are written to the output maps as zero values. Areas with
NULL data are considered as no barrier with shadowing effect.

The maps' history files are generated containing the following listed
parameters used in the computation:

The user can use a nice shellcript with variable day to compute
radiation for some time interval within the year (e.g. vegetation or
winter period). Elevation, aspect and slope input values should not be
reclassified into coarser categories. This could lead to incorrect
results.

---

## See Also

Related tools:
- [`r.horizon`](https://grass.osgeo.org/grass-devel/manuals/r.horizon.html)
- [`r.slope.aspect`](https://grass.osgeo.org/grass-devel/manuals/r.slope.aspect.html)
- [`r.sunhours`](https://grass.osgeo.org/grass-devel/manuals/r.sunhours.html)
- [`r.sunmask`](https://grass.osgeo.org/grass-devel/manuals/r.sunmask.html)
- [`g.proj`](https://grass.osgeo.org/grass-devel/manuals/g.proj.html)
- [`r.null`](https://grass.osgeo.org/grass-devel/manuals/r.null.html)
- [`v.surf.rst`](https://grass.osgeo.org/grass-devel/manuals/v.surf.rst.html)

---

## Authors

Jaroslav Hofierka, GeoModel, s.r.o. Bratislava, Slovakia Marcel Suri, GeoModel, s.r.o. Bratislava, Slovakia Thomas Huld, JRC, Italy © 2007, Jaroslav Hofierka, Marcel Suri. This program is free software
under the GNU General Public License (>=v2)
hofierka@geomodel.sk suri@geomodel.sk

---

## Resources

- [Official r.sun manual](https://grass.osgeo.org/grass-devel/manuals/r.sun.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.sun.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
