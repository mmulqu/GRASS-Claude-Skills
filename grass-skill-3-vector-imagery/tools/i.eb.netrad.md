# i.eb.netrad

**Category**: imagery

## Description

Net radiation approximation (Bastiaanssen, 1995).

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.i_eb_netrad(albedo,ndvi,temperature,localutctime,temperaturedifference2m,emissivity,transmissivity_singleway,dayofyear,sunzenithangle,output,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`albedo : str | np.ndarray, required`**
   - Name of albedo raster map [0.0;1.0]
   - Used as: input, raster, name

2. **`ndvi : str | np.ndarray, required`**
   - Name of NDVI raster map [-1.0;+1.0]
   - Used as: input, raster, name

3. **`temperature : str | np.ndarray, required`**
   - Name of surface temperature raster map [K]
   - Used as: input, raster, name

4. **`localutctime : str | np.ndarray, required`**
   - Name of time of satellite overpass raster map [local time in UTC]
   - Used as: input, raster, name

5. **`temperaturedifference2m : str | np.ndarray, required`**
   - Name of the difference map of temperature from surface skin to about 2 m height [K]
   - Used as: input, raster, name

6. **`emissivity : str | np.ndarray, required`**
   - Name of the emissivity map [-]
   - Used as: input, raster, name

7. **`transmissivity_singleway : str | np.ndarray, required`**
   - Name of the single-way atmospheric transmissivitymap [-]
   - Used as: input, raster, name

8. **`dayofyear : str | np.ndarray, required`**
   - Name of the Day Of Year (DOY) map [-]
   - Used as: input, raster, name

9. **`sunzenithangle : str | np.ndarray, required`**
   - Name of the sun zenith angle map [degrees]
   - Used as: input, raster, name

10. **`output : str | type(np.ndarray) | type(np.array) | type(gs.array.array), required`**
   - Name of the output net radiation layer
   - Used as: output, raster, name

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


*Showing 10 of 14 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/i.eb.netrad.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | np.ndarray | tuple[np.ndarray] | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned. If an array type (e.g., np.ndarray) is used for one of the raster outputs, the result will be an array and will have the shape corresponding to the computational region. If an array type is used for more than one raster output, the result will be a tuple of arrays.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

i.eb.netrad calculates the net radiation at the time of satellite
overpass, the way it is in the SEBAL model of Bastiaanssen (1995). It
takes input of Albedo, NDVI, Surface Skin temperature, time of satellite
overpass, surface emissivity, difference of temperature from surface
skin and about 2 m height (dT), instantaneous satellite overpass
single-way atmospheric transmissivity (tsw), Day of Year (DOY), and sun
zenith angle.

---

## See Also

Related tools:
- [`i.eb.soilheatflux`](https://grass.osgeo.org/grass-devel/manuals/i.eb.soilheatflux.html)
- [`i.eb.hsebal01`](https://grass.osgeo.org/grass-devel/manuals/i.eb.hsebal01.html)
- [`i.albedo`](https://grass.osgeo.org/grass-devel/manuals/i.albedo.html)

---

## Resources

- [Official i.eb.netrad manual](https://grass.osgeo.org/grass-devel/manuals/i.eb.netrad.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/i.eb.netrad.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
