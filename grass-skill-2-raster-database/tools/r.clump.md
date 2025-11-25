# r.clump

**Category**: raster

## Description

Recategorizes data in a raster map by grouping cells that form physically discrete areas into unique categories.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_clump(input,output=None,title=None,threshold=0,minsize=1,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str | list[str], required`**
   - Name of input raster map(s)
   - Used as: input, raster, name

2. **`output : str | type(np.ndarray) | type(np.array) | type(gs.array.array), optional`**
   - Name for output raster map
   - Used as: output, raster, name

3. **`title : str, optional`**
   - Title for output raster map

4. **`threshold : float, optional`**
   - Threshold to identify similar cells
   - Valid range: 0 = identical to < 1 = maximal difference
   - Default: 0

5. **`minsize : int, optional`**
   - Minimum clump size in cells
   - Clumps smaller than minsize will be merged to form larger clumps
   - Default: 1

6. **`flags : str, optional`**
   - Allowed values: d, g
   - d
   - Clump also diagonal cells
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/r.clump.html#__tabbed_2_3) for all details)*

7. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

8. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

9. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

10. **`superquiet : bool, optional`**
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

r.clump finds all areas of contiguous cell category values (connected
components) in the input raster map. NULL values in the input are
ignored. It assigns a unique category value to each such area ("clump")
in the resulting output raster map.

Category distinctions in the input raster map are preserved. This means
that if distinct category values are adjacent, they will NOT be clumped
together. The user can run r.reclass prior to r.clump to recategorize cells and reassign cell category values.

r.clump can also perform "fuzzy" clumping where neighboring cells that
are not identical but similar to each other are clumped together. Here,
the spectral distance between two cells is scaled to the range [0, 1]
and compared to the threshold value. Cells are clumped together if
their spectral distance is ≤ threshold . The result is very sensitive
to this threshold value, a recommended start value is 0.01, then
increasing or decreasing this value according to the desired output.
Once a suitable threshold has been determined, noise can be reduced by
merging small clumps with the minsize option.

r.clump can also use multiple raster maps of any kind (CELL, FCELL,
DCELL) as input. In this case, the spectral distance between cells is
used to determine the similarity of two cells. This means that input
maps must be metric: the difference cell 1 - cell 2 must make sense.
Categorical maps, e.g. land cover, can not be used in this case.
Examples for valid input maps are satellite imagery, vegetation indices,
elevation, climatic parameters etc.

---

## See Also

Related tools:
- [`r.buffer`](https://grass.osgeo.org/grass-devel/manuals/r.buffer.html)
- [`r.distance`](https://grass.osgeo.org/grass-devel/manuals/r.distance.html)
- [`r.grow`](https://grass.osgeo.org/grass-devel/manuals/r.grow.html)
- [`r.mapcalc`](https://grass.osgeo.org/grass-devel/manuals/r.mapcalc.html)
- [`r.mfilter`](https://grass.osgeo.org/grass-devel/manuals/r.mfilter.html)
- [`r.neighbors`](https://grass.osgeo.org/grass-devel/manuals/r.neighbors.html)
- [`r.to.vect`](https://grass.osgeo.org/grass-devel/manuals/r.to.vect.html)
- [`r.reclass`](https://grass.osgeo.org/grass-devel/manuals/r.reclass.html)
- [`r.statistics`](https://grass.osgeo.org/grass-devel/manuals/r.statistics.html)
- [`r.support`](https://grass.osgeo.org/grass-devel/manuals/r.support.html)

---

## Authors

Michael Shapiro, U.S. Army Construction Engineering Research
Laboratory Markus Metz (diagonal clump tracing, fuzzy clumping)

---

## Resources

- [Official r.clump manual](https://grass.osgeo.org/grass-devel/manuals/r.clump.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.clump.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
