# v.lidar.growing

**Category**: vector

## Description

Building contour determination and Region Growing algorithm for determining the building inside

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.v_lidar_growing(input,output,first,tj=0.2,td=0.6,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str, required`**
   - Name of input vector map
   - Input vector (v.lidar.edgedetection output)
   - Used as: input, vector, name

2. **`output : str, required`**
   - Name for output vector map
   - Used as: output, vector, name

3. **`first : str, required`**
   - Name of the first pulse vector map
   - Used as: input, vector, name

4. **`tj : float, optional`**
   - Threshold for cell object frequency in region growing
   - Default: 0.2

5. **`td : float, optional`**
   - Threshold for double pulse in region growing
   - Default: 0.6

6. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

7. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

8. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

9. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

v.lidar.growing is the second of three steps to filter LiDAR data. The
filter aims to recognize and extract attached and detached object (such
as buildings, bridges, power lines, trees, etc.) in order to create a
Digital Terrain Model.

The modules identifies which is the internal area of every object on a
LiDAR point surface. The classification categories from v.lidar.edgedetection are now rasterized. For each cell, it is
evaluated if it (the cell) contains a point with double impulse
(difference between the first and last pulse greater than a given
threshold). Starting from cells classified as OBJECT and with only one
pulse all linked cells are selected and a convex hull algorithm is
applied to them. Simultaneously, the mean of the corresponding heights
(mean edge height) are computed. Points inside the convex hull are
classified as OBJECT if their height is greater than or equal to the
previously mean computed edge height. This last step is done only in
case of high planimetric resolution.

---

## See Also

Related tools:
- [`v.lidar.edgedetection`](https://grass.osgeo.org/grass-devel/manuals/v.lidar.edgedetection.html)
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

- [Official v.lidar.growing manual](https://grass.osgeo.org/grass-devel/manuals/v.lidar.growing.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/v.lidar.growing.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
