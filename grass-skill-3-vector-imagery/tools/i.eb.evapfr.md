# i.eb.evapfr

**Category**: imagery

## Description

Computes evaporative fraction and root zone soil moisture.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.i_eb_evapfr(netradiation,soilheatflux,sensibleheatflux,evaporativefraction,soilmoisture=None,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`netradiation : str | np.ndarray, required`**
   - Name of Net Radiation raster map [W/m2]
   - Used as: input, raster, name

2. **`soilheatflux : str | np.ndarray, required`**
   - Name of soil heat flux raster map [W/m2]
   - Used as: input, raster, name

3. **`sensibleheatflux : str | np.ndarray, required`**
   - Name of sensible heat flux raster map [W/m2]
   - Used as: input, raster, name

4. **`evaporativefraction : str | type(np.ndarray) | type(np.array) | type(gs.array.array), required`**
   - Name for output evaporative fraction raster map
   - Used as: output, raster, name

5. **`soilmoisture : str | type(np.ndarray) | type(np.array) | type(gs.array.array), optional`**
   - Name for output root zone soil moisture raster map
   - Used as: output, raster, name

6. **`flags : str, optional`**
   - Allowed values: m
   - m
   - Root zone soil moisture output (Makin, Molden and Bastiaanssen, 2001)

7. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

8. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

9. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

10. **`superquiet : bool, optional`**
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

i.eb.evapfr calculates the evaporative fraction after Bastiaanssen
1995. The main implementation follows Alexandridis et al. (2009). The
module takes as input the net radiation (see r.sun , i.eb.netrad ),
soil heat flux (see i.eb.soilheatflux ) and sensible heat flux (see i.eb.hsebal01 ). A flag adds a root zone empirical soil moisture output
from the article of Bastiaanssen, et al. (2000).

---

## See Also

Related tools:
- [`i.eb.hsebal01`](https://grass.osgeo.org/grass-devel/manuals/i.eb.hsebal01.html)
- [`i.eb.netrad`](https://grass.osgeo.org/grass-devel/manuals/i.eb.netrad.html)
- [`i.eb.soilheatflux`](https://grass.osgeo.org/grass-devel/manuals/i.eb.soilheatflux.html)
- [`r.sun`](https://grass.osgeo.org/grass-devel/manuals/r.sun.html)

---

## Resources

- [Official i.eb.evapfr manual](https://grass.osgeo.org/grass-devel/manuals/i.eb.evapfr.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/i.eb.evapfr.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
