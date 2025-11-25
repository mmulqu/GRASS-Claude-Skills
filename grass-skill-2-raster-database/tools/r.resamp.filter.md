# r.resamp.filter

**Category**: raster

## Description

Resamples raster map layers using an analytic kernel.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_resamp_filter(input,output,filter,radius=None,x_radius=None,y_radius=None,memory=300,nprocs=0,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str | np.ndarray, required`**
   - Name of input raster map
   - Used as: input, raster, name

2. **`output : str | type(np.ndarray) | type(np.array) | type(gs.array.array), required`**
   - Name for output raster map
   - Used as: output, raster, name

3. **`filter : str | list[str], required`**
   - Filter kernel(s)
   - Allowed values: box, bartlett, gauss, normal, hermite, sinc, lanczos1, lanczos2, lanczos3, hann, hamming, blackman

4. **`radius : float | list[float] | str, optional`**
   - Filter radius

5. **`x_radius : float | list[float] | str, optional`**
   - Filter radius (horizontal)

6. **`y_radius : float | list[float] | str, optional`**
   - Filter radius (vertical)

7. **`memory : int, optional`**
   - Maximum memory to be used (in MB)
   - Cache size for raster rows
   - Used as: memory in MB

8. **`nprocs : int, optional`**
   - Number of threads for parallel computing
   - 0: use OpenMP default; >0: use nprocs; <0: use MAX-nprocs
   - Default: 0

9. **`flags : str, optional`**
   - Allowed values: n
   - n
   - Propagate NULLs

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


*Showing 10 of 13 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/r.resamp.filter.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | np.ndarray | tuple[np.ndarray] | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned. If an array type (e.g., np.ndarray) is used for one of the raster outputs, the result will be an array and will have the shape corresponding to the computational region. If an array type is used for more than one raster output, the result will be a tuple of arrays.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

r.resamp.filter resamples an input raster, filtering the input with an
analytic kernel. Each output cell is typically calculated based upon a
small subset of the input cells, not the entire input. r.resamp.filter performs convolution (i.e. a weighted sum is calculated for every raster
cell).

The radii must be given in map units. In order to consider more than one
input cell, at least one finite radius must be larger than half the
resolution of the input map, otherwise the selected kernels will have no
effect.

The module maps the input range to the width of the window function, so
wider windows will be "sharper" (have a higher cut-off frequency), e.g.
lanczos3 will be sharper than lanczos2.

r.resamp.filter implements FIR (finite impulse response) filtering.
All of the functions are low-pass filters, as they are symmetric. See Wikipedia: Window
function for examples of
common window functions and their frequency responses.

A piecewise-continuous function defined by sampled data can be
considered a mixture (sum) of the underlying signal and quantisation
noise. The intent of a low pass filter is to discard the quantisation
noise while retaining the signal. The cut-off frequency is normally
chosen according to the sampling frequency, as the quantisation noise is
dominated by the sampling frequency and its harmonics. In general, the
cut-off frequency is inversely proportional to the width of the central
"lobe" of the window function.

When using r.resamp.filter with a specific radius, a specific cut-off
frequency regardless of the method is chosen. So while lanczos3 uses 3
times as large a window as lanczos1, the cut-off frequency remains the
same. Effectively, the radius is "normalised".

All of the kernels specified by the filter parameter are multiplied
together. Typical usage will use either a single finitie window or an
infinite kernel along with a finite window.

To smooth a map, keeping its resolution, a good starting point is to use
the filters gauss,box with the radii 0.5 * input resolution , 2
* input resolution . See also r.neighbors

When resampling a map to a higher resolution (alternative to
interpolation, e.g. r.resamp.interp ), a good
starting point is to use the filters gauss,box with the radii 1.5
* input resolution , 3 * input resolution .

When resampling a map to a lower resolution (alternative to aggregation,
e.g. r.resamp.stats ), a good starting point is to
use the filters gauss,box with the radii 0.25 * output
resolution , 1 * output resolution .

These are recommendations for initial settings. The selection of filters
and radii might need adjustment according to the actual purpose.

---

## See Also

Related tools:
- [`g.region`](https://grass.osgeo.org/grass-devel/manuals/g.region.html)
- [`r.mfilter`](https://grass.osgeo.org/grass-devel/manuals/r.mfilter.html)
- [`r.resample`](https://grass.osgeo.org/grass-devel/manuals/r.resample.html)
- [`r.resamp.interp`](https://grass.osgeo.org/grass-devel/manuals/r.resamp.interp.html)
- [`r.resamp.rst`](https://grass.osgeo.org/grass-devel/manuals/r.resamp.rst.html)
- [`r.resamp.stats`](https://grass.osgeo.org/grass-devel/manuals/r.resamp.stats.html)

---

## Resources

- [Official r.resamp.filter manual](https://grass.osgeo.org/grass-devel/manuals/r.resamp.filter.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.resamp.filter.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
