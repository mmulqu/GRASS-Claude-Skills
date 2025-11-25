# i.evapo.pt

**Category**: imagery

## Description

Computes evapotranspiration calculation Priestley and Taylor formulation, 1972.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.i_evapo_pt(net_radiation,soil_heatflux,air_temperature,atmospheric_pressure,priestley_taylor_coeff=1.26,output,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`net_radiation : str | np.ndarray, required`**
   - Name of input net radiation raster map [W/m2]
   - Used as: input, raster, name

2. **`soil_heatflux : str | np.ndarray, required`**
   - Name of input soil heat flux raster map [W/m2]
   - Used as: input, raster, name

3. **`air_temperature : str | np.ndarray, required`**
   - Name of input air temperature raster map [K]
   - Used as: input, raster, name

4. **`atmospheric_pressure : str | np.ndarray, required`**
   - Name of input atmospheric pressure raster map [millibars]
   - Used as: input, raster, name

5. **`priestley_taylor_coeff : float, required`**
   - Priestley-Taylor coefficient
   - Default: 1.26

6. **`output : str | type(np.ndarray) | type(np.array) | type(gs.array.array), required`**
   - Name of output evapotranspiration raster map [mm/d]
   - Used as: output, raster, name

7. **`flags : str, optional`**
   - Allowed values: z
   - z
   - Set negative ETa to zero

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


*Showing 10 of 11 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/i.evapo.pt.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | np.ndarray | tuple[np.ndarray] | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned. If an array type (e.g., np.ndarray) is used for one of the raster outputs, the result will be an array and will have the shape corresponding to the computational region. If an array type is used for more than one raster output, the result will be a tuple of arrays.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

i.evapo.pt Calculates the diurnal evapotranspiration after Prestley
and Taylor (1972). The Priestley-Taylor model (Priestley and Taylor,
1972) is a modification of Penman's more theoretical equation.

---

## See Also

Related tools:
- [`i.evapo.mh`](https://grass.osgeo.org/grass-devel/manuals/i.evapo.mh.html)
- [`i.evapo.pm`](https://grass.osgeo.org/grass-devel/manuals/i.evapo.pm.html)
- [`i.evapo.time`](https://grass.osgeo.org/grass-devel/manuals/i.evapo.time.html)
- [`i.eb.netrad`](https://grass.osgeo.org/grass-devel/manuals/i.eb.netrad.html)
- [`r.sun`](https://grass.osgeo.org/grass-devel/manuals/r.sun.html)

---

## Resources

- [Official i.evapo.pt manual](https://grass.osgeo.org/grass-devel/manuals/i.evapo.pt.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/i.evapo.pt.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
