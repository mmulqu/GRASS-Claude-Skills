# v.parallel

**Category**: vector

## Description

Creates parallel line to input vector lines.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.v_parallel(input,layer="-1",output,distance,minordistance=None,angle=0,side="right",tolerance=None,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
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

3. **`output : str, required`**
   - Name for output vector map
   - Used as: output, vector, name

4. **`distance : float, required`**
   - Offset along major axis in map units
   - Allowed values: 0-100000000

5. **`minordistance : float, optional`**
   - Offset along minor axis in map units
   - Allowed values: 0-100000000

6. **`angle : float, optional`**
   - Angle of major axis in degrees
   - Default: 0

7. **`side : str, required`**
   - Side
   - Allowed values: left, right, both
   - left: Parallel line is on the left
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/v.parallel.html#__tabbed_2_3) for all details)*

8. **`tolerance : float, optional`**
   - Tolerance of arc polylines in map units
   - Allowed values: 0-100000000

9. **`flags : str, optional`**
   - Allowed values: r, b
   - r
   - Make outside corners round
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/v.parallel.html#__tabbed_2_3) for all details)*

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


*Showing 10 of 13 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/v.parallel.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

v.parallel creates parallel lines to the input vector lines which can
be used as half-buffers.

---

## See Also

Related tools:
- [`v.buffer`](https://grass.osgeo.org/grass-devel/manuals/v.buffer.html)

---

## Authors

Radim Blazek Rewritten by Rosen Matev (with support through the Google Summer of Code
program 2008)

---

## Resources

- [Official v.parallel manual](https://grass.osgeo.org/grass-devel/manuals/v.parallel.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/v.parallel.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
