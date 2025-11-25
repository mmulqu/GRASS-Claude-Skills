# r.distance

**Category**: raster

## Description

Locates the closest points between objects in two raster maps.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_distance(map,separator=None,sort=None,format="plain",flags=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`map : list[tuple[str, str]] | tuple[str, str] | list[str] | str, required`**
   - Name of two input raster maps for computing inter-class distances
   - Used as: input, raster, name1,name2

2. **`separator : str, optional`**
   - Field separator
   - Special characters: pipe, comma, space, tab, newline
   - Used as: input, separator, character

3. **`sort : str, optional`**
   - Sort output by distance
   - Default: sorted by categories
   - Allowed values: asc, desc
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/r.distance.html#__tabbed_2_3) for all details)*

4. **`format : str, required`**
   - Output format
   - Used as: name
   - Allowed values: plain, csv, json
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/r.distance.html#__tabbed_2_3) for all details)*

5. **`flags : str, optional`**
   - Allowed values: l, o, n
   - l
   - Include category labels in the output
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/r.distance.html#__tabbed_2_3) for all details)*

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

r.distance locates the closest points between "objects" in two raster
maps. An "object" is defined as all the grid cells that have the same
category number, and closest means having the shortest "straight-line"
distance. The cell centers are considered for the distance calculation
(two adjacent grid cells have the distance between their cell centers).

The output is an ascii list, one line per pair of objects, in the
following form:

from_category Category number from map1

to_category Category number from map2

distance The distance in meters between "from_category" and "to_category"

from_easting,from_northing The coordinates of the grid cell "from_category" which is closest to "to_category"

to_easting,to_northing The coordinates of the grid cell "to_category" which is closest to "from_category"

-l The -l flag outputs the category labels of the matched raster
objects at the beginning of the line, if they exist.

-o The -o flag reports zero distance if the input rasters are
overlapping.

---

## See Also

Related tools:
- [`r.buffer`](https://grass.osgeo.org/grass-devel/manuals/r.buffer.html)
- [`r.cost`](https://grass.osgeo.org/grass-devel/manuals/r.cost.html)
- [`r.drain`](https://grass.osgeo.org/grass-devel/manuals/r.drain.html)
- [`r.grow`](https://grass.osgeo.org/grass-devel/manuals/r.grow.html)
- [`r.grow.distance`](https://grass.osgeo.org/grass-devel/manuals/r.grow.distance.html)
- [`v.distance`](https://grass.osgeo.org/grass-devel/manuals/v.distance.html)

---

## Resources

- [Official r.distance manual](https://grass.osgeo.org/grass-devel/manuals/r.distance.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.distance.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
