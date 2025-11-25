# v.vol.rst

**Category**: vector

## Description

Interpolates point data to a 3D raster map using regularized spline with tension (RST) algorithm.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.v_vol_rst(input,cross_input=None,wcolumn=None,tension=40.,smooth=0.1,smooth_column=None,where=None,deviations=None,cvdev=None,maskmap=None,segmax=50,npmin=200,npmax=700,dmin=None,wscale=1.0,zscale=1.0,cross_output=None,elevation=None,gradient=None,aspect_horizontal=None,aspect_vertical=None,ncurvature=None,gcurvature=None,mcurvature=None,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str, required`**
   - Name of input 3D vector points map
   - Used as: input, vector, name

2. **`cross_input : str | np.ndarray, optional`**
   - Name of input surface raster map for cross-section
   - Used as: input, raster, name

3. **`wcolumn : str, optional`**
   - Name of column containing w-values attribute to interpolate
   - Used as: input, dbcolumn, name

4. **`tension : float, optional`**
   - Tension parameter
   - Default: 40.

5. **`smooth : float, optional`**
   - Smoothing parameter
   - Default: 0.1

6. **`smooth_column : str, optional`**
   - Name of column with smoothing parameters
   - Used as: input, dbcolumn, name

7. **`where : str, optional`**
   - WHERE conditions of SQL statement without 'where' keyword
   - Example: income < 1000 and population >= 10000
   - Used as: input, sql_query, sql_query

8. **`deviations : str, optional`**
   - Name for output deviations vector point map
   - Used as: output, vector, name

9. **`cvdev : str, optional`**
   - Name for output cross-validation errors vector point map
   - Used as: output, vector, name

10. **`maskmap : str | np.ndarray, optional`**
   - Name of input raster map used as mask
   - Used as: input, raster, name

11. **`segmax : int, optional`**
   - Maximum number of points in a segment
   - Default: 50

12. **`npmin : int, optional`**
   - Minimum number of points for approximation in a segment (>segmax)
   - Default: 200

13. **`npmax : int, optional`**
   - Maximum number of points for approximation in a segment (>npmin)
   - Default: 700

14. **`dmin : float, optional`**
   - Minimum distance between points (to remove almost identical points)

15. **`wscale : float, optional`**
   - Conversion factor for w-values used for interpolation
   - Default: 1.0

16. **`zscale : float, optional`**
   - Conversion factor for z-values
   - Default: 1.0

17. **`cross_output : str | type(np.ndarray) | type(np.array) | type(gs.array.array), optional`**
   - Name for output cross-section raster map
   - Used as: output, raster, name

18. **`elevation : str, optional`**
   - Name for output elevation 3D raster map
   - Used as: output, raster_3d, name

19. **`gradient : str, optional`**
   - Name for output gradient magnitude 3D raster map
   - Used as: output, raster_3d, name

20. **`aspect_horizontal : str, optional`**
   - Name for output gradient horizontal angle 3D raster map
   - Used as: output, raster_3d, name

21. **`aspect_vertical : str, optional`**
   - Name for output gradient vertical angle 3D raster map
   - Used as: output, raster_3d, name

22. **`ncurvature : str, optional`**
   - Name for output change of gradient 3D raster map
   - Used as: output, raster_3d, name

23. **`gcurvature : str, optional`**
   - Name for output Gaussian curvature 3D raster map
   - Used as: output, raster_3d, name

24. **`mcurvature : str, optional`**
   - Name for output mean curvature 3D raster map
   - Used as: output, raster_3d, name

25. **`flags : str, optional`**
   - Allowed values: c
   - c
   - Perform a cross-validation procedure without volume interpolation

26. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

27. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

28. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

29. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 29 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/v.vol.rst.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | np.ndarray | tuple[np.ndarray] | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned. If an array type (e.g., np.ndarray) is used for one of the raster outputs, the result will be an array and will have the shape corresponding to the computational region. If an array type is used for more than one raster output, the result will be a tuple of arrays.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

v.vol.rst interpolates values to a 3-dimensional raster map from
3-dimensional point data (e.g. temperature, rainfall data from climatic
stations, concentrations from drill holes etc.) given in a 3-D vector
point file named input .  The size of the output 3D raster map elevation is given by the current 3D region. Sometimes, the user may
want to get a 2-D map showing a modelled phenomenon at a crossection
surface. In that case, cross_input and cross_output options must
be specified, with the output 2D raster map cross_output containing
the crossection of the interpolated volume with a surface defined by cross_input 2D raster map. As an option, simultaneously with
interpolation, geometric parameters of the interpolated phenomenon can
be computed (magnitude of gradient, direction of gradient defined by
horizontal and vertical angles), change of gradient, Gauss-Kronecker
curvature, or mean curvature). These geometric parameters are saved as
3D raster maps gradient, aspect_horizontal, aspect_vertical,
ncurvature, gcurvature, mcurvature , respectively. Maps aspect_horizontal and aspect_vertical are in degrees.

At first, data points are checked for identical positions and points
that are closer to each other than given dmin are removed.
Parameters wscale and zscale allow the user to re-scale the
w-values and z-coordinates of the point data (useful e.g. for
transformation of elevations given in feet to meters, so that the proper
values of gradient and curvatures can be computed). Rescaling of
z-coordinates ( zscale ) is also needed when the distances in vertical
direction are much smaller than the horizontal distances; if that is the
case, the value of zscale should be selected so that the vertical
and horizontal distances have about the same magnitude.

Regularized spline with tension method is used in the interpolation. The tension parameter controls the distance over which each given point
influences the resulting volume (with very high tension, each point
influences only its close neighborhood and the volume goes rapidly to
trend between the points). Higher values of tension parameter reduce the
overshoots that can appear in volumes with rapid change of gradient. For
noisy data, it is possible to define a global smoothing parameter, smooth . With the smoothing parameter set to zero ( smooth=0 ) the
resulting volume passes exactly through the data points. When smoothing
is used, it is possible to output a vector map deviations containing
deviations of the resulting volume from the given data.

The user can define a 2D raster map named maskmap , which will be
used as a mask. The interpolation is skipped for 3-dimensional cells
whose 2-dimensional projection has a zero value in the mask. Zero values
will be assigned to these cells in all output 3D raster maps.

If the number of given points is greater than 700, segmented processing
is used. The region is split into 3-dimensional "box" segments, each
having less than segmax points and interpolation is performed on
each segment of the region. To ensure the smooth connection of segments,
the interpolation function for each segment is computed using the points
in the given segment and the points in its neighborhood. The minimum
number of points taken for interpolation is controlled by npmin ,
the value of which must be larger than segmax and less than 700.
This limit of 700 was selected to ensure the numerical stability and
efficiency of the algorithm.

Using the where parameter, the interpolation can be limited to use
only a subset of the input vectors.

Sometimes it can be difficult to figure out the proper values of
interpolation parameters. In this case, the user can use a
crossvalidation procedure using -c flag (a.k.a. "jack-knife" method)
to find optimal parameters for given data. In this method, every point
in the input point file is temporarily excluded from the computation and
interpolation error for this point location is computed. During this
procedure no output grid files can be simultanuously computed. The
procedure for larger datasets may take a very long time, so it might be
worth to use just a sample data representing the whole dataset.

Example (based on Slovakia3d
dataset ):

Based on these results, the parameters will have to be optimized. It is
recommended to plot the CV error as curve while modifying the
parameters.

The best approach is to start with tension , smooth and zscale with rough steps, or to set zscale to a constant
somewhere between 30-60. This helps to find minimal RMSE values while
then finer steps can be used in all parameters. The reasonable range is tension =10...100, smooth =0.1...1.0, zscale =10...100.

In v.vol.rst the tension parameter is much more sensitive to changes
than in v.surf.rst , therefore the user should always check the result
by visual inspection. Minimizing CV does not always provide the best
result, especially when the density of data are insufficient. Then the
optimal result found by CV is an oversmoothed surface.

---

## See Also

Related tools:
- [`g.region`](https://grass.osgeo.org/grass-devel/manuals/g.region.html)
- [`v.in.ascii`](https://grass.osgeo.org/grass-devel/manuals/v.in.ascii.html)
- [`r3.mask`](https://grass.osgeo.org/grass-devel/manuals/r3.mask.html)
- [`v.in.db`](https://grass.osgeo.org/grass-devel/manuals/v.in.db.html)
- [`v.surf.rst`](https://grass.osgeo.org/grass-devel/manuals/v.surf.rst.html)
- [`v.univar`](https://grass.osgeo.org/grass-devel/manuals/v.univar.html)

---

## Resources

- [Official v.vol.rst manual](https://grass.osgeo.org/grass-devel/manuals/v.vol.rst.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/v.vol.rst.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
