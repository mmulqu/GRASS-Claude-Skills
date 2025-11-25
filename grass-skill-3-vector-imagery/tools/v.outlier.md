# v.outlier

**Category**: vector

## Description

Removes outliers from vector point data.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.v_outlier(input,output,outlier,qgis=None,ew_step=None,ns_step=None,lambda=0.1,threshold=50,filter="both",flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str, required`**
   - Name of input vector map
   - Or data source for direct OGR access
   - Used as: input, vector, name

2. **`output : str, required`**
   - Name for output vector map
   - Used as: output, vector, name

3. **`outlier : str, required`**
   - Name for output outlier vector map
   - Used as: output, vector, name

4. **`qgis : str, optional`**
   - Name for vector map for visualization in QGIS
   - Used as: output, vector, name

5. **`ew_step : float, optional`**
   - Length of each spline step in the east-west direction
   - Default: 10 * east-west resolution

6. **`ns_step : float, optional`**
   - Length of each spline step in the north-south direction
   - Default: 10 * north-south resolution

7. **`lambda : float, optional`**
   - Tykhonov regularization weight
   - Default: 0.1

8. **`threshold : float, optional`**
   - Threshold for the outliers
   - Default: 50

9. **`filter : str, optional`**
   - Filtering option
   - Allowed values: both, positive, negative
   - Default: both

10. **`flags : str, optional`**
   - Allowed values: e
   - e
   - Estimate point density and distance

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


*Showing 10 of 14 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/v.outlier.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

v.outlier removes outliers in a 3D point cloud. By default, the
outlier identification is done by a bicubic spline interpolation of the
observation with a high regularization parameter and a low resolution in
south-north and east-west directions. Those points that differ in an
absolute value more than the given threshold from a fixed value,
reckoned from its surroundings by the interpolation, are considered as
an outlier, and hence are removed.

The filter option specifies if all outliers will be removed (default),
or only positive or only negative outliers. Filtering out only positive
outliers can be useful to filter out vegetation returns (e.g. from
forest canopies) from LIDAR point clouds, in order to extract digital
terrain models (DTMs). Filtering out only negative outliers can be
useful to estimate vegetation height.

There is a flag to create a vector that can be visualized in QGIS. That
means that topology is built and the z coordinate is considered as a
category.

---

## See Also

Related tools:
- [`v.surf.bspline`](https://grass.osgeo.org/grass-devel/manuals/v.surf.bspline.html)

---

## Authors

Original version of the program in GRASS 5.4: Maria Antonia Brovelli, Massimiliano Cannata, Ulisse Longoni and Mirko
Reguzzoni
Updates for GRASS 6: Roberto Antolin

---

## Resources

- [Official v.outlier manual](https://grass.osgeo.org/grass-devel/manuals/v.outlier.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/v.outlier.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
