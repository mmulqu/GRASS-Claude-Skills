# v.out.vtk

**Category**: vector

## Description

Converts a vector map to VTK ASCII output.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.v_out_vtk(input,layer="1",output=None,type="point,kernel,centroid,line,boundary,area,face",precision=None,zscale=1.0,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str, required`**
   - Name of input vector map
   - Or data source for direct OGR access
   - Used as: input, vector, name

2. **`layer : str, optional`**
   - Layer number or name
   - Vector features can have category values in different layers. This number determines which layer to use. When used with direct OGR access this is the layer name.
   - Used as: input, layer

3. **`output : str, optional`**
   - Name for output VTK file
   - Used as: output, file, name

4. **`type : str | list[str], optional`**
   - Input feature type
   - Allowed values: point, kernel, centroid, line, boundary, area, face
   - Default: point,kernel,centroid,line,boundary,area,face

5. **`precision : int, optional`**
   - Number of significant digits

6. **`zscale : float, optional`**
   - Scale factor for elevation
   - Default: 1.0

7. **`flags : str, optional`**
   - Allowed values: c, n
   - c
   - Correct the coordinates to fit the VTK-OpenGL precision
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/v.out.vtk.html#__tabbed_2_3) for all details)*

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


*Showing 10 of 11 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/v.out.vtk.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

v.out.vtk converts a GRASS vector map in binary format to the VTK
ASCII output.

If the output parameter is not given, the output will be send to
stdout.

---

## See Also

Related tools:
- [`v.out.ascii`](https://grass.osgeo.org/grass-devel/manuals/v.out.ascii.html)
- [`r.out.vtk`](https://grass.osgeo.org/grass-devel/manuals/r.out.vtk.html)
- [`r3.out.vtk`](https://grass.osgeo.org/grass-devel/manuals/r3.out.vtk.html)

---

## Resources

- [Official v.out.vtk manual](https://grass.osgeo.org/grass-devel/manuals/v.out.vtk.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/v.out.vtk.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
