# r.describe

**Category**: raster

## Description

Prints terse list of category values found in a raster map layer.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_describe(map,null_value="*",nsteps=255,format="plain",flags=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`map : str | np.ndarray, required`**
   - Name of raster map
   - Used as: input, raster, name

2. **`null_value : str, optional`**
   - String representing NULL value
   - Used as: string
   - Default: *

3. **`nsteps : int, optional`**
   - Number of quantization steps
   - Default: 255

4. **`format : str, required`**
   - Output format
   - Used as: name
   - Allowed values: plain, json
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/r.describe.html#__tabbed_2_3) for all details)*

5. **`flags : str, optional`**
   - Allowed values: 1, r, n, d, i
   - 1
   - Print the output one value per line
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/r.describe.html#__tabbed_2_3) for all details)*

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

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

r.describe prints a terse listing of category values found in a
user-specified raster map layer.

r.describe ignores the current geographic region and mask, and
reads the full extent of the input raster map. This functionality is
useful if the user intends to reclassify or rescale the data, since
these functions ( r.reclass and r.rescale ) also ignore the current geographic region and mask .

The nv parameter sets the string to be used to represent NULL values in the module output; the default is '*'.

The nsteps parameter sets the number of quantisation steps to
divide into the input raster map.

---

## See Also

Related tools:
- [`g.region`](https://grass.osgeo.org/grass-devel/manuals/g.region.html)
- [`r.mask`](https://grass.osgeo.org/grass-devel/manuals/r.mask.html)
- [`r.reclass`](https://grass.osgeo.org/grass-devel/manuals/r.reclass.html)
- [`r.report`](https://grass.osgeo.org/grass-devel/manuals/r.report.html)
- [`r.rescale`](https://grass.osgeo.org/grass-devel/manuals/r.rescale.html)
- [`r.stats`](https://grass.osgeo.org/grass-devel/manuals/r.stats.html)
- [`r.univar`](https://grass.osgeo.org/grass-devel/manuals/r.univar.html)

---

## Resources

- [Official r.describe manual](https://grass.osgeo.org/grass-devel/manuals/r.describe.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.describe.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
