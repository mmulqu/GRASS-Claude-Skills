# v.lidar.correction

**Category**: vector

## Description

Corrects the v.lidar.growing output. It is the last of the three algorithms for LIDAR filtering.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.v_lidar_correction(input,output,terrain,ew_step=None,ns_step=None,lambda_c=1,tch=2,tcl=1,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str, required`**
   - Name of input vector map
   - Input observation vector map name (v.lidar.growing output)
   - Used as: input, vector, name

2. **`output : str, required`**
   - Output classified vector map name
   - Used as: output, vector, name

3. **`terrain : str, required`**
   - Name for output only 'terrain' points vector map
   - Used as: output, vector, name

4. **`ew_step : float, optional`**
   - Length of each spline step in the east-west direction
   - Default: 25 * east-west resolution

5. **`ns_step : float, optional`**
   - Length of each spline step in the north-south direction
   - Default: 25 * north-south resolution

6. **`lambda_c : float, optional`**
   - Regularization weight in reclassification evaluation
   - Default: 1

7. **`tch : float, optional`**
   - High threshold for object to terrain reclassification
   - Default: 2

8. **`tcl : float, optional`**
   - Low threshold for terrain to object reclassification
   - Default: 1

9. **`flags : str, optional`**
   - Allowed values: e
   - e
   - Estimate point density and distance and quit

10. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

11. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

12. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

13. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 13 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/v.lidar.correction.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

v.lidar.correction is the last of three steps to filter LiDAR data.
The filter aims to recognize and extract attached and detached object
(such as buildings, bridges, power lines, trees, etc.) in order to
create a Digital Terrain Model.

The module, which could be iterated several times, makes a comparison
between the LiDAR observations and a bilinear spline interpolation with
a Tychonov regularization parameter performed on the TERRAIN SINGLE
PULSE points only. The gradient is minimized by the regularization
parameter. Analysis of the residuals between the observations and the
interpolated values results in four cases (the next classification is
referred to that of the v.lidar.growing output vector):

a) Points classified as TERRAIN differing more than a threshold
value are interpreted and reclassified as OBJECT, for both single and
double pulse points.

b) Points classified as OBJECT and closed enough to the interpolated
surface are interpreted and reclassified as TERRAIN, for both single and
double pulse points.

The length (in mapping units) of each spline step is defined by ew_step for the east-west direction and ns_step for the
north-south direction.

---

## See Also

Related tools:
- [`v.lidar.edgedetection`](https://grass.osgeo.org/grass-devel/manuals/v.lidar.edgedetection.html)
- [`v.lidar.growing`](https://grass.osgeo.org/grass-devel/manuals/v.lidar.growing.html)
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

- [Official v.lidar.correction manual](https://grass.osgeo.org/grass-devel/manuals/v.lidar.correction.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/v.lidar.correction.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
