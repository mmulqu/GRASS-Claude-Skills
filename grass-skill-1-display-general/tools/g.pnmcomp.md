# g.pnmcomp

**Category**: general

## Description

Overlays multiple PPM image files.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.g_pnmcomp(input,mask=None,opacity=None,output,output_mask=None,width,height,bgcolor=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str | list[str], required`**
   - Name of input file(s)
   - Used as: input, file, name

2. **`mask : str | list[str], optional`**
   - Name of input mask file(s)
   - Used as: input, file, name

3. **`opacity : float | list[float] | str, optional`**
   - Layer opacities

4. **`output : str, required`**
   - Name for output file
   - Used as: output, file, name

5. **`output_mask : str, optional`**
   - Name for output mask file
   - Used as: output, file, name

6. **`width : int, required`**
   - Image width

7. **`height : int, required`**
   - Image height

8. **`bgcolor : str, optional`**
   - Background color
   - Either a standard color name or R:G:B triplet
   - Used as: input, color, name

9. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

10. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

11. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

12. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 12 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/g.pnmcomp.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

g.pnmcomp isn't meant for end users. It's an internal tool for use by wxGUI .

In essence, g.pnmcomp generates a PPM image by overlaying a series of
PPM/PGM pairs (PPM = RGB image, PGM = alpha channel).

---

## See Also

Related tools:
- [`g.cairocomp`](https://grass.osgeo.org/grass-devel/manuals/g.cairocomp.html)

---

## Resources

- [Official g.pnmcomp manual](https://grass.osgeo.org/grass-devel/manuals/g.pnmcomp.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/g.pnmcomp.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
