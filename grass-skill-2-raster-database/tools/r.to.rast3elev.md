# r.to.rast3elev

**Category**: raster

## Description

Creates a 3D volume map based on 2D elevation and value raster maps.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_to_rast3elev(input,elevation,output,upper=None,lower=None,tilesize=32,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str | list[str], required`**
   - Name of input raster map(s)
   - Used as: input, raster, name

2. **`elevation : str | list[str], required`**
   - Name of input elevation raster map(s)
   - Used as: input, raster, name

3. **`output : str, required`**
   - Name for output 3D raster map
   - Used as: output, raster_3d, name

4. **`upper : float, optional`**
   - The value to fill the upper cells, default is null

5. **`lower : float, optional`**
   - The value to fill the lower cells, default is null

6. **`tilesize : int, optional`**
   - The maximum tile size in kilo bytes. Default is 32KB.
   - Default: 32

7. **`flags : str, optional`**
   - Allowed values: u, l, m
   - u
   - Use the input map values to fill the upper cells
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/r.to.rast3elev.html#__tabbed_2_3) for all details)*

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


*Showing 10 of 11 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/r.to.rast3elev.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

r.to.rast3elev creates a 3D volume map based on 2D elevation and value
raster maps. If the 2d and 3d region settings are different, the 2d
resolution will be adjust to the 3d resolution.

How r.to.rast3elev works

---

## See Also

Related tools:
- [`r.to.rast3`](https://grass.osgeo.org/grass-devel/manuals/r.to.rast3.html)
- [`r3.cross.rast`](https://grass.osgeo.org/grass-devel/manuals/r3.cross.rast.html)
- [`g.region`](https://grass.osgeo.org/grass-devel/manuals/g.region.html)

---

## Resources

- [Official r.to.rast3elev manual](https://grass.osgeo.org/grass-devel/manuals/r.to.rast3elev.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.to.rast3elev.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
