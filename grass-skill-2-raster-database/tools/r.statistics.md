# r.statistics

**Category**: raster

## Description

Calculates category or object oriented statistics.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_statistics(base,cover,method,output,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`base : str | np.ndarray, required`**
   - Name of base raster map
   - Used as: input, raster, name

2. **`cover : str | np.ndarray, required`**
   - Name of cover raster map
   - Used as: input, raster, name

3. **`method : str, required`**
   - Method of object-based statistic
   - Allowed values: diversity, average, mode, median, avedev, stddev, variance, skewness, kurtosis, min, max, sum
   - diversity: Diversity of values in specified objects in %%
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/r.statistics.html#__tabbed_2_3) for all details)*

4. **`output : str | type(np.ndarray) | type(np.array) | type(gs.array.array), required`**
   - Resultant raster map
   - Used as: output, raster, name

5. **`flags : str, optional`**
   - Allowed values: c
   - c
   - Cover values extracted from the category labels of the cover map

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

r.statistics is a tool to analyse exploratory statistics of a
categorical "cover layer" according to how it intersects with objects in
a "base layer". A variety of standard statistical measures are possible
(called "zonal statistics" in some GIS). All cells in the base layer are
considered one object for the analysis. For some applications, one will
first want to prepare the input data so that all areas of contiguous
cell category values in the base layer are uniquely identified, which
can be done with r.clump . The available methods are the following:

The calculations will be performed on each area of data of the cover
layers which fall within each unique value, or category, of the base
layer.

Setting the -c flag the category labels of the covering raster layer
will be used. This is nice to avoid the GRASS limitation to integer in
raster maps because using category values floating point numbers can be
stored.

All calculations create an output layer. The output layer is a
reclassified version of the base layer with identical category values,
but modified category labels - the results of the calculations are
stored in the category labels of the output layer.

---

## See Also

Related tools:
- [`r.category`](https://grass.osgeo.org/grass-devel/manuals/r.category.html)
- [`r.clump`](https://grass.osgeo.org/grass-devel/manuals/r.clump.html)
- [`r.mode`](https://grass.osgeo.org/grass-devel/manuals/r.mode.html)
- [`r.mapcalc`](https://grass.osgeo.org/grass-devel/manuals/r.mapcalc.html)
- [`r.neighbors`](https://grass.osgeo.org/grass-devel/manuals/r.neighbors.html)
- [`r.stats.quantile`](https://grass.osgeo.org/grass-devel/manuals/r.stats.quantile.html)
- [`r.stats.zonal`](https://grass.osgeo.org/grass-devel/manuals/r.stats.zonal.html)
- [`r.univar`](https://grass.osgeo.org/grass-devel/manuals/r.univar.html)

---

## Resources

- [Official r.statistics manual](https://grass.osgeo.org/grass-devel/manuals/r.statistics.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.statistics.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
