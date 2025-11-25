# r.watershed

**Category**: raster

## Description

Calculates hydrological parameters and RUSLE factors.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_watershed(elevation,depression=None,flow=None,disturbed_land=None,blocking=None,retention=None,threshold=None,max_slope_length=None,accumulation=None,tci=None,spi=None,drainage=None,basin=None,stream=None,half_basin=None,length_slope=None,slope_steepness=None,convergence=5,memory=300,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`elevation : str | np.ndarray, required`**
   - Name of input elevation raster map
   - Used as: input, raster, name

2. **`depression : str | np.ndarray, optional`**
   - Name of input depressions raster map
   - All non-NULL and non-zero cells are considered as real depressions
   - Used as: input, raster, name

3. **`flow : str | np.ndarray, optional`**
   - Name of input raster representing amount of overland flow per cell
   - Used as: input, raster, name

4. **`disturbed_land : str | np.ndarray, optional`**
   - Name of input raster map percent of disturbed land
   - For USLE
   - Used as: input, raster, name

5. **`blocking : str | np.ndarray, optional`**
   - Name of input raster map blocking overland surface flow
   - For USLE. All non-NULL and non-zero cells are considered as blocking terrain.
   - Used as: input, raster, name

6. **`retention : str | np.ndarray, optional`**
   - Name of input raster map with percentages for flow accumulation.
   - Used as: input, raster, name

7. **`threshold : int, optional`**
   - Minimum size of exterior watershed basin

8. **`max_slope_length : float, optional`**
   - Maximum length of surface flow in map units
   - For USLE

9. **`accumulation : str | type(np.ndarray) | type(np.array) | type(gs.array.array), optional`**
   - Name for output accumulation raster map
   - Number of cells that drain through each cell
   - Used as: output, raster, name

10. **`tci : str | type(np.ndarray) | type(np.array) | type(gs.array.array), optional`**
   - Name for output topographic index ln(a / tan(b)) map
   - Used as: output, raster, name

11. **`spi : str | type(np.ndarray) | type(np.array) | type(gs.array.array), optional`**
   - Name for output stream power index a * tan(b)
   - Name for output raster map
   - Used as: output, raster, name

12. **`drainage : str | type(np.ndarray) | type(np.array) | type(gs.array.array), optional`**
   - Name for output drainage direction raster map
   - Directions numbered from 1 to 8
   - Used as: output, raster, name

13. **`basin : str | type(np.ndarray) | type(np.array) | type(gs.array.array), optional`**
   - Name for output basins raster map
   - Used as: output, raster, name

14. **`stream : str | type(np.ndarray) | type(np.array) | type(gs.array.array), optional`**
   - Name for output stream segments raster map
   - Used as: output, raster, name

15. **`half_basin : str | type(np.ndarray) | type(np.array) | type(gs.array.array), optional`**
   - Name for output half basins raster map
   - Each half-basin is given a unique value
   - Used as: output, raster, name

16. **`length_slope : str | type(np.ndarray) | type(np.array) | type(gs.array.array), optional`**
   - Name for output slope length raster map
   - Slope length and steepness (LS) factor for USLE
   - Used as: output, raster, name

17. **`slope_steepness : str | type(np.ndarray) | type(np.array) | type(gs.array.array), optional`**
   - Name for output slope steepness raster map
   - Slope steepness (S) factor for USLE
   - Used as: output, raster, name

18. **`convergence : int, optional`**
   - Convergence factor for MFD (1-10)
   - 1 = most diverging flow, 10 = most converging flow. Recommended: 5
   - Default: 5

19. **`memory : int, optional`**
   - Maximum memory to be used (in MB)
   - Cache size for raster rows
   - Used as: memory in MB

20. **`flags : str, optional`**
   - Allowed values: s, 4, m, a, b
   - s
   - SFD (D8) flow (default is MFD)
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/r.watershed.html#__tabbed_2_3) for all details)*

21. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

22. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

23. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

24. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 24 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/r.watershed.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | np.ndarray | tuple[np.ndarray] | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned. If an array type (e.g., np.ndarray) is used for one of the raster outputs, the result will be an array and will have the shape corresponding to the computational region. If an array type is used for more than one raster output, the result will be a tuple of arrays.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

r.watershed generates a set of maps indicating: 1) flow accumulation,
drainage direction, the location of streams and watershed basins, and 2)
the LS and S factors of the Revised Universal Soil Loss Equation
(RUSLE).

---

## See Also

Related tools:
- [`g.region`](https://grass.osgeo.org/grass-devel/manuals/g.region.html)
- [`r.cost`](https://grass.osgeo.org/grass-devel/manuals/r.cost.html)
- [`r.drain`](https://grass.osgeo.org/grass-devel/manuals/r.drain.html)
- [`r.fillnulls`](https://grass.osgeo.org/grass-devel/manuals/r.fillnulls.html)
- [`r.flow`](https://grass.osgeo.org/grass-devel/manuals/r.flow.html)
- [`r.mask`](https://grass.osgeo.org/grass-devel/manuals/r.mask.html)
- [`r.neighbors`](https://grass.osgeo.org/grass-devel/manuals/r.neighbors.html)
- [`r.param.scale`](https://grass.osgeo.org/grass-devel/manuals/r.param.scale.html)
- [`r.resamp.interp`](https://grass.osgeo.org/grass-devel/manuals/r.resamp.interp.html)
- [`r.terraflow`](https://grass.osgeo.org/grass-devel/manuals/r.terraflow.html)
- [`r.topidx`](https://grass.osgeo.org/grass-devel/manuals/r.topidx.html)
- [`r.water.outlet`](https://grass.osgeo.org/grass-devel/manuals/r.water.outlet.html)
- [`r.stream.extract`](https://grass.osgeo.org/grass-devel/manuals/r.stream.extract.html)

---

## Authors

Original version: Charles Ehlschlaeger, U.S. Army Construction
Engineering Research Laboratory Faster sorting algorithm and MFD support: Markus Metz
\<markus.metz.giswork at gmail.com> Retention for flow distribution by Andreas Gericke (IGB Berlin)

---

## Resources

- [Official r.watershed manual](https://grass.osgeo.org/grass-devel/manuals/r.watershed.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.watershed.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
