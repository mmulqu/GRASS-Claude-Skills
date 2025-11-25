# r.mapcalc.simple

**Category**: raster

## Description

Calculates a new raster map from a simple r.mapcalc expression.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_mapcalc_simple(expression,a=None,b=None,c=None,d=None,e=None,f=None,output,seed=None,nprocs=0,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`expression : str, required`**
   - Formula (e.g. A-B or A*C+B)

2. **`a : str | np.ndarray, optional`**
   - Name of input A raster map
   - Used as: input, raster, name

3. **`b : str | np.ndarray, optional`**
   - Name of input B raster map
   - Used as: input, raster, name

4. **`c : str | np.ndarray, optional`**
   - Name of input C raster map
   - Used as: input, raster, name

5. **`d : str | np.ndarray, optional`**
   - Name of input D raster map
   - Used as: input, raster, name

6. **`e : str | np.ndarray, optional`**
   - Name of input E raster map
   - Used as: input, raster, name

7. **`f : str | np.ndarray, optional`**
   - Name of input F raster map
   - Used as: input, raster, name

8. **`output : str | type(np.ndarray) | type(np.array) | type(gs.array.array), required`**
   - Name for output raster map
   - Used as: output, raster, name

9. **`seed : int, optional`**
   - Seed for rand() function

10. **`nprocs : int, optional`**
   - Number of threads for parallel computing
   - 0: use OpenMP default; >0: use nprocs; <0: use MAX-nprocs
   - Default: 0

11. **`flags : str, optional`**
   - Allowed values: s, q, c
   - s
   - Generate random seed (result is non-deterministic)
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/r.mapcalc.simple.html#__tabbed_2_3) for all details)*

12. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

13. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

14. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

15. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 15 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/r.mapcalc.simple.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | np.ndarray | tuple[np.ndarray] | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned. If an array type (e.g., np.ndarray) is used for one of the raster outputs, the result will be an array and will have the shape corresponding to the computational region. If an array type is used for more than one raster output, the result will be a tuple of arrays.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

r.mapcalc.simple provides a wrapper to r.mapcalc . Up to 6 maps can
be combined using simple expressions.

The general syntax for the expression follows r.mapcalc expression format, for example, A + B or exp(A + B) are valid. The variables A, B, ..., F represent raster maps
which are provided as options a , b , ..., f .

The result name, i.e. the output raster map, is provided using the
option output and, unlike r.mapcalc it is not part of the
expression.

This module is meant for convenience (for users and programmers) while
the r.mapcalc module is a better choice for more complex expressions
and advanced usage.

---

## See Also

Related tools:
- [`r.mapcalc`](https://grass.osgeo.org/grass-devel/manuals/r.mapcalc.html)
- [`r3.mapcalc`](https://grass.osgeo.org/grass-devel/manuals/r3.mapcalc.html)
- [`t.rast.mapcalc`](https://grass.osgeo.org/grass-devel/manuals/t.rast.mapcalc.html)
- [`g.region`](https://grass.osgeo.org/grass-devel/manuals/g.region.html)

---

## Authors

Vaclav Petras, NCSU GeoForAll
Lab Michael Barton, Arizona State University (updated to GRASS 5.7) R. Brunzema (original 5.0 Bash version)

---

## Resources

- [Official r.mapcalc.simple manual](https://grass.osgeo.org/grass-devel/manuals/r.mapcalc.simple.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.mapcalc.simple.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
