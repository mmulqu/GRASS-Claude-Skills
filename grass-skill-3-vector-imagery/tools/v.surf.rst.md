# v.surf.rst

**Category**: vector

## Description

Performs surface interpolation from vector points map by splines. Spatial approximation and topographic analysis from given point or isoline data in vector format to floating point raster format using regularized spline with tension.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.v_surf_rst(input,layer="1",zcolumn=None,where=None,elevation=None,slope=None,aspect=None,pcurvature=None,tcurvature=None,mcurvature=None,deviations=None,cvdev=None,treeseg=None,overwin=None,nprocs=1,mask=None,tension=40.,smooth=None,smooth_column=None,segmax=40,npmin=300,dmin=None,dmax=None,zscale=1.0,theta=None,scalex=None,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str, required`**
   - Name of input vector map
   - Or data source for direct OGR access
   - Used as: input, vector, name

2. **`layer : str, optional`**
   - Layer number or name
   - Vector features can have category values in different layers. This number determines which layer to use. When used with direct OGR access this is the layer name.
   - Used as: input, layer

3. **`zcolumn : str, optional`**
   - Name of the attribute column with values to be used for approximation
   - If not given and input is 2D vector map then category values are used. If input is 3D vector map then z-coordinates are used.
   - Used as: input, dbcolumn, name

4. **`where : str, optional`**
   - WHERE conditions of SQL statement without 'where' keyword
   - Example: income < 1000 and population >= 10000
   - Used as: input, sql_query, sql_query

5. **`elevation : str | type(np.ndarray) | type(np.array) | type(gs.array.array), optional`**
   - Name for output surface elevation raster map
   - Used as: output, raster, name

6. **`slope : str | type(np.ndarray) | type(np.array) | type(gs.array.array), optional`**
   - Name for output slope raster map
   - Used as: output, raster, name

7. **`aspect : str | type(np.ndarray) | type(np.array) | type(gs.array.array), optional`**
   - Name for output aspect raster map
   - Used as: output, raster, name

8. **`pcurvature : str | type(np.ndarray) | type(np.array) | type(gs.array.array), optional`**
   - Name for output profile curvature raster map
   - Used as: output, raster, name

9. **`tcurvature : str | type(np.ndarray) | type(np.array) | type(gs.array.array), optional`**
   - Name for output tangential curvature raster map
   - Used as: output, raster, name

10. **`mcurvature : str | type(np.ndarray) | type(np.array) | type(gs.array.array), optional`**
   - Name for output mean curvature raster map
   - Used as: output, raster, name

11. **`deviations : str, optional`**
   - Name for output deviations vector point map
   - Used as: output, vector, name

12. **`cvdev : str, optional`**
   - Name for output cross-validation errors vector point map
   - Used as: output, vector, name

13. **`treeseg : str, optional`**
   - Name for output vector map showing quadtree segmentation
   - Used as: output, vector, name

14. **`overwin : str, optional`**
   - Name for output vector map showing overlapping windows
   - Used as: output, vector, name

15. **`nprocs : int, optional`**
   - Number of threads for parallel computing
   - Default: 1

16. **`mask : str | np.ndarray, optional`**
   - Name of raster map used as mask
   - Used as: input, raster, name

17. **`tension : float, optional`**
   - Tension parameter
   - Default: 40.

18. **`smooth : float, optional`**
   - Smoothing parameter
   - Smoothing is by default 0.1 unless smooth_column is specified

19. **`smooth_column : str, optional`**
   - Name of the attribute column with smoothing parameters

20. **`segmax : int, optional`**
   - Maximum number of points in a segment
   - Default: 40

21. **`npmin : int, optional`**
   - Minimum number of points for approximation in a segment (>segmax)
   - Default: 300

22. **`dmin : float, optional`**
   - Minimum distance between points (to remove almost identical points). Default value is half of  the smaller resolution of the current region

23. **`dmax : float, optional`**
   - Maximum distance between points on isoline (to insert additional points)

24. **`zscale : float, optional`**
   - Conversion factor for values used for approximation
   - Default: 1.0

25. **`theta : float, optional`**
   - Anisotropy angle (in degrees counterclockwise from East)

26. **`scalex : float, optional`**
   - Anisotropy scaling factor

27. **`flags : str, optional`**
   - Allowed values: c, t, d
   - c
   - Perform cross-validation procedure without raster approximation
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/v.surf.rst.html#__tabbed_2_3) for all details)*

28. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

29. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

30. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

31. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 31 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/v.surf.rst.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | np.ndarray | tuple[np.ndarray] | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned. If an array type (e.g., np.ndarray) is used for one of the raster outputs, the result will be an array and will have the shape corresponding to the computational region. If an array type is used for more than one raster output, the result will be a tuple of arrays.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

v.surf.rst program performs spatial approximation based on z-values (input vector map is 3D and zcolumn parameter is not given), categories (input vector map is 2D and zcolumn parameter is not
given), or attributes ( zcolumn parameter is given) of point or
isoline data given in a vector map named input to grid cells in the
output raster map elevation representing a surface.

As an option, simultaneously with approximation, topographic parameters
slope, aspect, profile curvature (measured in the direction of the
steepest slope), tangential curvature (measured in the direction of a
tangent to contour line) or mean curvature are computed and saved as
raster maps specified by the options slope, aspect, pcurv, tcurv,
mcurv respectively. If -d flag is set, v.surf.rst outputs
partial derivatives f_x , f_y , f_xx , f_yy , f_xy instead of slope, aspect, profile,
tangential and mean curvatures respectively. If the input vector map
have time stamp, the program creates time stamp for all output maps.

User can either use r.mask to set a mask or specify a
raster map in mask option, which will be used as a mask. The
approximation is skipped for cells which have zero or NULL value in
mask. NULL values will be assigned to these cells in all output raster
maps. Data points are checked for identical points and points that are
closer to each other than the given dmin are removed. If sparsely
digitized contours or isolines are used as input, additional points are
computed between each 2 points on a line if the distance between them is
greater than specified dmax . Parameter zmult allows user to
rescale the values used for approximation (useful e.g. for
transformation of elevations given in feet to meters, so that the proper
values of slopes and curvatures can be computed).

Regularized spline with tension is used for the approximation. The tension parameter tunes the character of the resulting surface from
thin plate to membrane. Smoothing parameter smooth controls the
deviation between the given points and the resulting surface and it can
be very effective in smoothing noisy data while preserving the
geometrical properties of the surface. With the smoothing parameter set
to zero ( smooth=0 ) the resulting surface passes exactly through the
data points (spatial interpolation is performed). When smoothing
parameter is used, it is also possible to output a vector point map deviations containing deviations of the resulting surface from the
given data.

If the number of given points is greater than segmax , segmented
processing is used. The region is split into quadtree-based rectangular
segments, each having less than segmax points and approximation is
performed on each segment of the region. To ensure smooth connection of
segments the approximation function for each segment is computed using
the points in the given segment and the points in its neighborhood which
are in the rectangular window surrounding the given segment. The number
of points taken for approximation is controlled by npmin , the value
of which must be larger than segmax . User can choose to output
vector maps treeseg and overwin which represent the quad tree
used for segmentation and overlapping neighborhoods from which
additional points for approximation on each segment were taken.

Predictive error of surface approximation for given parameters can be
computed using the -c flag. A crossvalidation procedure is then
performed using the data given in the vector map input and the
estimated predictive errors are stored in the vector point map cvdev . When using this flag, no raster output maps are computed.
Anisotropic surfaces can be interpolated by setting anisotropy angle theta and scaling factor scalex . The program writes values of
selected input and internally computed parameters to the history file of
raster map elevation .

The user must run g.region before the program to set
the region and resolution for approximation.

---

## See Also

Related tools:
- [`v.vol.rst`](https://grass.osgeo.org/grass-devel/manuals/v.vol.rst.html)
- [`v.surf.idw`](https://grass.osgeo.org/grass-devel/manuals/v.surf.idw.html)
- [`v.surf.bspline`](https://grass.osgeo.org/grass-devel/manuals/v.surf.bspline.html)
- [`r.fillnulls`](https://grass.osgeo.org/grass-devel/manuals/r.fillnulls.html)
- [`g.region`](https://grass.osgeo.org/grass-devel/manuals/g.region.html)

---

## Authors

Original version of program (in FORTRAN) and GRASS enhancements : Lubos Mitas, NCSA, University of Illinois at Urbana Champaign, Illinois,
USA (1990-2000); Department of Physics, North Carolina State University,
Raleigh Helena Mitasova, USA CERL, Department of Geography, University of
Illinois at Urbana-Champaign, USA (1990-2001); MEAS, North Carolina
State University, Raleigh
Modified program (translated to C, adapted for GRASS, new segmentation
procedure): Irina Kosinovsky, US Army CERL, Dave Gerdes, US Army CERL
Modifications for new sites format and timestamping: Darrel McCauley, Purdue University, Bill Brown, US Army CERL
Update for GRASS5.7, GRASS6 and addition of crossvalidation: Jaroslav Hofierka, University of Presov; Radim Blazek, ITC-irst
Parallelization using OpenMP: Stanislav Zubal, Czech Technical University in Prague Michal Lacko, Pavol Jozef Safarik University in Kosice
Parallelization of cross-validation using OpenMP: Chung-Yuan Liang, Purdue University, West Lafayette, Indiana, USA

---

## Resources

- [Official v.surf.rst manual](https://grass.osgeo.org/grass-devel/manuals/v.surf.rst.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/v.surf.rst.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
