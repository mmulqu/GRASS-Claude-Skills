# r.lake

**Category**: raster

## Description

Fills lake at given point to given level.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_lake(elevation,water_level,lake=None,coordinates=None,seed=None,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`elevation : str | np.ndarray, required`**
   - Name of input elevation raster map
   - Used as: input, raster, name

2. **`water_level : float, required`**
   - Water level

3. **`lake : str | type(np.ndarray) | type(np.array) | type(gs.array.array), optional`**
   - Name for output raster map
   - Used as: output, raster, name

4. **`coordinates : tuple[float, float] | list[float] | str, optional`**
   - Seed point coordinates
   - Either this coordinates pair or a seed map have to be specified
   - Used as: input, coords, east,north

5. **`seed : str | np.ndarray, optional`**
   - Input raster map with given starting point(s) (at least 1 cell > 0)
   - Either this parameter or a coordinates pair have to be specified
   - Used as: input, raster, name

6. **`flags : str, optional`**
   - Allowed values: n, o
   - n
   - Use negative depth values for lake raster map
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/r.lake.html#__tabbed_2_3) for all details)*

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

r.lake fills a lake to a target water level from a given start point.
The user can think of it as r.grow with additional checks
for elevation. The resulting raster map contains cells with values
representing lake depth and NULL for all other cells beyond the lake.
Lake depth is reported relative to specified water level (specified
level = 0 depth).

This module uses a 3x3 moving window approach to find all cells that
match three criteria and to define the lake:

The water level must be in DEM units.

---

## See Also

Related tools:
- [`r.mapcalc`](https://grass.osgeo.org/grass-devel/manuals/r.mapcalc.html)
- [`r.grow`](https://grass.osgeo.org/grass-devel/manuals/r.grow.html)
- [`r.plane`](https://grass.osgeo.org/grass-devel/manuals/r.plane.html)

---

## Resources

- [Official r.lake manual](https://grass.osgeo.org/grass-devel/manuals/r.lake.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.lake.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
