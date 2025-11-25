# i.tasscap

**Category**: imagery

## Description

Performs Tasseled Cap (Kauth Thomas) transformation.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.i_tasscap(input,output,sensor,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str | list[str], required`**
   - For Landsat4-7: bands 1, 2, 3, 4, 5, 7; for Landsat8: bands 2, 3, 4, 5, 6, 7; for MODIS: bands 1, 2, 3, 4, 5, 6, 7; for Sentinel-2: bands 1 to 12, 8A; for Worldview-2: bands 1, 2, 3, 4, 5, 6, 7, 8
   - Used as: input, raster, name

2. **`output : str | type(np.ndarray) | type(np.array) | type(gs.array.array), required`**
   - basename for output raster map(s)
   - Name for output basename raster map(s)
   - Used as: output, raster, basename

3. **`sensor : str, required`**
   - Satellite sensor
   - Allowed values: landsat4_tm, landsat5_tm, landsat7_etm, landsat8_oli, modis, sentinel2, worldview2

4. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

5. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

6. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

7. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None

### Returns

result : grass.tools.support.ToolResult | np.ndarray | tuple[np.ndarray] | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned. If an array type (e.g., np.ndarray) is used for one of the raster outputs, the result will be an array and will have the shape corresponding to the computational region. If an array type is used for more than one raster output, the result will be a tuple of arrays.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

i.tasscap calculates Tasseled Cap (Kauth Thomas, TC) transformation
for Landsat TM data (TM4, TM5, ETM7), MODIS and Sentinel-2 data. The
tasseled cap transformation is effectively a compression method to
reduce multiple spectral data into a few bands. The method was
originally developed for understanding important phenomena of crop
development in spectral space (Kauth and Thomas, 1976).

Tasseled cap coefficients for Landsat 7 ETM+ are at-satellite
reflectance values (C. Huang et al., 2001), the conversion can be
achieved with i.landsat.toar .

The following tasseled cap components are generated:

---

## See Also

Related tools:
- [`i.albedo`](https://grass.osgeo.org/grass-devel/manuals/i.albedo.html)
- [`i.atcorr`](https://grass.osgeo.org/grass-devel/manuals/i.atcorr.html)
- [`i.landsat.toar`](https://grass.osgeo.org/grass-devel/manuals/i.landsat.toar.html)
- [`i.vi`](https://grass.osgeo.org/grass-devel/manuals/i.vi.html)

---

## Authors

Dr. Agustin Lobo, original script, 1997
Markus Neteler, ITC-irst, 2001
Converted to Python by Glynn Clements
Code improvements by Leonardo Perathoner
Sentinel-2 support by Veronica Andreo
Worldview-2 support by Markus Neteler

---

## Resources

- [Official i.tasscap manual](https://grass.osgeo.org/grass-devel/manuals/i.tasscap.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/i.tasscap.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
