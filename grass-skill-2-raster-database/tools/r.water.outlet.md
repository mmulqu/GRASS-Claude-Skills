# r.water.outlet

**Category**: raster

## Description

Creates watershed basins from a drainage direction map.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_water_outlet(input,output,coordinates,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str | np.ndarray, required`**
   - Name of input drainage direction map
   - Used as: input, raster, name

2. **`output : str | type(np.ndarray) | type(np.array) | type(gs.array.array), required`**
   - Name for output watershed basin map
   - Used as: output, raster, name

3. **`coordinates : tuple[float, float] | list[float] | str, required`**
   - Coordinates of outlet point
   - Used as: input, coords, east,north

4. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

5. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

6. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

7. **`superquiet : bool, optional`**
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

r.water.outlet generates a watershed basin from a drainage direction
map and a set of coordinates representing the outlet point of the watershed.

Input drainage direction map indicates the "aspect" for each cell.
Multiplying positive values by 45 will give the direction in degrees
that the surface runoff will travel from that cell. The value -1
indicates that the cell is a depression area. Other negative values
indicate that surface runoff is leaving the boundaries of the current
geographic region. The absolute value of these negative cells indicates
the direction of flow. This raster map is generated from r.watershed .

Output raster map values of one (1) indicate the watershed basin. Values
of zero (0) are not in the watershed basin.

---

## See Also

Related tools:
- [`r.wateroutlet.lessmem`](https://grass.osgeo.org/grass-devel/manuals/r.wateroutlet.lessmem.html)
- [`d.where`](https://grass.osgeo.org/grass-devel/manuals/d.where.html)
- [`r.basins.fill`](https://grass.osgeo.org/grass-devel/manuals/r.basins.fill.html)
- [`r.watershed`](https://grass.osgeo.org/grass-devel/manuals/r.watershed.html)
- [`r.topidx`](https://grass.osgeo.org/grass-devel/manuals/r.topidx.html)

---

## Resources

- [Official r.water.outlet manual](https://grass.osgeo.org/grass-devel/manuals/r.water.outlet.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.water.outlet.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
