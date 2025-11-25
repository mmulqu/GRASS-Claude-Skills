# r.resample

**Category**: raster

## Description

GRASS raster map layer data resampling capability.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_resample(input,output,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str | np.ndarray, required`**
   - Name of an input layer
   - Used as: input, raster

2. **`output : str | type(np.ndarray) | type(np.array) | type(gs.array.array), required`**
   - Name of an output layer
   - Used as: output, raster

3. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

4. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

5. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

6. **`superquiet : bool, optional`**
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

r.resample resamples the data values in a user-specified raster input
map layer name (bounded by the current geographic region and masked by
the current mask), and produces a new raster output map layer name containing the results of the resampling. The category values in the new
raster output map layer will be the same as those in the original,
except that the resolution and extent of the new raster output map layer
will match those of the current geographic region settings (see g.region ). r.resample is intended for resampling of
discrete raster data (such as land cover, geology or soil type) to a
different resolution. Continuous data (such as elevation or temperature)
usually require reinterpolation when changing resolution, see r.resamp.interp .

---

## See Also

Related tools:
- [`g.region`](https://grass.osgeo.org/grass-devel/manuals/g.region.html)
- [`r.mapcalc`](https://grass.osgeo.org/grass-devel/manuals/r.mapcalc.html)
- [`r.mfilter`](https://grass.osgeo.org/grass-devel/manuals/r.mfilter.html)
- [`r.neighbors`](https://grass.osgeo.org/grass-devel/manuals/r.neighbors.html)
- [`r.rescale`](https://grass.osgeo.org/grass-devel/manuals/r.rescale.html)
- [`r.resamp.interp`](https://grass.osgeo.org/grass-devel/manuals/r.resamp.interp.html)

---

## Resources

- [Official r.resample manual](https://grass.osgeo.org/grass-devel/manuals/r.resample.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.resample.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
