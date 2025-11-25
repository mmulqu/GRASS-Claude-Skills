# r.smooth.edgepreserve

**Category**: raster

## Description

Smoothing with anisotropic diffusion

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_smooth_edgepreserve(input,output,threshold=5,lambda=0.1,steps=10,function="tukey",memory=300,nprocs=0,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str | np.ndarray, required`**
   - Name of input raster map
   - Used as: input, raster, name

2. **`output : str | type(np.ndarray) | type(np.array) | type(gs.array.array), required`**
   - Name for output raster map
   - Used as: output, raster, name

3. **`threshold : float, required`**
   - Gradient magnitude threshold (in map units)
   - Allowed values: 0.000000001-
   - Default: 5

4. **`lambda : float, required`**
   - Rate of diffusion
   - Allowed values: 0-1
   - Default: 0.1

5. **`steps : int, required`**
   - Number of diffusion steps
   - Allowed values: 1-
   - Default: 10

6. **`function : str, required`**
   - Diffusivity function
   - Allowed values: exponential, quadratic, tukey
   - Default: tukey

7. **`memory : int, optional`**
   - Maximum memory to be used (in MB)
   - Cache size for raster rows
   - Used as: memory in MB

8. **`nprocs : int, optional`**
   - Number of threads for parallel computing
   - 0: use OpenMP default; >0: use nprocs; <0: use MAX-nprocs
   - Default: 0

9. **`flags : str, optional`**
   - Allowed values: p
   - p
   - Preserve details with Tukey

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


*Showing 10 of 13 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/r.smooth.edgepreserve.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | np.ndarray | tuple[np.ndarray] | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned. If an array type (e.g., np.ndarray) is used for one of the raster outputs, the result will be an array and will have the shape corresponding to the computational region. If an array type is used for more than one raster output, the result will be a tuple of arrays.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

This module performs adaptive, edge-preserving raster smoothing
using anisotropic diffusion. The result is a denoised raster that
retains important features, especially edges. Unlike traditional
smoothing methods (such as a uniform average filter, like the one available
in r.neighbors ), this module smooths only areas with similar values
and works to preserve sharp transitions between different regions.

Figure: "A" is the original (unsmoothed) raster and
"B" is the smoothed version (with quite agressive settings to emphasize
smoothing effects).

The module supports three types of diffusivity (conductance) functions:

The Tukey’s biweight function is more aggressive than the others and
tends to produce large, smoothly blended areas. This makes it
particularly useful for raster segmentation. If you prefer a gentler
effect that preserves smaller features, you can use the -p flag,
which switches to a softer variant of the Tukey function — ideal for
applications like visualization.

---

## Resources

- [Official r.smooth.edgepreserve manual](https://grass.osgeo.org/grass-devel/manuals/r.smooth.edgepreserve.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.smooth.edgepreserve.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
