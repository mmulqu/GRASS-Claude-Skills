# r.surf.random

**Category**: raster

## Description

Produces a raster surface map of uniform random deviates with defined range.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_surf_random(output,min=0,max=100,seed=None,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`output : str | type(np.ndarray) | type(np.array) | type(gs.array.array), required`**
   - Name for output raster map
   - Used as: output, raster, name

2. **`min : float, optional`**
   - Minimum random value
   - Default: 0

3. **`max : float, optional`**
   - Maximum random value
   - Default: 100

4. **`seed : int, optional`**
   - Seed value for the random number generator
   - Using the same seed ensures identical results, while a randomly generated seed produces different outcomes in each run.

5. **`flags : str, optional`**
   - Allowed values: i
   - i
   - Create an integer raster map

6. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

7. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

8. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

9. **`superquiet : bool, optional`**
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

r.surf.random produces a raster map layer of uniform random deviates
whose range can be expressed by the user. It is essentially the same as r.surf.gauss , but uses a linear random number generator instead. It
uses the random number generator drand48() or rand(), depending on the
user's platform.

---

## See Also

Related tools:
- [`r.random.surface`](https://grass.osgeo.org/grass-devel/manuals/r.random.surface.html)
- [`r.surf.contour`](https://grass.osgeo.org/grass-devel/manuals/r.surf.contour.html)
- [`r.surf.fractal`](https://grass.osgeo.org/grass-devel/manuals/r.surf.fractal.html)
- [`r.surf.gauss`](https://grass.osgeo.org/grass-devel/manuals/r.surf.gauss.html)
- [`r.surf.idw`](https://grass.osgeo.org/grass-devel/manuals/r.surf.idw.html)
- [`v.surf.rst`](https://grass.osgeo.org/grass-devel/manuals/v.surf.rst.html)

---

## Resources

- [Official r.surf.random manual](https://grass.osgeo.org/grass-devel/manuals/r.surf.random.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.surf.random.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
