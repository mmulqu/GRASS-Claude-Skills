# r.cost

**Category**: raster

## Description

Creates a raster map showing the cumulative cost of moving between different geographic locations on an input raster map whose cell category values represent cost.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_cost(input,output,solver=None,nearest=None,outdir=None,start_points=None,stop_points=None,start_raster=None,start_coordinates=None,stop_coordinates=None,max_cost=0,null_cost=None,memory=300,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str | np.ndarray, required`**
   - Name of input raster map containing grid cell cost information
   - Used as: input, raster, name

2. **`output : str | type(np.ndarray) | type(np.array) | type(gs.array.array), required`**
   - Name for output raster map
   - Used as: output, raster, name

3. **`solver : str | np.ndarray, optional`**
   - Name of input raster map solving equal costs
   - Helper variable to pick a direction if two directions have equal cumulative costs (smaller is better)
   - Used as: input, raster, name

4. **`nearest : str | type(np.ndarray) | type(np.array) | type(gs.array.array), optional`**
   - Name for output raster map with nearest start point
   - Used as: output, raster, name

5. **`outdir : str | type(np.ndarray) | type(np.array) | type(gs.array.array), optional`**
   - Name for output raster map to contain movement directions
   - Used as: output, raster, name

6. **`start_points : str, optional`**
   - Name of starting vector points map
   - Or data source for direct OGR access
   - Used as: input, vector, name

7. **`stop_points : str, optional`**
   - Name of stopping vector points map
   - Or data source for direct OGR access
   - Used as: input, vector, name

8. **`start_raster : str | np.ndarray, optional`**
   - Name of starting raster points map
   - Used as: input, raster, name

9. **`start_coordinates : list[tuple[float, float]] | tuple[float, float] | list[float] | str, optional`**
   - Coordinates of starting point(s) (E,N)
   - Used as: input, coords, east,north

10. **`stop_coordinates : list[tuple[float, float]] | tuple[float, float] | list[float] | str, optional`**
   - Coordinates of stopping point(s) (E,N)
   - Used as: input, coords, east,north

11. **`max_cost : int, optional`**
   - Maximum cumulative cost
   - Used as: value
   - Default: 0

12. **`null_cost : float, optional`**
   - Cost assigned to null cells. By default, null cells are excluded
   - Used as: value

13. **`memory : int, optional`**
   - Maximum memory to be used (in MB)
   - Cache size for raster rows
   - Used as: memory in MB

14. **`flags : str, optional`**
   - Allowed values: k, n, r, i, b
   - k
   - Use the 'Knight's move'; slower, but more accurate
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/r.cost.html#__tabbed_2_3) for all details)*

15. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

16. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

17. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

18. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 18 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/r.cost.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | np.ndarray | tuple[np.ndarray] | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned. If an array type (e.g., np.ndarray) is used for one of the raster outputs, the result will be an array and will have the shape corresponding to the computational region. If an array type is used for more than one raster output, the result will be a tuple of arrays.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

r.cost determines the cumulative cost of moving to each cell on a cost surface (the input raster map) from other user-specified
cell(s) whose locations are specified by their geographic coordinate(s).
Each cell in the original cost surface map will contain a category value
which represents the cost of traversing that cell. r.cost will
produce 1) an output raster map in which each cell contains the
lowest total cost of traversing the space between each cell and the
user-specified points (diagonal costs are multiplied by a factor that
depends on the dimensions of the cell) and 2) a second raster map layer
showing the movement direction to the next cell on the path back to the
start point (see Movement Direction ). This module uses the
current geographic region settings. The output map will be of the
same data format as the input map, integer or floating point.

---

## See Also

Related tools:
- [`r.walk`](https://grass.osgeo.org/grass-devel/manuals/r.walk.html)
- [`r.path`](https://grass.osgeo.org/grass-devel/manuals/r.path.html)
- [`r.in.ascii`](https://grass.osgeo.org/grass-devel/manuals/r.in.ascii.html)
- [`r.mapcalc`](https://grass.osgeo.org/grass-devel/manuals/r.mapcalc.html)
- [`r.out.ascii`](https://grass.osgeo.org/grass-devel/manuals/r.out.ascii.html)

---

## Authors

Antony Awaida, Intelligent Engineering Systems Laboratory, M.I.T. James Westervelt, U.S.Army Construction Engineering Research
Laboratory Updated for Grass 5 by Pierre de Mouveaux ( pmx@audiovu.com ) Markus Metz Multiple path directions sponsored by mundialis

---

## Resources

- [Official r.cost manual](https://grass.osgeo.org/grass-devel/manuals/r.cost.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.cost.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
