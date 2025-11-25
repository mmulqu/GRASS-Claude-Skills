# i.landsat.toar

**Category**: imagery

## Description

Calculates top-of-atmosphere radiance or reflectance and temperature for Landsat MSS/TM/ETM+/OLI

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.i_landsat_toar(input,output,metfile=None,sensor=None,method="uncorrected",date=None,sun_elevation=None,product_date=None,gain=None,percent=0.01,pixel=1000,rayleigh=0.0,lsatmet=None,scale=1.0,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str | np.ndarray, required`**
   - Base name of input raster bands
   - Example: 'B.' for B.1, B.2, ...
   - Used as: input, raster, basename

2. **`output : str | type(np.ndarray) | type(np.array) | type(gs.array.array), required`**
   - Prefix for output raster maps
   - Example: 'B.toar.' generates B.toar.1, B.toar.2, ...
   - Used as: output, raster, basename

3. **`metfile : str | io.StringIO, optional`**
   - Name of Landsat metadata file (.met or MTL.txt)
   - Used as: input, file, name

4. **`sensor : str, optional`**
   - Spacecraft sensor
   - Required only if 'metfile' not given (recommended for sanity)
   - Allowed values: mss1, mss2, mss3, mss4, mss5, tm4, tm5, tm7, oli8
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/i.landsat.toar.html#__tabbed_2_3) for all details)*

5. **`method : str, optional`**
   - Atmospheric correction method
   - Allowed values: uncorrected, dos1, dos2, dos2b, dos3, dos4
   - Default: uncorrected

6. **`date : str, optional`**
   - Image acquisition date (yyyy-mm-dd)
   - Required only if 'metfile' not given
   - Used as: yyyy-mm-dd

7. **`sun_elevation : float, optional`**
   - Sun elevation in degrees
   - Required only if 'metfile' not given

8. **`product_date : str, optional`**
   - Image creation date (yyyy-mm-dd)
   - Required only if 'metfile' not given
   - Used as: yyyy-mm-dd

9. **`gain : str, optional`**
   - Gain (H/L) of all Landsat ETM+ bands (1-5,61,62,7,8)
   - Required only if 'metfile' not given

10. **`percent : float, optional`**
   - Percent of solar radiance in path radiance
   - Required only if 'method' is any DOS
   - Default: 0.01

11. **`pixel : int, optional`**
   - Minimum pixels to consider digital number as dark object
   - Required only if 'method' is any DOS
   - Default: 1000

12. **`rayleigh : float, optional`**
   - Rayleigh atmosphere (diffuse sky irradiance)
   - Required only if 'method' is DOS3
   - Default: 0.0

13. **`lsatmet : str | list[str], optional`**
   - return value stored for a given metadata
   - Required only if 'metfile' and -p given
   - Allowed values: number, creation, date, sun_elev, sensor, bands, sunaz, time
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/i.landsat.toar.html#__tabbed_2_3) for all details)*

14. **`scale : float, optional`**
   - Scale factor for output
   - Default: 1.0

15. **`flags : str, optional`**
   - Allowed values: r, n, p
   - r
   - Output at-sensor radiance instead of reflectance for all bands
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/i.landsat.toar.html#__tabbed_2_3) for all details)*

16. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

17. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

18. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

19. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 19 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/i.landsat.toar.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | np.ndarray | tuple[np.ndarray] | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned. If an array type (e.g., np.ndarray) is used for one of the raster outputs, the result will be an array and will have the shape corresponding to the computational region. If an array type is used for more than one raster output, the result will be a tuple of arrays.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

i.landsat.toar is used to transform the calibrated digital number of
Landsat imagery products to top-of-atmosphere radiance or
top-of-atmosphere reflectance and temperature (band 6 of the sensors TM
and ETM+). Optionally, it can be used to calculate the at-surface
radiance or reflectance with atmospheric correction (DOS method).

Usually, to do so the production date, the acquisition date, and the
solar elevation are needed. Moreover, for Landsat-7 ETM+ it is also
needed the gain (high or low) of the nine respective bands.

Optionally (recommended), the data can be read from metadata file (.met
or MTL.txt) for all Landsat MSS, TM, ETM+ and OLI/TIRS. However, if the
solar elevation is given the value of the metadata file is overwritten.
This is necessary when the data in the .met file is incorrect or not
accurate. Also, if acquisition or production dates are not found in the
metadata file then the command line values are used.

Attention : Any null value or smaller than QCALmin in the input
raster is set to null in the output raster and it is not included in the
equations.

Attention : This module does not respect the current region
settings, in order to have the largest possible sample of pixels from
where to get the darkest one of the scene and perform the DOS
correction. To limit the results to a custom region, the user is advised
to clip the results (with r.clip ,
for instance) or to define the region first, import the images with
region cropping, and then running the module.

---

## See Also

Related tools:
- [`i.atcorr`](https://grass.osgeo.org/grass-devel/manuals/i.atcorr.html)
- [`i.colors.enhance`](https://grass.osgeo.org/grass-devel/manuals/i.colors.enhance.html)
- [`r.mapcalc`](https://grass.osgeo.org/grass-devel/manuals/r.mapcalc.html)
- [`r.in.gdal`](https://grass.osgeo.org/grass-devel/manuals/r.in.gdal.html)

---

## Resources

- [Official i.landsat.toar manual](https://grass.osgeo.org/grass-devel/manuals/i.landsat.toar.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/i.landsat.toar.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
