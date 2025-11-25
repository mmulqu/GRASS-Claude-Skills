# v.out.svg

**Category**: vector

## Description

Exports a vector map to SVG file.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.v_out_svg(input,layer="-1",output,type="poly",precision=6,attribute=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
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
   - Name for SVG output file
   - Used as: output, file, name

4. **`type : str, required`**
   - Output type
   - Defines which feature-type will be extracted
   - Allowed values: poly, line, point

5. **`precision : int, optional`**
   - Coordinate precision
   - Default: 6

6. **`attribute : str | list[str], optional`**
   - Attribute(s) to include in output SVG
   - Used as: input, dbcolumn, name

7. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

8. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

9. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

10. **`superquiet : bool, optional`**
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

v.out.svg converts GRASS vector data to SVG (Scalable Vector Graphics)
code notation. In particular, it

The precision parameter controls the number of decimals for
coordinates output ( precision=0 corresponds to integer precision in
the output SVG file).

---

## See Also

Related tools:
- [`v.out.ogr`](https://grass.osgeo.org/grass-devel/manuals/v.out.ogr.html)

---

## Resources

- [Official v.out.svg manual](https://grass.osgeo.org/grass-devel/manuals/v.out.svg.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/v.out.svg.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
