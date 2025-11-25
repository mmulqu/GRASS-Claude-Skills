# r.out.vtk

**Category**: raster

## Description

Converts raster maps into the VTK-ASCII format.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_out_vtk(input=None,output=None,elevation=None,null=-99999.99,z=0.0,rgbmaps=None,vectormaps=None,zscale=1.0,precision=12,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str | list[str], optional`**
   - Raster map(s) to be converted to VTK-ASCII data format
   - Used as: input, raster, name

2. **`output : str, optional`**
   - Name for VTK-ASCII output file
   - Used as: output, file, name

3. **`elevation : str | np.ndarray, optional`**
   - Name of input elevation raster map
   - Used as: input, raster, name

4. **`null : float, optional`**
   - Value to represent no data cell
   - Default: -99999.99

5. **`z : float, optional`**
   - Constant elevation (if no elevation map is specified)
   - Default: 0.0

6. **`rgbmaps : str | list[str], optional`**
   - Three (r,g,b) raster maps to create RGB values [redmap,greenmap,bluemap]
   - Used as: input, raster

7. **`vectormaps : str | list[str], optional`**
   - Three (x,y,z) raster maps to create vector values [xmap,ymap,zmap]
   - Used as: input, raster

8. **`zscale : float, optional`**
   - Scale factor for elevation
   - Default: 1.0

9. **`precision : int, optional`**
   - Number of significant digits (floating point only)
   - Allowed values: 0-20
   - Default: 12

10. **`flags : str, optional`**
   - Allowed values: p, s, t, v, o, c
   - p
   - Create VTK point data instead of VTK cell data (if no elevation map is given)
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/r.out.vtk.html#__tabbed_2_3) for all details)*

11. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

12. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

13. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

14. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 14 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/r.out.vtk.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

Outputs raster maps in VTK-ASCII format. Map's are valid raster
map's in the current mapset. output is the name of an VTK-ASCII file
which will be written in the current working directory. If output is
not specified then stdout is used. The module is sensitive to region
settings (set with g.region).

Elevation, scaling, point/celldata, vector and RGB Data are supported.
If the map is in LL projection, the elevation values will automatically
scaled to degrees. It is supposed that the elevation values are provided
in meters. If the elevation values are in a different unit than meters,
use the scale parameter to convert the units.

If no elevation map is given, the user can set the height of the map by
one value. Point or cell data are available. Also scaling is supported
for this elevation value. The elevation value must be provided in
meters.

The RGB input requires three raster maps: red, green, blue - in this
order. The maps must have values between 0 and 255, otherwise you will
get lots of warnings and the values are set to 0. More than one RGB
dataset (3 maps) is not supported.

The vector input requires three raster maps: x, y, z -- defining the
vector coordinates - in this order. More than one vector dataset (3
maps) is not supported.

---

## See Also

Related tools:
- [`r3.out.vtk`](https://grass.osgeo.org/grass-devel/manuals/r3.out.vtk.html)
- [`r.out.ascii`](https://grass.osgeo.org/grass-devel/manuals/r.out.ascii.html)
- [`g.region`](https://grass.osgeo.org/grass-devel/manuals/g.region.html)

---

## Resources

- [Official r.out.vtk manual](https://grass.osgeo.org/grass-devel/manuals/r.out.vtk.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.out.vtk.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
