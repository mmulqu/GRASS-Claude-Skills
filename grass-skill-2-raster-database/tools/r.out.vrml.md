# r.out.vrml

**Category**: raster

## Description

Exports a raster map to the Virtual Reality Modeling Language (VRML).

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_out_vrml(elevation,color=None,exaggeration=1.0,output,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`elevation : str | np.ndarray, required`**
   - Name of input elevation raster map
   - Used as: input, raster, name

2. **`color : str | np.ndarray, optional`**
   - Name of input color map
   - Used as: input, raster, name

3. **`exaggeration : float, optional`**
   - Vertical exaggeration
   - Default: 1.0

4. **`output : str, required`**
   - Name for output VRML file
   - Used as: output, file, name

5. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

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

This module exports a GRASS raster map to the Virtual Reality Modeling
Language (VRML) format for 3D visualization.

This version only outputs raster maps in VRML 1.0 format. The newer VRML
2.0 format will be more efficient for geographic applications, as it
introduces an "ElevationGrid" node so that only the elevation points
will have to be written instead of the whole geometry. The vast majority
of VRML viewers currently only support VRML 1.0. If the extension "wrl"
(world) is not present in the he output parameter, it will be added.

---

## Resources

- [Official r.out.vrml manual](https://grass.osgeo.org/grass-devel/manuals/r.out.vrml.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.out.vrml.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
