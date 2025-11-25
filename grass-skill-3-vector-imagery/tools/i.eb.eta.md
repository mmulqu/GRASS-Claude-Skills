# i.eb.eta

**Category**: imagery

## Description

Actual evapotranspiration for diurnal period (Bastiaanssen, 1995).

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.i_eb_eta(netradiationdiurnal="rnetday",evaporativefraction="evapfr",temperature="tempk",output,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`netradiationdiurnal : str | np.ndarray, required`**
   - Name of the diurnal net radiation map [W/m2]
   - Used as: input, raster, name
   - Default: rnetday

2. **`evaporativefraction : str | np.ndarray, required`**
   - Name of the evaporative fraction map [-]
   - Used as: input, raster, name
   - Default: evapfr

3. **`temperature : str | np.ndarray, required`**
   - Name of the surface skin temperature [K]
   - Used as: input, raster, name
   - Default: tempk

4. **`output : str | type(np.ndarray) | type(np.array) | type(gs.array.array), required`**
   - Name of the output actual evapotranspiration layer [mm/d]
   - Used as: output, raster, name

5. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

6. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

7. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

8. **`superquiet : bool, optional`**
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

i.eb.eta calculates the actual evapotranspiration (ETa ; mm/d) for
diurnal period after [1], implemented in [3]. It takes input of
Diurnal Net Radiation (see r.sun ), evaporative fraction (see i.eb.evapfr ) and surface skin temperature.

---

## See Also

Related tools:
- [`r.sun`](https://grass.osgeo.org/grass-devel/manuals/r.sun.html)
- [`i.eb.evapfr`](https://grass.osgeo.org/grass-devel/manuals/i.eb.evapfr.html)
- [`i.eb.netrad`](https://grass.osgeo.org/grass-devel/manuals/i.eb.netrad.html)

---

## Resources

- [Official i.eb.eta manual](https://grass.osgeo.org/grass-devel/manuals/i.eb.eta.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/i.eb.eta.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
