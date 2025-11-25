# i.pca

**Category**: imagery

## Description

Principal components analysis (PCA) for image processing.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.i_pca(input,output,rescale="0,255",percent=99,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str | list[str], required`**
   - Name of two or more input raster maps or imagery group
   - Used as: input, raster, name

2. **`output : str | type(np.ndarray) | type(np.array) | type(gs.array.array), required`**
   - Name for output basename raster map(s)
   - A numerical suffix will be added for each component map
   - Used as: output, raster, basename

3. **`rescale : tuple[int, int] | list[int] | str, optional`**
   - Rescaling range for output maps
   - For no rescaling use 0,0
   - Used as: min,max

4. **`percent : int, optional`**
   - Cumulative percent importance for filtering
   - Allowed values: 50-99
   - Default: 99

5. **`flags : str, optional`**
   - Allowed values: n, f
   - n
   - Normalize (center and scale) input maps
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/i.pca.html#__tabbed_2_3) for all details)*

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

i.pca is an image processing program based on the algorithm provided
by Vali (1990), that processes n (n >= 2) input raster map layers and
produces n output raster map layers containing the principal components
of the input data in decreasing order of variance ("contrast"). The
output raster map layers are assigned names with .1, .2, ... .n
suffixes. The numbers used as suffix correspond to percent importance
with .1 being the scores of the principal component with the highest
importance.

The current geographic region definition and raster mask settings are
respected when reading the input raster map layers. When the rescale
option is used, the output files are rescaled to fit the min,max range.

The order of the input bands does not matter for the output maps (PC
scores), but does matter for the vectors (loadings), since each loading
refers to a specific input band.

If the output is not rescaled ( rescale=0,0 , the output raster maps
will be of type DCELL, otherwise the output raster maps will be of type
CELL.

By default, the values of the input raster maps are centered for each
map separately with x - mean . With -n , the input raster maps are
normalized for each map separately with (x - mean) / stddev .
Normalizing is highly recommended when the input raster maps have
different units, e.g. represent different environmental parameters.

The -f flag, together with the percent option, can be used to remove
noise from input bands. Input bands will be recalculated from a subset
of the principal components (inverse PCA). The subset is selected by
using only the most important (highest eigenvalue) principal components
which explain together percent percent variance observed in the input
bands.

---

## Authors

David Satnik, GIS Laboratory
Major modifications for GRASS 4.1 were made by Olga Waupotitsch and Michael Shapiro, U.S.Army Construction Engineering
Research Laboratory
Rewritten for GRASS 6.x and major modifications by Brad Douglas

---

## Resources

- [Official i.pca manual](https://grass.osgeo.org/grass-devel/manuals/i.pca.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/i.pca.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
