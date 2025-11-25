# r.resamp.rst

**Category**: raster

## Description

Reinterpolates and optionally computes topographic analysis from input raster map to a new raster map (possibly with different resolution) using regularized spline with tension and smoothing.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_resamp_rst(input,ew_res,ns_res,elevation=None,slope=None,aspect=None,pcurvature=None,tcurvature=None,mcurvature=None,smooth=None,maskmap=None,overlap=3,zscale=1.0,tension=40.,theta=None,scalex=None,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str | np.ndarray, required`**
   - Name of input raster map
   - Used as: input, raster, name

2. **`ew_res : float, required`**
   - Desired east-west resolution

3. **`ns_res : float, required`**
   - Desired north-south resolution

4. **`elevation : str | type(np.ndarray) | type(np.array) | type(gs.array.array), optional`**
   - Name for output elevation raster map
   - Used as: output, raster, name

5. **`slope : str | type(np.ndarray) | type(np.array) | type(gs.array.array), optional`**
   - Name for output slope map (or fx)
   - Used as: output, raster, name

6. **`aspect : str | type(np.ndarray) | type(np.array) | type(gs.array.array), optional`**
   - Name for output aspect map (or fy)
   - Used as: output, raster, name

7. **`pcurvature : str | type(np.ndarray) | type(np.array) | type(gs.array.array), optional`**
   - Name for output profile curvature map (or fxx)
   - Used as: output, raster, name

8. **`tcurvature : str | type(np.ndarray) | type(np.array) | type(gs.array.array), optional`**
   - Name for output tangential curvature map (or fyy)
   - Used as: output, raster, name

9. **`mcurvature : str | type(np.ndarray) | type(np.array) | type(gs.array.array), optional`**
   - Name for output mean curvature map (or fxy)
   - Used as: output, raster, name

10. **`smooth : str | np.ndarray, optional`**
   - Name of input raster map containing smoothing
   - Used as: input, raster, name

11. **`maskmap : str | np.ndarray, optional`**
   - Name of input raster map to be used as mask
   - Used as: input, raster, name

12. **`overlap : int, optional`**
   - Rows/columns overlap for segmentation
   - Default: 3

13. **`zscale : float, optional`**
   - Multiplier for z-values
   - Default: 1.0

14. **`tension : float, optional`**
   - Spline tension value
   - Default: 40.

15. **`theta : float, optional`**
   - Anisotropy angle (in degrees counterclockwise from East)

16. **`scalex : float, optional`**
   - Anisotropy scaling factor

17. **`flags : str, optional`**
   - Allowed values: t, d
   - t
   - Use dnorm independent tension
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/r.resamp.rst.html#__tabbed_2_3) for all details)*

18. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

19. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

20. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

21. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 21 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/r.resamp.rst.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | np.ndarray | tuple[np.ndarray] | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned. If an array type (e.g., np.ndarray) is used for one of the raster outputs, the result will be an array and will have the shape corresponding to the computational region. If an array type is used for more than one raster output, the result will be a tuple of arrays.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

r.resamp.rst reinterpolates the values a from given raster map (named input ) to a new raster map (named elev ). This module is intended for
reinterpolation of continuous data to a different resolution rather than
for interpolation from scattered data (use the v.surf.* modules for
that purpose).

The extent of all resulting raster maps is taken from the settings of
the actual computational region (which may differ from the extent of the
input raster map). The resolution of the computational region however
has to be aligned to the resolution of the input map to avoid artefacts.

Reinterpolation (resampling) is done to higher, same or lower resolution
specified by the ew_res and ns_res parameters.

All resulting raster maps are created using the settings of the current
region (which may be different from that of the input raster map).

Optionally, and simultaneously with interpolation, topographic
parameters are computed from an input raster map containing z-values of
elevation/depth: slope, aspect, profile curvature (measured in the
direction of steepest slope), tangential curvature (measured in the
direction of a tangent to contour line) and/or mean curvature are
computed from and saved as raster maps as specified by the options slope, aspect, pcurv, tcurv, mcurv respectively.

If the -d flag is set the program outputs partial derivatives fx, fy,
fxx, fxy, and fyy instead of slope, aspect and curvatures.

For noisy data it is possible to define spatially variable smoothing by
providing a raster map named by the smooth option containing smoothing
parameters. With the smoothing parameter set to zero ( smooth is not
given or contains zero data), the resulting surface passes exactly
through the data points.

The user can also define a raster map (named with maskmap ) which will
be used as a mask. The interpolation is skipped for cells which have
zero or NULL value in the mask.

Zero values will be assigned to these cells in all output raster maps.

The zmult parameter allows the user to rescale the z-values which may
be useful, e.g., for transformation of elevations given in feet to
meters, so that the proper values of slopes and curvatures can be
computed. The default value is 1.

A regularized spline with tension method is used for the interpolation.
The tension parameter tunes the character of the resulting surface
from thin plate to membrane. Higher values of tension parameter reduce
the overshoots that can appear in surfaces with rapid change of
gradient.

The -t flag can be set to use "dnorm independent tension".

The interpolation is performed for overlapping rectangular segments. The
user can define the width of overlap (in number of cells) with the overlap option. The default value is 3.

---

## Authors

Original version of program (in FORTRAN): Lubos Mitas, NCSA, University of Illinois at Urbana Champaign, Il Helena Mitasova, US Army CERL, Champaign, Illinois
Modified program (translated to C, adapted for GRASS , segmentation
procedure): Irina Kosinovsky, US Army CERL. Dave Gerdes, US Army CERL.

---

## Resources

- [Official r.resamp.rst manual](https://grass.osgeo.org/grass-devel/manuals/r.resamp.rst.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.resamp.rst.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
