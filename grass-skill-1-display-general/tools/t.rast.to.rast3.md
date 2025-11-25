# t.rast.to.rast3

**Category**: temporal

## Description

Converts a space time raster dataset into a 3D raster map.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.t_rast_to_rast3(input,output,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str, required`**
   - Name of the input space time raster dataset
   - Used as: input, strds, name

2. **`output : str, required`**
   - Name for output 3D raster map
   - Used as: output, raster_3d, name

3. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

4. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

5. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

6. **`superquiet : bool, optional`**
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

t.rast.to.rast3 is designed to convert a space time raster dataset
(STRDS) into a space time voxel cube. A space time voxel cube is a 3
dimensional raster map layer (3D raster map or voxel map layer) that as
time as unit for the z-dimension.

A space time raster dataset that should be converted into a space time
voxel cube must have a valid temporal topology. Hence, overlapping or
inclusion of time stamps is not allowed. The granularity of the STRDS is
used to set the resolution of the 3D raster map layer and to sample the
registered time stamped raster map layers.

Gaps between raster map layer in the STRDS will be represented by NULL
values in the voxel map layer.

---

## See Also

Related tools:
- [`r3.mapcalc`](https://grass.osgeo.org/grass-devel/manuals/r3.mapcalc.html)
- [`r3.info`](https://grass.osgeo.org/grass-devel/manuals/r3.info.html)

---

## Resources

- [Official t.rast.to.rast3 manual](https://grass.osgeo.org/grass-devel/manuals/t.rast.to.rast3.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/t.rast.to.rast3.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
