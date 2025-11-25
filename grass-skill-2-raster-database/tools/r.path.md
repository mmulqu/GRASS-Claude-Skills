# r.path

**Category**: raster

## Description

Traces paths from starting points following input directions.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_path(input,format="auto",values=None,raster_path=None,vector_path=None,start_coordinates=None,start_points=None,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str | np.ndarray, required`**
   - Name of input direction
   - Direction in degrees CCW from east, or bitmask encoded
   - Used as: input, raster, name

2. **`format : str, required`**
   - Format of the input direction map
   - Allowed values: auto, degree, 45degree, bitmask
   - auto: auto-detect direction format
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/r.path.html#__tabbed_2_3) for all details)*

3. **`values : str | np.ndarray, optional`**
   - Name of input raster values to be used for output
   - Name of input raster map
   - Used as: input, raster, name

4. **`raster_path : str | type(np.ndarray) | type(np.array) | type(gs.array.array), optional`**
   - Name for output raster path map
   - Name for output raster map
   - Used as: output, raster, name

5. **`vector_path : str, optional`**
   - Name for output vector path map
   - Name for output vector map
   - Used as: output, vector, name

6. **`start_coordinates : list[tuple[float, float]] | tuple[float, float] | list[float] | str, optional`**
   - Coordinates of starting point(s) (E,N)
   - Used as: input, coords, east,north

7. **`start_points : str | list[str], optional`**
   - Name of starting vector points map(s)
   - Or data source(s) for direct OGR access
   - Used as: input, vector, name

8. **`flags : str, optional`**
   - Allowed values: e, b, c, a, n
   - e
   - Start bitmask encoded directions from East (e.g., r.terraflow)
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/r.path.html#__tabbed_2_3) for all details)*

9. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

10. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

11. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

12. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 12 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/r.path.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | np.ndarray | tuple[np.ndarray] | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned. If an array type (e.g., np.ndarray) is used for one of the raster outputs, the result will be an array and will have the shape corresponding to the computational region. If an array type is used for more than one raster output, the result will be a tuple of arrays.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

r.path traces a path from starting points following input directions.
Such a movement direction map can be generated with r.walk , r.cost , r.slope.aspect , r.watershed ,
or r.fill.dir , provided that the direction is in
degrees, measured counterclockwise from east.

Alternatively, bitmask-encoded directions can be provided where each bit
position corresponds to a specific neighbour. A path will continue to
all neighbours with their bit set. This means a path can split and
merge. Such bitmasked directions can be created with the -b flag of r.cost and r.walk .

A path stops when the direction is zero or negative, indicating a stop
point or outlet.

The output raster map will show one or more least-cost paths between
each user-provided location(s) and the target points (direction ≤ 0). By
default, the output will be an integer CELL map with the id of the
start points along the least cost path, and null cells elsewhere.

With the -c ( copy ) flag, the values raster map cell values are
copied verbatim along the path. With the -a ( accumulate ) flag, the
accumulated cell value from the starting point up to the current cell is
written on output. With either the -c or the -a flags, the raster_path map is created with the same cell type as the values raster map (integer, float or double). With the -n ( number ) flag,
the cells are numbered consecutively from the starting point to the
final point. The -c , -a , and -n flags are mutually
incompatible.

The start_coordinates parameter consists of map E and N grid
coordinates of a starting point. Each x,y pair is the easting and
northing (respectively) of a starting point from which a path will be
traced following input directions. The start_points parameter
can take multiple vector maps containing additional starting points.

---

## See Also

Related tools:
- [`g.region`](https://grass.osgeo.org/grass-devel/manuals/g.region.html)
- [`r.basins.fill`](https://grass.osgeo.org/grass-devel/manuals/r.basins.fill.html)
- [`r.cost`](https://grass.osgeo.org/grass-devel/manuals/r.cost.html)
- [`r.fill.dir`](https://grass.osgeo.org/grass-devel/manuals/r.fill.dir.html)
- [`r.mapcalc`](https://grass.osgeo.org/grass-devel/manuals/r.mapcalc.html)
- [`r.recode`](https://grass.osgeo.org/grass-devel/manuals/r.recode.html)
- [`r.terraflow`](https://grass.osgeo.org/grass-devel/manuals/r.terraflow.html)
- [`r.walk`](https://grass.osgeo.org/grass-devel/manuals/r.walk.html)
- [`r.watershed`](https://grass.osgeo.org/grass-devel/manuals/r.watershed.html)

---

## Resources

- [Official r.path manual](https://grass.osgeo.org/grass-devel/manuals/r.path.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.path.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
