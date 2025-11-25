# v.surf.idw

**Category**: vector

## Description

Provides surface interpolation from vector point data by Inverse Distance Squared Weighting.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.v_surf_idw(input,layer="1",column=None,output,npoints=12,power=2.0,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
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

3. **`column : str, optional`**
   - Name of attribute column with values to interpolate
   - If not given and input is 2D vector map then category values are used. If input is 3D vector map then z-coordinates are used.
   - Used as: input, dbcolumn, name

4. **`output : str | type(np.ndarray) | type(np.array) | type(gs.array.array), required`**
   - Name for output raster map
   - Used as: output, raster, name

5. **`npoints : int, optional`**
   - Number of interpolation points
   - Used as: count
   - Default: 12

6. **`power : float, optional`**
   - Power parameter
   - Greater values assign greater influence to closer points
   - Default: 2.0

7. **`flags : str, optional`**
   - Allowed values: n
   - n
   - Don't index points by raster cell

8. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

9. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

10. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

11. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 11 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/v.surf.idw.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | np.ndarray | tuple[np.ndarray] | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned. If an array type (e.g., np.ndarray) is used for one of the raster outputs, the result will be an array and will have the shape corresponding to the computational region. If an array type is used for more than one raster output, the result will be a tuple of arrays.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

v.surf.idw fills a raster matrix with interpolated values generated
from a set of irregularly spaced vector data points using numerical
approximation (weighted averaging) techniques. The interpolated value of
a cell is determined by values of nearby data points and the distance of
the cell from those input points. In comparison with other methods,
numerical approximation allows representation of more complex surfaces
(particularly those with anomalous features), restricts the spatial
influence of any errors, and generates the interpolated surface from the
data points.

Values to interpolate are read from column option. If this option is
not given than the program uses categories as values to interpolate or z-coordinates if the input vector map is 3D.

---

## See Also

Related tools:
- [`g.region`](https://grass.osgeo.org/grass-devel/manuals/g.region.html)
- [`r.surf.contour`](https://grass.osgeo.org/grass-devel/manuals/r.surf.contour.html)
- [`r.surf.idw`](https://grass.osgeo.org/grass-devel/manuals/r.surf.idw.html)
- [`r.surf.gauss`](https://grass.osgeo.org/grass-devel/manuals/r.surf.gauss.html)
- [`r.surf.fractal`](https://grass.osgeo.org/grass-devel/manuals/r.surf.fractal.html)
- [`r.surf.random`](https://grass.osgeo.org/grass-devel/manuals/r.surf.random.html)
- [`v.surf.rst`](https://grass.osgeo.org/grass-devel/manuals/v.surf.rst.html)

---

## Authors

Michael Shapiro, U.S. Army Construction Engineering Research
Laboratory Improved algorithm (indexes points according to cell and ignores points
outside current region) by Paul Kelly

---

## Resources

- [Official v.surf.idw manual](https://grass.osgeo.org/grass-devel/manuals/v.surf.idw.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/v.surf.idw.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
