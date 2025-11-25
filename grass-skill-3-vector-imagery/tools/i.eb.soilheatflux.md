# i.eb.soilheatflux

**Category**: imagery

## Description

Soil heat flux approximation (Bastiaanssen, 1995).

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.i_eb_soilheatflux(albedo,ndvi,temperature,netradiation,localutctime,output,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`albedo : str | np.ndarray, required`**
   - Name of albedo raster map [0.0;1.0]
   - Used as: input, raster, name

2. **`ndvi : str | np.ndarray, required`**
   - Name of NDVI raster map [-1.0;+1.0]
   - Used as: input, raster, name

3. **`temperature : str | np.ndarray, required`**
   - Name of Surface temperature raster map [K]
   - Used as: input, raster, name

4. **`netradiation : str | np.ndarray, required`**
   - Name of Net Radiation raster map [W/m2]
   - Used as: input, raster, name

5. **`localutctime : str | np.ndarray, required`**
   - Name of time of satellite overpass raster map [local time in UTC]
   - Used as: input, raster, name

6. **`output : str | type(np.ndarray) | type(np.array) | type(gs.array.array), required`**
   - Name for output raster map
   - Used as: output, raster, name

7. **`flags : str, optional`**
   - Allowed values: r
   - r
   - HAPEX-Sahel empirical correction (Roerink, 1995)

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


*Showing 10 of 11 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/i.eb.soilheatflux.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | np.ndarray | tuple[np.ndarray] | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned. If an array type (e.g., np.ndarray) is used for one of the raster outputs, the result will be an array and will have the shape corresponding to the computational region. If an array type is used for more than one raster output, the result will be a tuple of arrays.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

i.eb.soilheatflux calculates the soil heat flux approximation (g0)
after Bastiaanssen (1995). The main reference for implementation is
Alexandridis, 2009. It takes input of Albedo, NDVI, Surface Skin
temperature, Net Radiation (see r.sun ), time of satellite overpass,
and a flag for the Roerink empirical modification from the HAPEX-Sahel
experiment. The "time of satellite overpass" map can be obtained as
follows:

For Landsat, the overpass map can be computed by using a two-step
method:

---

## See Also

Related tools:
- [`r.sun`](https://grass.osgeo.org/grass-devel/manuals/r.sun.html)
- [`i.albedo`](https://grass.osgeo.org/grass-devel/manuals/i.albedo.html)
- [`i.emissivity`](https://grass.osgeo.org/grass-devel/manuals/i.emissivity.html)
- [`i.eb.hsebal01`](https://grass.osgeo.org/grass-devel/manuals/i.eb.hsebal01.html)
- [`i.eb.evapfr`](https://grass.osgeo.org/grass-devel/manuals/i.eb.evapfr.html)
- [`i.landsat.toar`](https://grass.osgeo.org/grass-devel/manuals/i.landsat.toar.html)

---

## Resources

- [Official i.eb.soilheatflux manual](https://grass.osgeo.org/grass-devel/manuals/i.eb.soilheatflux.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/i.eb.soilheatflux.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
