# v.extrude

**Category**: vector

## Description

Extrudes flat vector features to 3D vector features with defined height. Optionally the height can be derived from sampling of elevation raster map.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.v_extrude(input,layer="-1",cats=None,where=None,type="point,line,area",output,zshift=0,height=None,height_column=None,elevation=None,method="nearest",scale=1.0,null_value=None,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str, required`**
   - Name of input vector map
   - Or data source for direct OGR access
   - Used as: input, vector, name

2. **`layer : str, optional`**
   - Layer number or name ('-1' for all layers)
   - A single vector map can be connected to multiple database tables. This number determines which table to use. When used with direct OGR access this is the layer name.
   - Used as: input, layer

3. **`cats : str, optional`**
   - Category values
   - Example: 1,3,7-9,13
   - Used as: input, cats, range

4. **`where : str, optional`**
   - WHERE conditions of SQL statement without 'where' keyword
   - Example: income < 1000 and population >= 10000
   - Used as: input, sql_query, sql_query

5. **`type : str | list[str], optional`**
   - Input feature type
   - Allowed values: point, line, area
   - Default: point,line,area

6. **`output : str, required`**
   - Name for output vector map
   - Used as: output, vector, name

7. **`zshift : float, optional`**
   - Shifting value for z coordinates
   - Default: 0

8. **`height : float, optional`**
   - Fixed height for 3D vector features

9. **`height_column : str, optional`**
   - Name of attribute column with feature height
   - Used as: input, dbcolumn, name

10. **`elevation : str | np.ndarray, optional`**
   - Elevation raster map for height extraction
   - Used as: input, raster, name

11. **`method : str, optional`**
   - Sampling interpolation method
   - Allowed values: nearest, bilinear, bicubic
   - nearest: Nearest-neighbor interpolation
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/v.extrude.html#__tabbed_2_3) for all details)*

12. **`scale : float, optional`**
   - Scale factor sampled raster values
   - Default: 1.0

13. **`null_value : float, optional`**
   - Height for sampled raster NULL values

14. **`flags : str, optional`**
   - Allowed values: t
   - t
   - Trace elevation

15. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

16. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

17. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

18. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 18 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/v.extrude.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

v.extrude creates faces, kernels or 3D lines based on input 2D vector
features. Points are converted to 3D vertical lines, lines to faces and
areas to volumes (composition of closed set of faces and kernel).

If elevation parameter is used then 3D vector features follow the
elevation model by using individual elevation values for the vertices.
Height for vertices is interpolated from elevation raster map using
given interpolation method .

---

## See Also

Related tools:
- [`v.transform`](https://grass.osgeo.org/grass-devel/manuals/v.transform.html)
- [`v.drape`](https://grass.osgeo.org/grass-devel/manuals/v.drape.html)
- [`v.to.3d`](https://grass.osgeo.org/grass-devel/manuals/v.to.3d.html)

---

## Authors

Jachym Cepicky, Updated for GRASS 7 by Martin Landa, FBK-irst, Italy and Czech Technical
University in Prague, Czech Republic

---

## Resources

- [Official v.extrude manual](https://grass.osgeo.org/grass-devel/manuals/v.extrude.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/v.extrude.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
