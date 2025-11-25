# r.random

**Category**: raster

## Description

Creates randomly placed raster cells or vector points Creates a raster map and vector point map containing randomly located cells and points.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_random(input,cover=None,npoints,raster=None,vector=None,seed=None,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str | np.ndarray, required`**
   - Name of input raster map
   - Used as: input, raster, name

2. **`cover : str | np.ndarray, optional`**
   - Name of cover raster map
   - Used as: input, raster, name

3. **`npoints : str, required`**
   - The number of points (or cells) to generate
   - The number of vector points or raster cells to generate, possibly as a percentage of number of cells
   - Used as: number[%]

4. **`raster : str | type(np.ndarray) | type(np.array) | type(gs.array.array), optional`**
   - Name for output raster map
   - Used as: output, raster, name

5. **`vector : str, optional`**
   - Name for output vector map
   - Used as: output, vector, name

6. **`seed : int, optional`**
   - Seed value for the random number generator
   - Using the same seed ensures identical results, while a randomly generated seed produces different outcomes in each run.

7. **`flags : str, optional`**
   - Allowed values: s, n, z, b
   - s
   - Generate random seed (result is non-deterministic)
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/r.random.html#__tabbed_2_3) for all details)*

8. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

9. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

10. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

11. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 11 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/r.random.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | np.ndarray | tuple[np.ndarray] | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned. If an array type (e.g., np.ndarray) is used for one of the raster outputs, the result will be an array and will have the shape corresponding to the computational region. If an array type is used for more than one raster output, the result will be a tuple of arrays.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

The module r.random creates a raster map with values in random places.
Alternatively, it creates random vector points at these places. Number
of random cells or points can be a fixed number or a percentage of cells
from the input. By default, generated cells or points will be subset of
non-NULL cells of the input. Resulting raster map consists of original
cell values at the selected random locations and NULL (no data) values
elsewhere.

The module allows the user to create a raster map and/or a vector points
map containing coordinates of points whose locations have been randomly
determined. The module places these randomly generated vector points
within the current computational region and raster mask (if any), on
non-NULL raster cells in a user-specified raster map. If the user sets
the -n flag, points will be randomly generated across all cells
(even those with NULL values). Cells in the resulting raster overlap
with the cells of the input raster based on the current computational
region. Points in the resulting vector map are placed in cell centers of
these cells.

The user may specify the quantity of random locations to be generated
either as a positive integer (e.g., 10), or as a percentage of the
raster map's cells (e.g., 10%, or 3.05%). The number of cells
considered for the percentage reflects whether or not the -n flag
was given. Options are 0-100; fractions of percent may be stated as
decimals (e.g., 66.67%, or 0.05%).

The cell values and corresponding category names (if present) associated
with the random point locations in the input map are assigned to the
newly generated cells in the raster map. If the -n is specified,
then a unique entry is made for the value used where the input was
NULL. This value is at least 1 less than the smallest value in the input raster and is given a medium gray color.

If a cover raster map is specified, values are taken from the cover raster map instead of the input raster map. If a cover raster map is
specified and the cover map contains NULL (no data) values, these
points are suppressed in the resulting vector or raster map.

The vector file created by r.random contains vector points that
represent the center points of the randomly generated cells. A value attribute contains the cell value of the input raster (or the assigned
value when -n is used). If a cover map is additionally specified,
a second column covervalue is populated with raster values from the cover map.

If the user sets the -b flag, vector points are written without
topology to minimize the required resources. This is suitable input to v.surf.rst and other vector modules.

---

## Authors

Dr. James Hinthorne, GIS Laboratory, Central Washington University
Modified for GRASS 5.0 by Eric G. Miller
Cover map support by Markus Neteler, 2007

---

## Resources

- [Official r.random manual](https://grass.osgeo.org/grass-devel/manuals/r.random.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.random.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
