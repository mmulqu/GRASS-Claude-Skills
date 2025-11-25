# v.rectify

**Category**: vector

## Description

Rectifies a vector by computing a coordinate transformation for each object in the vector based on the control points.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.v_rectify(input,output,group=None,points=None,rmsfile=None,order=1,separator="pipe",flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str, required`**
   - Name of input vector map
   - Or data source for direct OGR access
   - Used as: input, vector, name

2. **`output : str, required`**
   - Name for output vector map
   - Used as: output, vector, name

3. **`group : str, optional`**
   - Name of input imagery group
   - Used as: input, group, name

4. **`points : str | io.StringIO, optional`**
   - Name of input file with control points
   - Used as: input, file, name

5. **`rmsfile : str | io.StringIO, optional`**
   - Name of output file with RMS errors (if omitted or '-' output to stdout
   - Used as: input, file, name

6. **`order : int, optional`**
   - Rectification polynomial order (1-3)
   - Allowed values: 1-3
   - Default: 1

7. **`separator : str, optional`**
   - Field separator for RMS report
   - Special characters: pipe, comma, space, tab, newline
   - Used as: input, separator, character

8. **`flags : str, optional`**
   - Allowed values: 3, o, r, b
   - 3
   - Perform 3D transformation
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/v.rectify.html#__tabbed_2_3) for all details)*

9. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

10. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

11. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

12. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 12 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/v.rectify.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

v.rectify uses control points to calculate a 2D or 3D transformation
matrix based on a first, second, or third order polynomial and then
converts x,y(, z) coordinates to standard map coordinates for each
object in the vector map. The result is a vector map with a transformed
coordinate system (i.e., a different coordinate system than before it
was rectified).

The -o flag enforces orthogonal rotation (currently for 3D only) where
the axes remain orthogonal to each other, e.g. a cube with right angles
remains a cube with right angles after transformation. This is not
guaranteed even with affine (1st order) 3D transformation.

Great care should be taken with the placement of Ground Control Points.
For 2D transformation, the control points must not lie on a line,
instead 3 of the control points must form a triangle. For 3D
transformation, the control points must not lie on a plane, instead 4 of
the control points must form a triangular pyramid. It is recommended to
investigate RMS errors and deviations of the Ground Control Points prior
to transformation.

2D Ground Control Points can be identified in g.gui.gcp .

3D Ground Control Points must be provided in a text file with the points option. The 3D format is equivalent to the format for 2D
ground control points with an additional third coordinate:

where x, y, z are source coordinates, east, north, height are target
coordinates and status (0 or 1) indicates whether a given point should
be used. Numbers must be separated by space and must use a point (.) as
decimal separator.

If no group is given, the rectified vector will be written to the
current mapset. If a group is given and a target has been set for
this group with i.target , the rectified vector will be
written to the target project and mapset.

The desired order of transformation (1, 2, or 3) is selected with the order option. If the -r flag is given, v.rectify will
calculate the Root Mean Square Error (RMSE) and print out statistics in
tabular format. The last row gives a summary with the first column
holding the number of active points, followed by average deviations for
each dimension and both forward and backward transformation and finally
forward and backward overall RMSE.

x' = a1 + b1 * x + c1 * y

y' = a2 + b2 * x + c2 * y

x' = a1 + b1 * x + c1 * y + d1 * z

y' = a2 + b2 * x + c2 * y + d2 * z

z' = a3 + b3 * x + c3 * y + d3 * z

The a,b,c,d coefficients are determined by least squares regression
based on the control points entered. This transformation applies
scaling, translation and rotation. It is NOT a general purpose
rubber-sheeting, nor is it ortho-photo rectification using a DEM, not
second order polynomial, etc. It can be used if (1) you have
geometrically correct data, and (2) the terrain or camera distortion
effect can be ignored.

v.rectify uses a first, second, or third order transformation matrix
to calculate the registration coefficients. The minimum number of
control points required for a 2D transformation of the selected order
(represented by n) is

((n + 1) * (n + 2) / 2)

or 3, 6, and 10 respectively. For a 3D transformation of first, second,
or third order, the minimum number of required control points is 4, 10,
and 20, respectively. It is strongly recommended that more than the
minimum number of points be identified to allow for an overly-determined
transformation calculation which will generate the Root Mean Square
(RMS) error values for each included point. The polynomial equations are
determined using a modified Gaussian elimination method.

---

## See Also

Related tools:

---

## Resources

- [Official v.rectify manual](https://grass.osgeo.org/grass-devel/manuals/v.rectify.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/v.rectify.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
