# v.drape

**Category**: vector

## Description

Converts 2D vector features to 3D by sampling of elevation raster map.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.v_drape(input,layer="-1",cats=None,where=None,type="point,line,boundary,centroid",output,elevation,method="nearest",scale=1.0,null_value=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
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
   - Allowed values: point, line, boundary, centroid
   - Default: point,line,boundary,centroid

6. **`output : str, required`**
   - Name for output vector map
   - Used as: output, vector, name

7. **`elevation : str | np.ndarray, required`**
   - Elevation raster map for height extraction
   - Used as: input, raster, name

8. **`method : str, optional`**
   - Sampling interpolation method
   - Allowed values: nearest, bilinear, bicubic
   - nearest: Nearest-neighbor interpolation
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/v.drape.html#__tabbed_2_3) for all details)*

9. **`scale : float, optional`**
   - Scale factor sampled raster values
   - Default: 1.0

10. **`null_value : float, optional`**
   - Height for sampled raster NULL values

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


*Showing 10 of 14 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/v.drape.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

v.drape converts 2D/3D vector data into 3D vector format via sampling
of an elevation surface. Three sampling algorithms adapted from v.sample were incorporated into this module: nearest
neighbor, bilinear, and cubic convultion.

v.drape will skip vector features outside of current computational
region or where raster map has NULL value. It's possible to include all
vector features by specifying height value that will be assigned to
verticles whose values can not be determined from raster map.

---

## See Also

Related tools:
- [`v.extrude`](https://grass.osgeo.org/grass-devel/manuals/v.extrude.html)
- [`v.to.3d`](https://grass.osgeo.org/grass-devel/manuals/v.to.3d.html)
- [`r.out.pov`](https://grass.osgeo.org/grass-devel/manuals/r.out.pov.html)
- [`v.in.region`](https://grass.osgeo.org/grass-devel/manuals/v.in.region.html)
- [`v.out.pov`](https://grass.osgeo.org/grass-devel/manuals/v.out.pov.html)
- [`v.overlay`](https://grass.osgeo.org/grass-devel/manuals/v.overlay.html)
- [`v.split`](https://grass.osgeo.org/grass-devel/manuals/v.split.html)
- [`v.what.rast`](https://grass.osgeo.org/grass-devel/manuals/v.what.rast.html)

---

## Authors

Dylan Beaudette, University of California at Davis. Updated for GRASS 7 by Martin Landa, Czech Technical University in
Prague, Czech Republic

---

## Resources

- [Official v.drape manual](https://grass.osgeo.org/grass-devel/manuals/v.drape.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/v.drape.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
