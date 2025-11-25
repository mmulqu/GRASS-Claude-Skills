# i.zc

**Category**: imagery

## Description

Zero-crossing "edge detection" raster function for image processing.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.i_zc(input,output,width=9,threshold=1.0,orientations=1,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str | np.ndarray, required`**
   - Name of input raster map
   - Used as: input, raster

2. **`output : str | type(np.ndarray) | type(np.array) | type(gs.array.array), required`**
   - Zero crossing raster map
   - Used as: output, raster

3. **`width : int, optional`**
   - x-y extent of the Gaussian filter
   - Default: 9

4. **`threshold : float, optional`**
   - Sensitivity of Gaussian filter
   - Default: 1.0

5. **`orientations : int, optional`**
   - Number of azimuth directions categorized
   - Default: 1

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

i.zc is an image processing module used for edge detection. The raster
map produced shows the location of "boundaries" on the input map.
Boundaries tend to be found in regions of changing cell values and tend
to run perpendicular to the direction of the slope. The algorithm used
for edge detection is one of the "zero-crossing" algorithms and is
discussed briefly below.

---

## See Also

Related tools:
- [`i.fft`](https://grass.osgeo.org/grass-devel/manuals/i.fft.html)
- [`i.ifft`](https://grass.osgeo.org/grass-devel/manuals/i.ifft.html)
- [`r.mapcalc`](https://grass.osgeo.org/grass-devel/manuals/r.mapcalc.html)
- [`r.mfilter`](https://grass.osgeo.org/grass-devel/manuals/r.mfilter.html)
- [`r.slope.aspect`](https://grass.osgeo.org/grass-devel/manuals/r.slope.aspect.html)

---

## Resources

- [Official i.zc manual](https://grass.osgeo.org/grass-devel/manuals/i.zc.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/i.zc.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
