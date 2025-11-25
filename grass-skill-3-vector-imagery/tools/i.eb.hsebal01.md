# i.eb.hsebal01

**Category**: imagery

## Description

Computes sensible heat flux iteration SEBAL 01.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.i_eb_hsebal01(netradiation,soilheatflux,aerodynresistance,temperaturemeansealevel,vapourpressureactual,frictionvelocitystar=0.32407,row_wet_pixel=None,column_wet_pixel=None,row_dry_pixel=None,column_dry_pixel=None,output,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`netradiation : str | np.ndarray, required`**
   - Name of instantaneous net radiation raster map [W/m2]
   - Used as: input, raster, name

2. **`soilheatflux : str | np.ndarray, required`**
   - Name of instantaneous soil heat flux raster map [W/m2]
   - Used as: input, raster, name

3. **`aerodynresistance : str | np.ndarray, required`**
   - Name of aerodynamic resistance to heat momentum raster map [s/m]
   - Used as: input, raster, name

4. **`temperaturemeansealevel : str | np.ndarray, required`**
   - Name of altitude corrected surface temperature raster map [K]
   - Used as: input, raster, name

5. **`vapourpressureactual : str | np.ndarray, required`**
   - Name of the actual vapour pressure (e_act) map [KPa]
   - Used as: input, raster, name

6. **`frictionvelocitystar : float, required`**
   - Value of the height independent friction velocity (u*) [m/s]
   - Default: 0.32407

7. **`row_wet_pixel : float, optional`**
   - Row value of the wet pixel

8. **`column_wet_pixel : float, optional`**
   - Column value of the wet pixel

9. **`row_dry_pixel : float, optional`**
   - Row value of the dry pixel

10. **`column_dry_pixel : float, optional`**
   - Column value of the dry pixel

11. **`output : str | type(np.ndarray) | type(np.array) | type(gs.array.array), required`**
   - Name for output sensible heat flux raster map [W/m2]
   - Used as: output, raster, name

12. **`flags : str, optional`**
   - Allowed values: a, c
   - a
   - Automatic wet/dry pixel (careful!)
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/i.eb.hsebal01.html#__tabbed_2_3) for all details)*

13. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

14. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

15. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

16. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 16 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/i.eb.hsebal01.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | np.ndarray | tuple[np.ndarray] | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned. If an array type (e.g., np.ndarray) is used for one of the raster outputs, the result will be an array and will have the shape corresponding to the computational region. If an array type is used for more than one raster output, the result will be a tuple of arrays.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

i.eb.hsebal01 will calculate the sensible heat flux map (h0), given
both maps of Net Radiation and soil Heat flux (Rn, g0) at instantaneous
time, the surface roughness (z0m), a map of the altitude corrected
temperature (t0dem), a point data of the frictional velocity (u*), a
value of actual vapour pressure (ea[KPa]) and the (x,y) pairs for wet
and dry pixels. Full process will need those:

(for time integration: i.evapo.time_integration )

i.eb.hsebal01 performs the computation of sensible heat flux [W/m2] after Bastiaanssen, 1995 in [1], used in this form in 2001 by
[2]. Implemented in this code in [3].

---

## See Also

Related tools:
- [`i.eb.soilheatflux`](https://grass.osgeo.org/grass-devel/manuals/i.eb.soilheatflux.html)
- [`i.eb.evapfr`](https://grass.osgeo.org/grass-devel/manuals/i.eb.evapfr.html)

---

## Resources

- [Official i.eb.hsebal01 manual](https://grass.osgeo.org/grass-devel/manuals/i.eb.hsebal01.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/i.eb.hsebal01.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
