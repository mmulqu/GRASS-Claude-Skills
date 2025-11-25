# r.rescale.eq

**Category**: raster

## Description

Rescales histogram equalized the range of category values in a raster map layer.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_rescale_eq(input,from=None,output,to,title=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str | np.ndarray, required`**
   - The name of the raster map to be rescaled
   - Used as: input, raster, name

2. **`from : tuple[int, int] | list[int] | str, optional`**
   - The input data range to be rescaled (default: full range of input map)
   - Used as: min,max

3. **`output : str | type(np.ndarray) | type(np.array) | type(gs.array.array), required`**
   - The resulting raster map name
   - Used as: output, raster, name

4. **`to : tuple[int, int] | list[int] | str, required`**
   - The output data range
   - Used as: min,max

5. **`title : str, optional`**
   - Title for new raster map
   - Used as: phrase

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

The r.rescale.eq program rescales the range of category values
appearing in a raster map layer with equalized histogram. A new raster
map layer, and an appropriate category file and color table based upon
the original raster map layer, are generated with category labels that
reflect the original category values that produced each category. This
command is useful for producing representations with a reduced number of
categories from a raster map layer with a large range of category values
(e.g., elevation). Rescaled map layers are appropriate for use in such
GRASS commands as r.stats , r.report , and r.coin .

---

## See Also

Related tools:
- [`r.coin`](https://grass.osgeo.org/grass-devel/manuals/r.coin.html)
- [`r.describe`](https://grass.osgeo.org/grass-devel/manuals/r.describe.html)
- [`r.info`](https://grass.osgeo.org/grass-devel/manuals/r.info.html)
- [`r.mapcalc`](https://grass.osgeo.org/grass-devel/manuals/r.mapcalc.html)
- [`r.reclass`](https://grass.osgeo.org/grass-devel/manuals/r.reclass.html)
- [`r.rescale`](https://grass.osgeo.org/grass-devel/manuals/r.rescale.html)
- [`r.report`](https://grass.osgeo.org/grass-devel/manuals/r.report.html)
- [`r.resample`](https://grass.osgeo.org/grass-devel/manuals/r.resample.html)
- [`r.stats`](https://grass.osgeo.org/grass-devel/manuals/r.stats.html)

---

## Resources

- [Official r.rescale.eq manual](https://grass.osgeo.org/grass-devel/manuals/r.rescale.eq.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.rescale.eq.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
