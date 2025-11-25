# r.drain

**Category**: raster

## Description

Traces a flow through an elevation model or cost surface on a raster map.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_drain(input,direction=None,output,drain=None,start_coordinates=None,start_points=None,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str | np.ndarray, required`**
   - Name of input elevation or cost surface raster map
   - Used as: input, raster, name

2. **`direction : str | np.ndarray, optional`**
   - Name of input movement direction map associated with the cost surface
   - Direction in degrees CCW from east
   - Used as: input, raster, name

3. **`output : str | type(np.ndarray) | type(np.array) | type(gs.array.array), required`**
   - Name for output raster map
   - Used as: output, raster, name

4. **`drain : str, optional`**
   - Name for output drain vector map
   - Recommended for cost surface made using knight's move
   - Used as: output, vector, name

5. **`start_coordinates : list[tuple[float, float]] | tuple[float, float] | list[float] | str, optional`**
   - Coordinates of starting point(s) (E,N)
   - Used as: input, coords, east,north

6. **`start_points : str | list[str], optional`**
   - Name of starting vector points map(s)
   - Used as: input, vector, name

7. **`flags : str, optional`**
   - Allowed values: c, a, n, d
   - c
   - Copy input cell values on output
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/r.drain.html#__tabbed_2_3) for all details)*

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


*Showing 10 of 11 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/r.drain.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | np.ndarray | tuple[np.ndarray] | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned. If an array type (e.g., np.ndarray) is used for one of the raster outputs, the result will be an array and will have the shape corresponding to the computational region. If an array type is used for more than one raster output, the result will be a tuple of arrays.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

r.drain traces a flow through a least-cost path in an elevation model
or cost surface. For cost surfaces, a movement direction map must be
specified with the direction option and the -d flag to trace a
flow path following the given directions. Such a movement direction map
can be generated with r.walk , r.cost , r.slope.aspect or r.watershed provided that the direction is in degrees, measured counterclockwise
from east.

The output raster map will show one or more least-cost paths between
each user-provided location(s) and the minima (low category values) in
the raster input map. If the -d flag is used the output
least-cost paths will be found using the direction raster map. By
default, the output will be an integer CELL map with category 1
along the least cost path, and null cells elsewhere.

With the -c ( copy ) flag, the input raster map cell values are
copied verbatim along the path. With the -a ( accumulate ) flag, the
accumulated cell value from the starting point up to the current cell is
written on output. With either the -c or the -a flags, the output map is created with the same cell type as the input raster map (integer, float or double). With the -n ( number ) flag,
the cells are numbered consecutively from the starting point to the
final point. The -c , -a , and -n flags are mutually
incompatible.

For an elevation surface, the path is calculated by choosing the steeper
"slope" between adjacent cells. The slope calculation accurately
accounts for the variable scale in lat-lon projections. For a cost
surface, the path is calculated by following the movement direction
surface back to the start point given in r.walk or r.cost . The path search stops as soon as a region border
or a neighboring NULL cell is encountered, because in these cases the
direction can not be determined (the path could continue outside the
current region).

The start_coordinates parameter consists of map E and N grid
coordinates of a starting point. Each x,y pair is the easting and
northing (respectively) of a starting point from which a least-cost
corridor will be developed. The start_points parameter can take
multiple vector maps containing additional starting points. Up to 1024
starting points can be input from a combination of the start_coordinates and start_points parameters.

Consider the following example:

The user-provided starting location in the above example is the boxed 19 in the left-hand map. The path in the output shows the least-cost
corridor for moving from the starting box to the lowest (smallest)
possible point. This is the path a raindrop would take in this
landscape.

With the -c (copy) flag, you get the following result:

With the -a (accumulate) flag, you get the following result:

With the -n (number) flag, you get the following result:

With the -d (direction) flag, the direction raster is used for the
input, rather than the elevation surface. The output is then created
according to one of the -can flags.

---

## See Also

Related tools:
- [`g.region`](https://grass.osgeo.org/grass-devel/manuals/g.region.html)
- [`r.cost`](https://grass.osgeo.org/grass-devel/manuals/r.cost.html)
- [`r.fill.dir`](https://grass.osgeo.org/grass-devel/manuals/r.fill.dir.html)
- [`r.basins.fill`](https://grass.osgeo.org/grass-devel/manuals/r.basins.fill.html)
- [`r.watershed`](https://grass.osgeo.org/grass-devel/manuals/r.watershed.html)
- [`r.terraflow`](https://grass.osgeo.org/grass-devel/manuals/r.terraflow.html)
- [`r.mapcalc`](https://grass.osgeo.org/grass-devel/manuals/r.mapcalc.html)
- [`r.walk`](https://grass.osgeo.org/grass-devel/manuals/r.walk.html)

---

## Authors

Completely rewritten by Roger S. Miller, 2001 July 2004 at WebValley 2004, error checking and vector points added by
Matteo Franchi (Liceo Leonardo Da Vinci, Trento) and Roberto Flor
(ITC-irst, Trento, Italy)

---

## Resources

- [Official r.drain manual](https://grass.osgeo.org/grass-devel/manuals/r.drain.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.drain.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
