# r.tileset

**Category**: raster

## Description

Produces tilings of the source projection for use in the destination region and projection.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_tileset(region=None,sourceproj,sourcescale="1",destproj=None,destscale=None,maxcols=1024,maxrows=1024,overlap=0,separator="pipe",flags=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`region : str, optional`**
   - Name of region to use instead of current region for bounds and resolution

2. **`sourceproj : str, required`**
   - Source projection

3. **`sourcescale : str, optional`**
   - Conversion factor from units to meters in source projection
   - Default: 1

4. **`destproj : str, optional`**
   - Destination projection, defaults to this location's projection

5. **`destscale : str, optional`**
   - Conversion factor from units to meters in source projection

6. **`maxcols : int, optional`**
   - Maximum number of columns for a tile in the source projection
   - Default: 1024

7. **`maxrows : int, optional`**
   - Maximum number of rows for a tile in the source projection
   - Default: 1024

8. **`overlap : int, optional`**
   - Number of cells tiles should overlap in each direction
   - Default: 0

9. **`separator : str, optional`**
   - Field separator
   - Output field separator
   - Used as: input, separator, character

10. **`flags : str, optional`**
   - Allowed values: g, w
   - g
   - Produces shell script output
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/r.tileset.html#__tabbed_2_3) for all details)*

11. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

12. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

13. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 13 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/r.tileset.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

r.tileset generates sets of tiles in another projection that cover a
region in this projection with adequate resolution. By default the
current region and its resolution are used, the bounds and resolution of
another region can be used via the region option.

---

## Authors

Cedric Shock Updated for GRASS 7 by Martin Landa, CTU in Prague, Czech Republic

---

## Resources

- [Official r.tileset manual](https://grass.osgeo.org/grass-devel/manuals/r.tileset.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.tileset.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
