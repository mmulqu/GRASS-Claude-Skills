# i.rectify

**Category**: imagery

## Description

Rectifies an image by computing a coordinate transformation for each pixel in the image based on the control points.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.i_rectify(group,input=None,extension,order=1,resolution=None,memory=300,method="nearest",flags=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`group : str, required`**
   - Name of input imagery group
   - Used as: input, group, name

2. **`input : str | list[str], optional`**
   - Name of input raster map(s)
   - Used as: input, raster, name

3. **`extension : str, required`**
   - Output raster map(s) suffix

4. **`order : int, required`**
   - Rectification polynomial order (1-3)
   - Allowed values: 1-3
   - Default: 1

5. **`resolution : float, optional`**
   - Target resolution (ignored if -c flag used)

6. **`memory : int, optional`**
   - Maximum memory to be used (in MB)
   - Cache size for raster rows
   - Used as: memory in MB

7. **`method : str, optional`**
   - Interpolation method to use
   - Allowed values: nearest, linear, cubic, lanczos, linear_f, cubic_f, lanczos_f
   - Default: nearest

8. **`flags : str, optional`**
   - Allowed values: c, a, t
   - c
   - Use current region settings in target location (def.=calculate smallest area)
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/i.rectify.html#__tabbed_2_3) for all details)*

9. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

10. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

11. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 11 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/i.rectify.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

i.rectify uses the control points included in the source data or
identified with the Ground Control Points Manager to
calculate a transformation matrix and then converts x,y cell coordinates
to standard map coordinates for each pixel in the image. The result is a
planimetric image with a transformed coordinate system (i.e., a
different coordinate system than before it was rectified). Supported
transformation methods are first, second, and third order polynomial and
thin plate spline. Thin plate spline is recommended for ungeoreferenced
satellite imagery where ground control points (GCPs) are included.
Examples are NOAA/AVHRR and ENVISAT imagery which include throusands of GCPs.

If no ground control points are available, the Ground Control Points
Manager must be run before i.rectify . An image must be
georeferenced before it can reside in a standard coordinate project, and
therefore be analyzed with the other map layers there. Upon completion
of i.rectify , the rectified image is deposited in the target standard
coordinate project. This project is selected using i.target .

More than one raster map may be rectified at a time. Each cell file
should be given a unique output file name. The rectified image or
rectified raster maps will be located in the target project when the
program is completed. The original unrectified files are not modified or
removed.

If the -c flag is used, i.rectify will only rectify that portion
of the image or raster map that occurs within the chosen window region
in the target project, and only that portion of the cell file will be
relocated in the target database. It is important therefore, to check
the current mapset window in the target project if the -c flag is
used.

If you are rectifying a file with plans to patch it to another file
using the GRASS program r.patch , choose option number one, the current
window in the target project. This window, however, must be the default
window for the target project. When a file being rectified is smaller
than the default window in which it is being rectified, NULLs are added
to the rectified file. Patching files of the same size that contain NULL
data, eliminates the possibility of a no-data line in the patched
result. This is because, when the images are patched, the NULLs in the
image are "covered" with non-NULL pixel values. When rectifying files
that are going to be patched, rectify all of the files using the same
default window.

The desired order of transformation (1, 2, or 3) is selected with the order option. The program will calculate the RMSE and check the
required number of points.

x' = ax + by + c

y' = Ax + By + C

The a, b, c, A, B, C are determined by least squares regression based on
the control points entered. This transformation applies scaling,
translation and rotation. It is NOT a general purpose rubber-sheeting
like TPS, nor is it ortho-photo rectification using a DEM, not second
order polynomial, etc. It can be used if (1) you have geometrically
correct images, and (2) the terrain or camera distortion effect can be
ignored.

i.rectify uses a first, second, or third order transformation matrix
to calculate the registration coefficients. The number of control points
required for a selected order of transformation (represented by n) is

((n + 1) * (n + 2) / 2)

or 3, 6, and 10 respectively. It is strongly recommended that one or
more additional points be identified to allow for an overly-determined
transformation calculation which will generate the Root Mean Square
(RMS) error values for each included point. The RMS error values for all
the included control points are immediately recalculated when the user
selects a different transformation order from the menu bar. The
polynomial equations are performed using a modified Gaussian elimination
method.

TPS transformation is selected with the -t flag. This method of
coordinate transformation is recommended for satellite imagery where
hundreds or thousands of GCPs are included, and for historical printed
or scanned maps with unknown georeferencing and/or known localized
distortions.

TPS combines a linear affine transformation with individual
transformation coefficients for each GCP, using the radial basis kernel
function with the distance dist between any two points:

dist^2 * log(dist)

As a consequence, localized distortions can be removed with TPS
transformation. For example, scan line sensors will have due to the
changing viewing angle larger distortions towards the end points of the
scan line than at the center of the scan line. Even higher order
polynomial transformations are not able to remove these locally
different distortions, but TPS transformation can. For best results, TPS
requires an even and, for localized distortions, dense spacing of GCPs.

The rectified data is resampled with one of seven different methods: nearest , bilinear , cubic , lanczos , bilinear_f , cubic_f , or lanczos_f .

The method=nearest method, which performs a nearest neighbor
assignment, is the fastest of the resampling methods. It is primarily
used for categorical data such as a land use classification, since it
will not change the values of the data cells. The method=bilinear method determines the new value of the cell based on a weighted distance
average of the 4 surrounding cells in the input map. The method=cubic method determines the new value of the cell based on a weighted distance
average of the 16 surrounding cells in the input map. The method=lanczos method determines the new value of the cell based on a
weighted distance average of the 25 surrounding cells in the input map.

The bilinear, cubic and lanczos interpolation methods are most
appropriate for continuous data and cause some smoothing. These options
should not be used with categorical data, since the cell values will be
altered.

In the bilinear, cubic and lanczos methods, if any of the surrounding
cells used to interpolate the new cell value are NULL, the resulting
cell will be NULL, even if the nearest cell is not NULL. This will cause
some thinning along NULL borders, such as the coasts of land areas in a
DEM. The bilinear_f , cubic_f and lanczos_f interpolation methods
can be used if thinning along NULL edges is not desired. These methods
"fall back" to simpler interpolation methods along NULL borders. That
is, from lanczos to cubic to bilinear to nearest.

If nearest neighbor assignment is used, the output map has the same
raster format as the input map. If any of the other interpolations is
used, the output map is written as floating point.

---

## See Also

Related tools:

---

## Authors

William R. Enslin, Michigan State University, Center for Remote Sensing
Modified for GRASS 5.0 by: Luca Palmeri ( palmeri@ux1.unipd.it ) Bill Hughes Pierre de Mouveaux ( pmx@audiovu.com ) CMD mode by Bob Covill

---

## Resources

- [Official i.rectify manual](https://grass.osgeo.org/grass-devel/manuals/i.rectify.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/i.rectify.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
