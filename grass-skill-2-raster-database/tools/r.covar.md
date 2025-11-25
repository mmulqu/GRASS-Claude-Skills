# r.covar

**Category**: raster

## Description

Outputs a covariance/correlation matrix for user-specified raster map layer(s).

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_covar(map,flags=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`map : str | list[str], required`**
   - Name of raster map(s)
   - Used as: input, raster, name

2. **`flags : str, optional`**
   - Allowed values: r
   - r
   - Print correlation matrix

3. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

4. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

5. **`superquiet : bool, optional`**
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

r.covar outputs a covariance/correlation matrix for user-specified
raster map layer(s). The output can be printed, or saved by redirecting
output into a file.

The output is an N x N symmetric covariance (correlation) matrix, where
N is the number of raster map layers specified on the command line.

---

## See Also

Related tools:
- [`i.pca`](https://grass.osgeo.org/grass-devel/manuals/i.pca.html)
- [`m.eigensystem`](https://grass.osgeo.org/grass-devel/manuals/m.eigensystem.html)
- [`r.mapcalc`](https://grass.osgeo.org/grass-devel/manuals/r.mapcalc.html)
- [`r.rescale`](https://grass.osgeo.org/grass-devel/manuals/r.rescale.html)

---

## Resources

- [Official r.covar manual](https://grass.osgeo.org/grass-devel/manuals/r.covar.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.covar.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
