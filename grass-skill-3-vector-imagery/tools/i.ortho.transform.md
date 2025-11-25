# i.ortho.transform

**Category**: imagery

## Description

Computes a coordinate transformation based on the control points.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.i_ortho_transform(group,format="fd,rd",coords=None,flags=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`group : str, required`**
   - Name of input imagery group
   - Used as: input, group, name

2. **`format : str | list[str], optional`**
   - Output format
   - Allowed values: idx, src, dst, fwd, rev, fxy, rxy, fd, rd
   - idx: point index
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/i.ortho.transform.html#__tabbed_2_3) for all details)*

3. **`coords : str | io.StringIO, optional`**
   - File containing coordinates to transform ("-" to read from stdin)
   - Local x,y,z coordinates to target east,north,height
   - Used as: input, file, name

4. **`flags : str, optional`**
   - Allowed values: s, r, x, p
   - s
   - Display summary information
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/i.ortho.transform.html#__tabbed_2_3) for all details)*

5. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

6. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

7. **`superquiet : bool, optional`**
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

i.ortho.transform is an utility to compute transformation based upon
GCPs and output error measurements.

If coordinates are given with the input file option or fed from stdin , both the input and the output format is "x y z" with one
coordinate pair per line. Reverse transform is performed with the -r flag.

The format option determines how control points are printed out. A
summary on the control points can be printed with the -s flag. The
summary includes maximum deviation observed when transforming GCPs and
overall RMS. The format option is ignored when coordinates are given
with the input file option.

---

## See Also

Related tools:
- [`i.rectify`](https://grass.osgeo.org/grass-devel/manuals/i.rectify.html)

---

## Authors

Brian J. Buckley Glynn Clements Hamish Bowman

---

## Resources

- [Official i.ortho.transform manual](https://grass.osgeo.org/grass-devel/manuals/i.ortho.transform.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/i.ortho.transform.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
