# i.evapo.pm

**Category**: imagery

## Description

Computes potential evapotranspiration calculation with hourly Penman-Monteith.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.i_evapo_pm(elevation,temperature,relativehumidity,windspeed,netradiation,cropheight,output,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`elevation : str | np.ndarray, required`**
   - Name of input elevation raster map [m a.s.l.]
   - Used as: input, raster, name

2. **`temperature : str | np.ndarray, required`**
   - Name of input temperature raster map [C]
   - Used as: input, raster, name

3. **`relativehumidity : str | np.ndarray, required`**
   - Name of input relative humidity raster map [%]
   - Used as: input, raster, name

4. **`windspeed : str | np.ndarray, required`**
   - Name of input wind speed raster map [m/s]
   - Used as: input, raster, name

5. **`netradiation : str | np.ndarray, required`**
   - Name of input net solar radiation raster map [MJ/m2/h]
   - Used as: input, raster, name

6. **`cropheight : str | np.ndarray, required`**
   - Name of input crop height raster map [m]
   - Used as: input, raster, name

7. **`output : str | type(np.ndarray) | type(np.array) | type(gs.array.array), required`**
   - Name for output raster map [mm/h]
   - Used as: output, raster, name

8. **`flags : str, optional`**
   - Allowed values: z, n
   - z
   - Set negative evapotranspiration to zero
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/i.evapo.pm.html#__tabbed_2_3) for all details)*

9. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

10. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

11. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

12. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 12 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/i.evapo.pm.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | np.ndarray | tuple[np.ndarray] | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned. If an array type (e.g., np.ndarray) is used for one of the raster outputs, the result will be an array and will have the shape corresponding to the computational region. If an array type is used for more than one raster output, the result will be a tuple of arrays.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

i.evapo.pm , given the vegetation height (hc), humidity (RU), wind
speed at two meters height (WS), temperature (T), digital terrain model
(DEM), and net radiation (NSR) raster input maps, calculates the
potential evapotranspiration map (EPo).

Optionally the user can activate a flag (-z) that allows him setting to
zero all of the negative evapotranspiration cells; in fact these
negative values motivated by the condensation of the air water vapour
content, are sometime undesired because they can produce computational
problems. The usage of the flag -n detect that the module is run in
night hours and the appropriate soil heat flux is calculated.

The algorithm implements well known approaches: the hourly
Penman-Monteith method as presented in Allen et al. (1998) for land
surfaces and the Penman method (Penman, 1948) for water surfaces.

Land and water surfaces are idenfyied by Vh:

For more details on the algorithms see [1,2,3].

---

## See Also

Related tools:
- [`i.evapo.mh`](https://grass.osgeo.org/grass-devel/manuals/i.evapo.mh.html)
- [`i.evapo.time`](https://grass.osgeo.org/grass-devel/manuals/i.evapo.time.html)
- [`r.sun`](https://grass.osgeo.org/grass-devel/manuals/r.sun.html)
- [`r.mapcalc`](https://grass.osgeo.org/grass-devel/manuals/r.mapcalc.html)

---

## Authors

Original version of program: The HydroFOSS project, 2006, IST-SUPSI.
( http://istgis.ist.supsi.ch:8001/geomatica/index.php?id=1 ) Massimiliano
Cannata, Scuola Universitaria Professionale della Svizzera Italiana -
Istituto Scienze della Terra Maria A. Brovelli, Politecnico di Milano - Polo regionale di Como
Contact: Massimiliano Cannata

---

## Resources

- [Official i.evapo.pm manual](https://grass.osgeo.org/grass-devel/manuals/i.evapo.pm.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/i.evapo.pm.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
