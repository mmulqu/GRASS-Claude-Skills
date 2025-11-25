# r.import

**Category**: raster

## Description

Imports raster data into a GRASS raster map using GDAL library and reprojects on the fly.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_import(input,band=None,memory=300,output=None,resample="nearest",extent="input",resolution="estimated",resolution_value=None,title=None,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str, required`**
   - Name of GDAL dataset to be imported
   - Used as: input, file, name

2. **`band : int | list[int] | str, optional`**
   - Input band(s) to select (default is all bands)

3. **`memory : int, optional`**
   - Maximum memory to be used (in MB)
   - Cache size for raster rows
   - Used as: memory in MB

4. **`output : str | type(np.ndarray) | type(np.array) | type(gs.array.array), optional`**
   - Name for output raster map
   - Used as: output, raster, name

5. **`resample : str, optional`**
   - Resampling method to use for reprojection
   - Allowed values: nearest, bilinear, bicubic, lanczos, bilinear_f, bicubic_f, lanczos_f
   - nearest: nearest neighbor
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/r.import.html#__tabbed_2_3) for all details)*

6. **`extent : str, optional`**
   - Output raster map extent
   - Allowed values: input, region
   - input: extent of input map
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/r.import.html#__tabbed_2_3) for all details)*

7. **`resolution : str, optional`**
   - Resolution of output raster map (default: estimated)
   - Allowed values: estimated, value, region
   - estimated: estimated resolution
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/r.import.html#__tabbed_2_3) for all details)*

8. **`resolution_value : float, optional`**
   - Resolution of output raster map (use with option resolution=value)

9. **`title : str, optional`**
   - Title for resultant raster map
   - Used as: phrase

10. **`flags : str, optional`**
   - Allowed values: e, n, l, o
   - e
   - Estimate resolution only
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/r.import.html#__tabbed_2_3) for all details)*

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


*Showing 10 of 14 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/r.import.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | np.ndarray | tuple[np.ndarray] | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned. If an array type (e.g., np.ndarray) is used for one of the raster outputs, the result will be an array and will have the shape corresponding to the computational region. If an array type is used for more than one raster output, the result will be a tuple of arrays.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

r.import imports a map or selected bands from a GDAL raster datasource
into the current project (previously called location) and mapset. If the
coordinate reference system (CRS) of the input does not match the CRS of
the project, the input is reprojected into the current project. If the
CRS of the input does match the CRS of the project, the input is
imported directly with r.in.gdal .

---

## See Also

Related tools:
- [`r.in.gdal`](https://grass.osgeo.org/grass-devel/manuals/r.in.gdal.html)
- [`r.proj`](https://grass.osgeo.org/grass-devel/manuals/r.proj.html)

---

## Authors

Markus Metz Improvements: Martin Landa, Anna Petrasova

---

## Resources

- [Official r.import manual](https://grass.osgeo.org/grass-devel/manuals/r.import.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.import.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
