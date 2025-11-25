# r.out.bin

**Category**: raster

## Description

Exports a GRASS raster to a binary array.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_out_bin(input,output=None,null=0,bytes=None,order="native",flags=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str | np.ndarray, required`**
   - Name of input raster map
   - Used as: input, raster

2. **`output : str, optional`**
   - Name for output binary map (use output=- for stdout)

3. **`null : float, optional`**
   - Value to write out for null
   - Default: 0

4. **`bytes : int, optional`**
   - Number of bytes per cell
   - Allowed values: 1, 2, 4, 8

5. **`order : str, optional`**
   - Output byte order
   - Allowed values: big, little, native, swap
   - Default: native

6. **`flags : str, optional`**
   - Allowed values: i, f, h, b, s
   - i
   - Generate integer output
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/r.out.bin.html#__tabbed_2_3) for all details)*

7. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

8. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

9. **`superquiet : bool, optional`**
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

The r.out.bin program exports a GRASS raster map to a binary array
file. Optionally, output can be sent to standard output (stdout) for
direct input (pipe) into other applications. Data is exported according
to the original GRASS raster type (e.g. float). If the "-i" flag is
specified, an integer array is output. The region parameters are printed
to stderr.

---

## See Also

Related tools:
- [`r.in.bin`](https://grass.osgeo.org/grass-devel/manuals/r.in.bin.html)
- [`r.in.ascii`](https://grass.osgeo.org/grass-devel/manuals/r.in.ascii.html)
- [`r.in.gdal`](https://grass.osgeo.org/grass-devel/manuals/r.in.gdal.html)
- [`r.out.ascii`](https://grass.osgeo.org/grass-devel/manuals/r.out.ascii.html)

---

## Resources

- [Official r.out.bin manual](https://grass.osgeo.org/grass-devel/manuals/r.out.bin.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.out.bin.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
