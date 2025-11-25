# i.biomass

**Category**: imagery

## Description

Computes biomass growth, precursor of crop yield calculation.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.i_biomass(fpar,lightuse_efficiency,latitude,dayofyear,transmissivity_singleway,water_availability,output,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`fpar : str | np.ndarray, required`**
   - Name of fPAR raster map
   - Used as: input, raster, name

2. **`lightuse_efficiency : str | np.ndarray, required`**
   - Name of light use efficiency raster map (UZB:cotton=1.9)
   - Used as: input, raster, name

3. **`latitude : str | np.ndarray, required`**
   - Name of degree latitude raster map [dd.ddd]
   - Used as: input, raster, name

4. **`dayofyear : str | np.ndarray, required`**
   - Name of Day of Year raster map [1-366]
   - Used as: input, raster, name

5. **`transmissivity_singleway : str | np.ndarray, required`**
   - Name of single-way transmissivity raster map [0.0-1.0]
   - Used as: input, raster, name

6. **`water_availability : str | np.ndarray, required`**
   - Value of water availability raster map [0.0-1.0]
   - Used as: input, raster, name

7. **`output : str | type(np.ndarray) | type(np.array) | type(gs.array.array), required`**
   - Name for output daily biomass growth raster map [kg/ha/d]
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


*Showing 10 of 11 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/i.biomass.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | np.ndarray | tuple[np.ndarray] | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned. If an array type (e.g., np.ndarray) is used for one of the raster outputs, the result will be an array and will have the shape corresponding to the computational region. If an array type is used for more than one raster output, the result will be a tuple of arrays.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

i.biomass calculates the biomass growth for a day after [1][2].
Input:

---

## See Also

Related tools:
- [`i.eb.evapfr`](https://grass.osgeo.org/grass-devel/manuals/i.eb.evapfr.html)
- [`r.latlong`](https://grass.osgeo.org/grass-devel/manuals/r.latlong.html)
- [`r.sun`](https://grass.osgeo.org/grass-devel/manuals/r.sun.html)

---

## Resources

- [Official i.biomass manual](https://grass.osgeo.org/grass-devel/manuals/i.biomass.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/i.biomass.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
