# r.surf.gauss

**Category**: raster

## Description

Generates a raster map using gaussian random number generator. Mean and standard deviation of gaussian deviates can be expressed by the user.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_surf_gauss(output,mean=0.0,sigma=1.0,seed=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`output : str | type(np.ndarray) | type(np.array) | type(gs.array.array), required`**
   - Name for output raster map
   - Used as: output, raster, name

2. **`mean : float, optional`**
   - Distribution mean
   - Default: 0.0

3. **`sigma : float, optional`**
   - Standard deviation
   - Default: 1.0

4. **`seed : int, optional`**
   - Seed value for the random number generator
   - Using the same seed ensures identical results, while a randomly generated seed produces different outcomes in each run.

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

r.surf.gauss produces a raster map of Gaussian deviates whose mean and
standard deviation can be expressed by the user. It uses a Gaussian
random number generator. It is essentially the same as r.surf.random , but uses a Gaussian random number
generator instead.

---

## See Also

Related tools:
- [`r.surf.contour`](https://grass.osgeo.org/grass-devel/manuals/r.surf.contour.html)
- [`r.surf.fractal`](https://grass.osgeo.org/grass-devel/manuals/r.surf.fractal.html)
- [`r.surf.idw`](https://grass.osgeo.org/grass-devel/manuals/r.surf.idw.html)
- [`r.surf.random`](https://grass.osgeo.org/grass-devel/manuals/r.surf.random.html)
- [`v.surf.rst`](https://grass.osgeo.org/grass-devel/manuals/v.surf.rst.html)

---

## Resources

- [Official r.surf.gauss manual](https://grass.osgeo.org/grass-devel/manuals/r.surf.gauss.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.surf.gauss.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
