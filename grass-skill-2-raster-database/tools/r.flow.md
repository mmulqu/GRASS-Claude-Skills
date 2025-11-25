# r.flow

**Category**: raster

## Description

Constructs flowlines. Computes flowlines, flowpath lengths, and flowaccumulation (contributing areas) from a elevation raster map.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_flow(elevation,aspect=None,barrier=None,skip=None,bound=None,flowline=None,flowlength=None,flowaccumulation=None,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`elevation : str | np.ndarray, required`**
   - Name of input elevation raster map
   - Used as: input, raster, name

2. **`aspect : str | np.ndarray, optional`**
   - Name of input aspect raster map
   - Used as: input, raster, name

3. **`barrier : str | np.ndarray, optional`**
   - Name of input barrier raster map
   - Used as: input, raster, name

4. **`skip : int, optional`**
   - Number of cells between flowlines

5. **`bound : int, optional`**
   - Maximum number of segments per flowline

6. **`flowline : str, optional`**
   - Name for output flow line vector map
   - Used as: output, vector, name

7. **`flowlength : str | type(np.ndarray) | type(np.array) | type(gs.array.array), optional`**
   - Name for output flow path length raster map
   - Used as: output, raster, name

8. **`flowaccumulation : str | type(np.ndarray) | type(np.array) | type(gs.array.array), optional`**
   - Name for output flow accumulation raster map
   - Used as: output, raster, name

9. **`flags : str, optional`**
   - Allowed values: u, 3, m
   - u
   - Compute upslope flowlines instead of default downhill flowlines
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/r.flow.html#__tabbed_2_3) for all details)*

10. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

11. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

12. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

13. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 13 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/r.flow.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | np.ndarray | tuple[np.ndarray] | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned. If an array type (e.g., np.ndarray) is used for one of the raster outputs, the result will be an array and will have the shape corresponding to the computational region. If an array type is used for more than one raster output, the result will be a tuple of arrays.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

r.flow generates flowlines using a combined raster-vector approach
(see Mitasova and Hofierka
1993 and Mitasova et al.
1995 ) from
an input elevation raster map (integer or floating point), and
optionally an input aspect raster map and/or an input barrier raster map.

There are three possible output raster maps which can be produced in any
combination simultaneously: a vector map flowline of flowlines, a
raster map flowlength of flowpath lengths, and a raster map flowaccumulation of flowline densities (which are equal upslope
contributed areas per unit width, when multiplied by resolution).

---

## See Also

Related tools:
- [`r.basins.fill`](https://grass.osgeo.org/grass-devel/manuals/r.basins.fill.html)
- [`r.drain`](https://grass.osgeo.org/grass-devel/manuals/r.drain.html)
- [`r.fill.dir`](https://grass.osgeo.org/grass-devel/manuals/r.fill.dir.html)
- [`r.water.outlet`](https://grass.osgeo.org/grass-devel/manuals/r.water.outlet.html)
- [`r.watershed`](https://grass.osgeo.org/grass-devel/manuals/r.watershed.html)
- [`v.category`](https://grass.osgeo.org/grass-devel/manuals/v.category.html)
- [`v.to.rast`](https://grass.osgeo.org/grass-devel/manuals/v.to.rast.html)

---

## Authors

Original version of program: Maros Zlocha and Jaroslav Hofierka,
Comenius University, Bratislava, Slovakia
The version of the program (adapted for GRASS 5.0) : Joshua Caplan,
Mark Ruesink, Helena Mitasova, University of Illinois at
Urbana-Champaign with support from USA CERL. GMSL/University of
Illinois at
Urbana-Champaign

---

## Resources

- [Official r.flow manual](https://grass.osgeo.org/grass-devel/manuals/r.flow.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.flow.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
