# i.evapo.time

**Category**: imagery

## Description

Computes temporal integration of satellite ET actual (ETa) following the daily ET reference (ETo) from meteorological station(s).

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.i_evapo_time(eta,eta_doy,eto,eto_doy_min,start_period,end_period,output,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`eta : str | list[str], required`**
   - Names of satellite ETa raster maps [mm/d or cm/d]
   - Used as: input, raster, name

2. **`eta_doy : str | list[str], required`**
   - Names of satellite ETa Day of Year (DOY) raster maps [0-400] [-]
   - Used as: input, raster, name

3. **`eto : str | list[str], required`**
   - Names of meteorological station ETo raster maps [0-400] [mm/d or cm/d]
   - Used as: input, raster, name

4. **`eto_doy_min : float, required`**
   - Value of DOY for ETo first day

5. **`start_period : float, required`**
   - Value of DOY for the first day of the period studied

6. **`end_period : float, required`**
   - Value of DOY for the last day of the period studied

7. **`output : str | type(np.ndarray) | type(np.array) | type(gs.array.array), required`**
   - Name for output raster map
   - Used as: output, raster, name

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


*Showing 10 of 11 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/i.evapo.time.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | np.ndarray | tuple[np.ndarray] | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned. If an array type (e.g., np.ndarray) is used for one of the raster outputs, the result will be an array and will have the shape corresponding to the computational region. If an array type is used for more than one raster output, the result will be a tuple of arrays.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

i.evapo.time (i.evapo.time_integration) integrates ETa in time
following a reference ET (typically) from a set of meteorological
stations dataset. Inputs:

Method:

representative days calculation: let assume i belongs to range
[DOYmin;DOYmax]

---

## See Also

Related tools:
- [`i.eb.eta`](https://grass.osgeo.org/grass-devel/manuals/i.eb.eta.html)
- [`i.evapo.mh`](https://grass.osgeo.org/grass-devel/manuals/i.evapo.mh.html)
- [`i.evapo.pt`](https://grass.osgeo.org/grass-devel/manuals/i.evapo.pt.html)
- [`i.evapo.pm`](https://grass.osgeo.org/grass-devel/manuals/i.evapo.pm.html)
- [`r.sun`](https://grass.osgeo.org/grass-devel/manuals/r.sun.html)

---

## Resources

- [Official i.evapo.time manual](https://grass.osgeo.org/grass-devel/manuals/i.evapo.time.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/i.evapo.time.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
