# r.surf.fractal

**Category**: raster

## Description

Creates a fractal surface of a given fractal dimension.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_surf_fractal(output,dimension=2.05,number=0,seed=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`output : str | type(np.ndarray) | type(np.array) | type(gs.array.array), required`**
   - Name for output raster map
   - Used as: output, raster, name

2. **`dimension : float, optional`**
   - Fractal dimension of surface (2 < D < 3)
   - Default: 2.05

3. **`number : int, optional`**
   - Number of intermediate images to produce
   - Default: 0

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

r.surf.fractal creates a fractal surface of a given fractal
dimension. It uses the spectral synthesis method. The module can create
intermediate layers showing the build up of different spectral
coefficients (see Saupe, pp.106-107 for an example of this).

This module generates naturally looking synthetical elevation models
(DEM).

---

## Note

This module requires the FFTW library for computing
Discrete Fourier Transforms.

---

## See Also

Related tools:
- [`r.surf.contour`](https://grass.osgeo.org/grass-devel/manuals/r.surf.contour.html)
- [`r.surf.idw`](https://grass.osgeo.org/grass-devel/manuals/r.surf.idw.html)
- [`r.surf.gauss`](https://grass.osgeo.org/grass-devel/manuals/r.surf.gauss.html)
- [`r.surf.random`](https://grass.osgeo.org/grass-devel/manuals/r.surf.random.html)
- [`v.surf.idw`](https://grass.osgeo.org/grass-devel/manuals/v.surf.idw.html)
- [`v.surf.rst`](https://grass.osgeo.org/grass-devel/manuals/v.surf.rst.html)

---

## Resources

- [Official r.surf.fractal manual](https://grass.osgeo.org/grass-devel/manuals/r.surf.fractal.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.surf.fractal.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
