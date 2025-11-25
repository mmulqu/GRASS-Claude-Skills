# r.resamp.bspline

**Category**: raster

## Description

Performs bilinear or bicubic spline interpolation with Tykhonov regularization.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_resamp_bspline(input,output,grid=None,mask=None,ew_step=None,ns_step=None,method="bicubic",lambda=0.01,memory=300,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str | np.ndarray, required`**
   - Name of input raster map
   - Used as: input, raster, name

2. **`output : str | type(np.ndarray) | type(np.array) | type(gs.array.array), required`**
   - Name for output raster map
   - Used as: output, raster, name

3. **`grid : str, optional`**
   - Name for output vector map with interpolation grid
   - Used as: output, vector, name

4. **`mask : str | np.ndarray, optional`**
   - Name of raster map to use for masking
   - Only cells that are not NULL and not zero are interpolated
   - Used as: input, raster, name

5. **`ew_step : float, optional`**
   - Length of each spline step in the east-west direction. Default: 1.5 * ewres.

6. **`ns_step : float, optional`**
   - Length of each spline step in the north-south direction. Default: 1.5 * nsres.

7. **`method : str, optional`**
   - Spline interpolation algorithm
   - Allowed values: bilinear, bicubic
   - bilinear: Bilinear interpolation
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/r.resamp.bspline.html#__tabbed_2_3) for all details)*

8. **`lambda : float, optional`**
   - Tykhonov regularization parameter (affects smoothing)
   - Default: 0.01

9. **`memory : int, optional`**
   - Maximum memory to be used (in MB)
   - Cache size for raster rows
   - Used as: memory in MB

10. **`flags : str, optional`**
   - Allowed values: n, c
   - n
   - Only interpolate null cells in input raster map

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


*Showing 10 of 14 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/r.resamp.bspline.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | np.ndarray | tuple[np.ndarray] | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned. If an array type (e.g., np.ndarray) is used for one of the raster outputs, the result will be an array and will have the shape corresponding to the computational region. If an array type is used for more than one raster output, the result will be a tuple of arrays.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

r.resamp.bspline performs a bilinear/bicubic spline interpolation with
Tykhonov regularization. The input is a raster surface map, e.g.
elevation, temperature, precipitation etc. Output is a raster map.
Optionally, only input NULL cells are interpolated, useful to fill NULL
cells, an alternative to r.fillnulls . Using the -n flag to only interpolate NULL cells will considerably speed up
the module.

The input raster map is read at its native resolution, the output raster
map will be produced for the current computational region set with g.region . A raster mask, if present, will be respected.
Masked values will be treated like other NULL cells in both the input
and output maps.

Spline step values ew_step for the east-west direction and ns_step for the north-south direction should not be smaller than the
east-west and north-south resolutions of the input map. For a raster map
without NULL cells, 1 * resolution can be used, but check for
undershoots and overshoots. For very large areas with missing values
(NULL cells), larger spline step values may be required, but most of the
time the defaults (1.5 x resolution) should be fine.

The Tykhonov regularization parameter ( lambda ) acts to smooth the
interpolation. With a small lambda , the interpolated surface closely
follows observation points; a larger value will produce a smoother
interpolation. Reasonable values are 0.0001, 0.001, 0.005, 0.01, 0.02,
0.05, 0.1 (needs more testing). For seamless NULL cell interpolation, a
small value is required. The default lambda value is set to 0.01.

From a theoretical perspective, the interpolating procedure takes place
in two parts: the first is an estimate of the linear coefficients of a
spline function; these are derived from the observation points using a
least squares regression; the second is the computation of the
interpolated surface (or interpolated vector points). As used here, the
splines are 2D piece-wise non-zero polynomial functions calculated
within a limited 2D area. The length of each spline step is defined by ew_step for the east-west direction and ns_step for the
north-south direction. For optimal performance, the spline step values
should be no less than the east-west and north-south resolutions of the
input map. Each non-NULL cell observation is modeled as a linear
function of the non-zero splines in the area around the observation. The
least squares regression predicts the coefficients of these linear
functions. Regularization avoids the need to have one one observation
and one coefficient for each spline (in order to avoid instability).

A cross validation "leave-one-out" analysis is available to help to
determine the optimal lambda value that produces an interpolation
that best fits the original observation data. The more points used for
cross-validation, the longer the time needed for computation. Empirical
testing indicates a threshold of a maximum of 100 points is recommended.
Note that cross validation can run very slowly if more than 100
observations are used. The cross-validation output reports mean and rms of the residuals from the true point value and the estimated from
the interpolation for a fixed series of lambda values. No vector nor
raster output will be created when cross-validation is selected.

---

## See Also

Related tools:
- [`r.fillnulls`](https://grass.osgeo.org/grass-devel/manuals/r.fillnulls.html)
- [`r.resamp.rst`](https://grass.osgeo.org/grass-devel/manuals/r.resamp.rst.html)
- [`r.resamp.interp`](https://grass.osgeo.org/grass-devel/manuals/r.resamp.interp.html)
- [`v.surf.bspline`](https://grass.osgeo.org/grass-devel/manuals/v.surf.bspline.html)

---

## Authors

Markus Metz
based on v.surf.bspline by Maria Antonia Brovelli, Massimiliano Cannata, Ulisse Longoni, Mirko
Reguzzoni, Roberto Antolin

---

## Resources

- [Official r.resamp.bspline manual](https://grass.osgeo.org/grass-devel/manuals/r.resamp.bspline.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.resamp.bspline.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
