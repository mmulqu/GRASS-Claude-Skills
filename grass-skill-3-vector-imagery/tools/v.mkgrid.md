# v.mkgrid

**Category**: vector

## Description

Creates a vector map of a user-defined grid.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.v_mkgrid(map,grid=None,position="region",coordinates=None,box=None,angle=0,breaks=0,type="area",flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`map : str, required`**
   - Name for output vector map
   - Used as: output, vector, name

2. **`grid : tuple[int, int] | list[int] | str, optional`**
   - Number of rows and columns in grid
   - Used as: rows,columns

3. **`position : str, optional`**
   - Where to place the grid
   - Allowed values: region, coor
   - region: current region
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/v.mkgrid.html#__tabbed_2_3) for all details)*

4. **`coordinates : tuple[float, float] | list[float] | str, optional`**
   - Lower left easting and northing coordinates of map
   - Used as: input, coords, east,north

5. **`box : tuple[float, float] | list[float] | str, optional`**
   - Width and height of boxes in grid
   - Used as: width,height

6. **`angle : float, optional`**
   - Angle of rotation (in degrees counter-clockwise)
   - Default: 0

7. **`breaks : int, optional`**
   - Number of vertex points per grid cell
   - Allowed values: 0-60
   - Default: 0

8. **`type : str, optional`**
   - Output feature type
   - Allowed values: point, line, area
   - Default: area

9. **`flags : str, optional`**
   - Allowed values: h, a, d
   - h
   - Create hexagons (default: rectangles)
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/v.mkgrid.html#__tabbed_2_3) for all details)*

10. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

11. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

12. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

13. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 13 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/v.mkgrid.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

v.mkgrid creates a vector map representation of a regular coordinate
grid. Point, line, and area vector grids can be created.

---

## See Also

Related tools:
- [`d.grid`](https://grass.osgeo.org/grass-devel/manuals/d.grid.html)
- [`v.in.region`](https://grass.osgeo.org/grass-devel/manuals/v.in.region.html)
- [`v.patch`](https://grass.osgeo.org/grass-devel/manuals/v.patch.html)
- [`v.vect.stats`](https://grass.osgeo.org/grass-devel/manuals/v.vect.stats.html)

---

## Authors

Michael Higgins, U.S.Army Construction Engineering Research Laboratory
Update for new vectors Radim Blazek 10/2004

---

## Resources

- [Official v.mkgrid manual](https://grass.osgeo.org/grass-devel/manuals/v.mkgrid.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/v.mkgrid.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
