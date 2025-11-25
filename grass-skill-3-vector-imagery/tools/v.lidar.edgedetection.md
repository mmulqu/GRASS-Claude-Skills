# v.lidar.edgedetection

**Category**: vector

## Description

Detects the object's edges from a LIDAR data set.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.v_lidar_edgedetection(input,output,ew_step=None,ns_step=None,lambda_g=0.01,tgh=6,tgl=3,theta_g=0.26,lambda_r=2,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str, required`**
   - Name of input vector map
   - Or data source for direct OGR access
   - Used as: input, vector, name

2. **`output : str, required`**
   - Name for output vector map
   - Used as: output, vector, name

3. **`ew_step : float, optional`**
   - Length of each spline step in the east-west direction
   - Default: 4 * east-west resolution

4. **`ns_step : float, optional`**
   - Length of each spline step in the north-south direction
   - Default: 4 * north-south resolution

5. **`lambda_g : float, optional`**
   - Regularization weight in gradient evaluation
   - Default: 0.01

6. **`tgh : float, optional`**
   - High gradient threshold for edge classification
   - Default: 6

7. **`tgl : float, optional`**
   - Low gradient threshold for edge classification
   - Default: 3

8. **`theta_g : float, optional`**
   - Angle range for same direction detection
   - Default: 0.26

9. **`lambda_r : float, optional`**
   - Regularization weight in residual evaluation
   - Default: 2

10. **`flags : str, optional`**
   - Allowed values: e
   - e
   - Estimate point density and distance and quit

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


*Showing 10 of 14 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/v.lidar.edgedetection.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

v.lidar.edgedetection is the first of three steps to filter LiDAR
data. The filter aims to recognize and extract attached and detached
object (such as buildings, bridges, power lines, trees, etc.) in order
to create a Digital Terrain Model.

In particular, this module detects the edge of each single feature over
the terrain surface of a LIDAR point surface. First of all, a bilinear
spline interpolation with a Tychonov regularization parameter is
performed. The gradient is minimized and the low Tychonov regularization
parameter brings the interpolated functions as close as possible to the
observations. Bicubic spline interpolation with Tychonov regularization
is then performed. However, now the curvature is minimized and the
regularization parameter is set to a high value. For each point, an
interpolated value is computed from the bicubic surface and an
interpolated gradient is computed from the bilinear surface. At each
point the gradient magnitude and the direction of the edge vector are
calculated, and the residual between interpolated and observed values is
computed. Two thresholds are defined on the gradient, a high threshold tgh and a low one tgl . For each point, if the gradient magnitude
is greater than or equal to the high threshold and its residual is
greater than or equal to zero, it is labeled as an EDGE point. Similarly
a point is labeled as being an EDGE point if the gradient magnitude is
greater than or equal to the low threshold, its residual is greater than
or equal to zero, and the gradient to two of eight neighboring points is
greater than the high threshold. Other points are classified as TERRAIN.

The length (in mapping units) of each spline step is defined by ew_step for the east-west direction and ns_step for the
north-south direction.

The output will be a vector map in which points has been classified as
TERRAIN, EDGE or UNKNOWN. This vector map should be the input of v.lidar.growing module.

---

## See Also

Related tools:
- [`v.lidar.growing`](https://grass.osgeo.org/grass-devel/manuals/v.lidar.growing.html)
- [`v.lidar.correction`](https://grass.osgeo.org/grass-devel/manuals/v.lidar.correction.html)
- [`v.surf.bspline`](https://grass.osgeo.org/grass-devel/manuals/v.surf.bspline.html)
- [`v.surf.rst`](https://grass.osgeo.org/grass-devel/manuals/v.surf.rst.html)
- [`v.in.pdal`](https://grass.osgeo.org/grass-devel/manuals/v.in.pdal.html)
- [`v.in.ascii`](https://grass.osgeo.org/grass-devel/manuals/v.in.ascii.html)

---

## Authors

Original version of program in GRASS 5.4: Maria Antonia Brovelli, Massimiliano Cannata, Ulisse Longoni and Mirko
Reguzzoni
Update for GRASS 6.X: Roberto Antolin and Gonzalo Moreno

---

## Resources

- [Official v.lidar.edgedetection manual](https://grass.osgeo.org/grass-devel/manuals/v.lidar.edgedetection.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/v.lidar.edgedetection.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
