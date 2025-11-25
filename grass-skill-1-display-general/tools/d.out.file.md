# d.out.file

**Category**: display

## Description

Saves the contents of the active display monitor to a graphics file.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.d_out_file(output,format="png",size=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`output : str, required`**
   - Name for output file
   - Used as: output, file, name

2. **`format : str, required`**
   - Graphics file format
   - Allowed values: png, jpg, bmp, gif, tif
   - Default: png

3. **`size : tuple[int, int] | list[int] | str, optional`**
   - Width and height of output image
   - Used as: width,height

4. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

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

d.out.file saves the content of the currently selected monitor into
graphic file. The active monitor can be selected with d.mon . d.out.file can be run from GUI Console tab, too.

---

## See Also

Related tools:
- [`d.redraw`](https://grass.osgeo.org/grass-devel/manuals/d.redraw.html)
- [`d.erase`](https://grass.osgeo.org/grass-devel/manuals/d.erase.html)
- [`d.rast`](https://grass.osgeo.org/grass-devel/manuals/d.rast.html)
- [`d.vect`](https://grass.osgeo.org/grass-devel/manuals/d.vect.html)
- [`d.mon`](https://grass.osgeo.org/grass-devel/manuals/d.mon.html)

---

## Resources

- [Official d.out.file manual](https://grass.osgeo.org/grass-devel/manuals/d.out.file.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/d.out.file.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
