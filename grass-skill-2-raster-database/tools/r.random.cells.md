# r.random.cells

**Category**: raster

## Description

Generates random cell values with spatial dependence.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_random_cells(output,distance,ncells=None,seed=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`output : str | type(np.ndarray) | type(np.array) | type(gs.array.array), required`**
   - Name for output raster map
   - Used as: output, raster, name

2. **`distance : float, required`**
   - Maximum distance of spatial correlation (value >= 0.0)

3. **`ncells : int, optional`**
   - Maximum number of cells to be created
   - Allowed values: 1-

4. **`seed : int, optional`**
   - Seed value for the random number generator
   - Using the same seed ensures identical results, while a randomly generated seed produces different outcomes in each run.

5. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

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

result : grass.tools.support.ToolResult | np.ndarray | tuple[np.ndarray] | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned. If an array type (e.g., np.ndarray) is used for one of the raster outputs, the result will be an array and will have the shape corresponding to the computational region. If an array type is used for more than one raster output, the result will be a tuple of arrays.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

r.random.cells generates a random sets of raster cells that are at
least distance apart. The cells are numbered from 1 to the numbers
of cells generated, all other cells are NULL (no data). Random cells
will not be generated in areas masked off.

output Random cells. Each random cell has a unique non-zero cell value ranging
from 1 to the number of cells generated. The heuristic for this
algorithm is to randomly pick cells until there are no cells outside of
the chosen cell's buffer of radius distance .

distance Determines the minimum distance the centers of the random cells will be
apart.

seed Specifies the random seed that r.random.cells will use to generate the
cells. If the random seed is not given, r.random.cells will get a seed
from the process ID number.

---

## See Also

Related tools:
- [`r.random.surface`](https://grass.osgeo.org/grass-devel/manuals/r.random.surface.html)
- [`r.random`](https://grass.osgeo.org/grass-devel/manuals/r.random.html)
- [`v.random`](https://grass.osgeo.org/grass-devel/manuals/v.random.html)
- [`r.to.vect`](https://grass.osgeo.org/grass-devel/manuals/r.to.vect.html)
- [`v.perturb`](https://grass.osgeo.org/grass-devel/manuals/v.perturb.html)

---

## Resources

- [Official r.random.cells manual](https://grass.osgeo.org/grass-devel/manuals/r.random.cells.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.random.cells.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
