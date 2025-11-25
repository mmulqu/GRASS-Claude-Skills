# r.horizon

**Category**: raster

## Description

Computes horizon angle height from a digital elevation model. The module has two different modes of operation: 1. Computes the entire horizon around a single point whose coordinates are given with the 'coord' option. The horizon height (in radians). 2. Computes one or more raster maps of the horizon height in a single direction. The input for this is the angle (in degrees), which is measured counterclockwise with east=0, north=90 etc. The output is the horizon height in radians.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_horizon(elevation,direction=None,step=None,start=0.0,end=360.0,bufferzone=None,e_buff=None,w_buff=None,n_buff=None,s_buff=None,maxdistance=None,output=None,coordinates=None,distance=1.0,format="plain",file="-",nprocs=0,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`elevation : str | np.ndarray, required`**
   - Name of input elevation raster map
   - Used as: input, raster, name

2. **`direction : float, optional`**
   - Direction in which you want to know the horizon height

3. **`step : float, optional`**
   - Angle step size for multidirectional horizon [degrees]

4. **`start : float, optional`**
   - Start angle for multidirectional horizon [degrees]
   - Default: 0.0

5. **`end : float, optional`**
   - End angle for multidirectional horizon [degrees]
   - Default: 360.0

6. **`bufferzone : float, optional`**
   - For horizon rasters, read from the DEM an extra buffer around the present region
   - Allowed values: 0-

7. **`e_buff : float, optional`**
   - For horizon rasters, read from the DEM an extra buffer eastward the present region
   - Allowed values: 0-

8. **`w_buff : float, optional`**
   - For horizon rasters, read from the DEM an extra buffer westward the present region
   - Allowed values: 0-

9. **`n_buff : float, optional`**
   - For horizon rasters, read from the DEM an extra buffer northward the present region
   - Allowed values: 0-

10. **`s_buff : float, optional`**
   - For horizon rasters, read from the DEM an extra buffer southward the present region
   - Allowed values: 0-

11. **`maxdistance : float, optional`**
   - The maximum distance to consider when finding the horizon height

12. **`output : str | type(np.ndarray) | type(np.array) | type(gs.array.array), optional`**
   - Name for output basename raster map(s)
   - Used as: output, raster, basename

13. **`coordinates : list[tuple[float, float]] | tuple[float, float] | list[float] | str, optional`**
   - Coordinate(s) for which you want to calculate the horizon
   - Used as: input, coords, east,north

14. **`distance : float, optional`**
   - Sampling distance step coefficient (0.5-1.5)
   - Default: 1.0

15. **`format : str, required`**
   - Output format
   - Used as: name
   - Allowed values: plain, json
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/r.horizon.html#__tabbed_2_3) for all details)*

16. **`file : str, optional`**
   - Name of file for output (use output=- for stdout)
   - Used as: output, file, name
   - Default: -

17. **`nprocs : int, optional`**
   - Number of threads for parallel computing
   - 0: use OpenMP default; >0: use nprocs; <0: use MAX-nprocs
   - Default: 0

18. **`flags : str, optional`**
   - Allowed values: l, d, c
   - l
   - Include horizon distance in the plain output
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/r.horizon.html#__tabbed_2_3) for all details)*

19. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

20. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

21. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

22. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 22 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/r.horizon.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | np.ndarray | tuple[np.ndarray] | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned. If an array type (e.g., np.ndarray) is used for one of the raster outputs, the result will be an array and will have the shape corresponding to the computational region. If an array type is used for more than one raster output, the result will be a tuple of arrays.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

r.horizon computes the angular height of terrain horizon in radians.
It reads a raster of elevation data and outputs the horizon outline in
one of two modes:

The directions are given as azimuthal angles (in degrees), with the
angle starting with 0 towards East and moving counterclockwise (North is
90, etc.). The calculation takes into account the actual projection, so
the angles are corrected for direction distortions imposed by it. The
directions are thus aligned to those of the geographic projection and
not the coordinate system given by the rows and columns of the raster
map. This correction implies that the resulting cardinal directions
represent true orientation towards the East, North, West and South. The
only exception of this feature is x,y coordinate system, where this
correction is not applied.

Using the -c flag, the azimuthal angles will be printed in compass
orientation (North=0, clockwise).

Activating the -l flag allows additionally printing the distance to
each horizon angle.

The elevation parameter is an input elevation raster map. If the
buffer options are used (see below), this raster should extend over the
area that accommodate the presently defined region plus defined buffer
zones.

The step parameter gives the angle step (in degrees) between
successive azimuthal directions for the calculation of the horizon.
Thus, a value of 5 for the step will give a total of 360/5=72
directions (72 raster maps if used in the raster map mode).

The start parameter gives the angle start (in degrees) for the
calculation of the horizon. The default value is 0 (East with North
being 90 etc.).

The end parameter gives the angle end (in degrees) for the calculation
of the horizon. The end point is omitted! So for example if we run
r.horizon with step=10, start=30 and end=70 the raster maps generated by
r.horizon will be only for angles: 30, 40, 50, 60. The default value is
360.

The direction parameter gives the initial direction of the first
output. This parameter acts as an direction angle offset. For example,
if you want to get horizon angles for directions 45 and 225 degrees, the direction should be set to 45 and step to 180. If you only want one
single direction, use this parameter to specify desired direction of
horizon angle, and set the step size to 0 degrees. Otherwise all
angles for a given starting direction with step of step are
calculated.

The distance controls the sampling distance step size for the search
for horizon along the line of sight. The default value is 1.0 meaning
that the step size will be taken from the raster resolution. Setting the
value below 1.0 might slightly improve results for directions apart from
the cardinal ones, but increasing the processing load of the search
algorithm.

The maxdistance value gives a maximum distance to move away from the
origin along the line of sight in order to search for the horizon
height. The default maxdistance is the full map extent. The smaller
this value the faster the calculation but the higher the risk that you
may miss a terrain feature that can contribute significantly to the
horizon outline. Note that a viewshed can be calculated with r.viewshed .

The coordinate parameter takes one or multiple pairs of
easting-northing values in the current coordinate system and calculates
the values of angular height of the horizon around each point. To
achieve the consistency of the results, the point coordinate is aligned
to the midpoint of the closest elevation raster cell.

If an analyzed point (or raster cell) lies close to the edge of the
defined region, the horizon calculation may not be realistic, since it
may not see some significant terrain features which could have
contributed to the horizon, because these features are outside the
region. There are to options how to set the size of the buffer that is
used to increase the area of the horizon analysis. The bufferzone parameter allows you to specify the same size of buffer for all cardinal
directions and the parameters e_buff , n_buff , s_buff , and w_buff allow you to specify a buffer size individually for each of the four
directions. The buffer parameters influence only size of the read
elevation map, while the analysis in the raster mode will be done only
for the area specified by the current region definition.

The output parameter defines the basename of the output horizon raster
maps. The raster name of each horizon direction raster will be
constructed as basename_ ANGLE, where ANGLE is the angle in degrees
with the direction. If you use r.horizon in the point mode this
option will be ignored.

The file parameter allows saving the resulting horizon angles in a
comma separated ASCII file with option format=plain or in a JSON
file with option format=json (point mode only). If you use r.horizon in the raster map mode this option will be ignored.

At the moment the elevation and maximum distance must be measured in
meters, even if you use geographical coordinates (longitude/latitude).
If your projection is based on distance (easting and northing), these
too must be in meters. The buffer parameters must be in the same units
as the raster coordinates (e.g., for latitude-longitude buffers are
measured in degrees).

---

## See Also

Related tools:
- [`r.sun`](https://grass.osgeo.org/grass-devel/manuals/r.sun.html)
- [`r.sunmask`](https://grass.osgeo.org/grass-devel/manuals/r.sunmask.html)
- [`r.viewshed`](https://grass.osgeo.org/grass-devel/manuals/r.viewshed.html)

---

## Authors

Thomas Huld, Joint Research Centre of the European Commission, Ispra,
Italy
Tomas Cebecauer, Joint Research Centre of the European Commission,
Ispra, Italy
Jaroslav Hofierka, GeoModel s.r.o., Bratislava, Slovakia Marcel Suri, Joint Research Centre of the European Commission, Ispra,
Italy
© 2007, Thomas Huld, Tomas Cebecauer, Jaroslav Hofierka, Marcel Suri Thomas.Huld@jrc.it Tomas.Cebecauer@jrc.it hofierka@geomodel.sk Marcel.Suri@jrc.it

---

## Resources

- [Official r.horizon manual](https://grass.osgeo.org/grass-devel/manuals/r.horizon.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.horizon.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
