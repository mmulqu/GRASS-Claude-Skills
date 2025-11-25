# v.out.pov

**Category**: vector

## Description

Converts GRASS x,y,z points to POV-Ray x,z,y format.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.v_out_pov(input,layer="-1",type="point,line,area,face",output,size="10",zmod=None,objmod=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str, required`**
   - Name of input vector map
   - Or data source for direct OGR access
   - Used as: input, vector, name

2. **`layer : str, optional`**
   - Layer number or name ('-1' for all layers)
   - A single vector map can be connected to multiple database tables. This number determines which table to use. When used with direct OGR access this is the layer name.
   - Used as: input, layer

3. **`type : str | list[str], optional`**
   - Input feature type
   - Allowed values: point, line, boundary, centroid, area, face, kernel
   - Default: point,line,area,face

4. **`output : str, required`**
   - Name for output POV file
   - Used as: output, file, name

5. **`size : str, optional`**
   - Radius of sphere for points and tube for lines
   - May be also variable, e.g. grass_r.
   - Default: 10

6. **`zmod : str, optional`**
   - This string is appended to each z coordinate. Examples: '*10', '+1000', '*10+100', '*exaggeration'

7. **`objmod : str, optional`**
   - Object modifier (OBJECT_MODIFIER in POV-Ray documentation)
   - Example: "pigment { color red 0 green 1 blue 0 }"

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


*Showing 10 of 11 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/v.out.pov.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

v.out.pov converts GRASS vector data to POV-Ray format
( )

---

## See Also

Related tools:
- [`r.out.pov`](https://grass.osgeo.org/grass-devel/manuals/r.out.pov.html)

---

## Resources

- [Official v.out.pov manual](https://grass.osgeo.org/grass-devel/manuals/v.out.pov.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/v.out.pov.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
