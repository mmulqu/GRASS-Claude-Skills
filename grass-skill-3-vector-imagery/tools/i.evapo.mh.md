# i.evapo.mh

**Category**: imagery

## Description

Computes evapotranspiration calculation modified or original Hargreaves formulation, 2001.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.i_evapo_mh(netradiation_diurnal,average_temperature,minimum_temperature,maximum_temperature,precipitation=None,output,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`netradiation_diurnal : str | np.ndarray, required`**
   - Name of input diurnal net radiation raster map [W/m2/d]
   - Used as: input, raster, name

2. **`average_temperature : str | np.ndarray, required`**
   - Name of input average air temperature raster map [C]
   - Used as: input, raster, name

3. **`minimum_temperature : str | np.ndarray, required`**
   - Name of input minimum air temperature raster map [C]
   - Used as: input, raster, name

4. **`maximum_temperature : str | np.ndarray, required`**
   - Name of input maximum air temperature raster map [C]
   - Used as: input, raster, name

5. **`precipitation : str | np.ndarray, optional`**
   - Name of precipitation raster map [mm/month]
   - Disabled for original Hargreaves (1985)
   - Used as: input, raster, name

6. **`output : str | type(np.ndarray) | type(np.array) | type(gs.array.array), required`**
   - Name for output raster map [mm/d]
   - Used as: output, raster, name

7. **`flags : str, optional`**
   - Allowed values: z, h, s
   - z
   - Set negative ETa to zero
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/i.evapo.mh.html#__tabbed_2_3) for all details)*

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


*Showing 10 of 11 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/i.evapo.mh.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | np.ndarray | tuple[np.ndarray] | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned. If an array type (e.g., np.ndarray) is used for one of the raster outputs, the result will be an array and will have the shape corresponding to the computational region. If an array type is used for more than one raster output, the result will be a tuple of arrays.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

i.evapo.mh calculates the reference evapotranspiration (ET) after
Hargreaves et al. (1985), Hargreaves and Samani (1985) and the Modified
Hargreaves version found in Droogers and Allen (2002).

---

## See Also

Related tools:
- [`i.evapo.pt`](https://grass.osgeo.org/grass-devel/manuals/i.evapo.pt.html)
- [`i.evapo.pm`](https://grass.osgeo.org/grass-devel/manuals/i.evapo.pm.html)
- [`i.evapo.time`](https://grass.osgeo.org/grass-devel/manuals/i.evapo.time.html)
- [`r.sun`](https://grass.osgeo.org/grass-devel/manuals/r.sun.html)

---

## Resources

- [Official i.evapo.mh manual](https://grass.osgeo.org/grass-devel/manuals/i.evapo.mh.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/i.evapo.mh.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
