# i.spectral

**Category**: imagery

## Description

Displays spectral response at user specified locations in group or images.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.i_spectral(group=None,subgroup=None,raster=None,coordinates,output=None,format="png",flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`group : str, optional`**
   - Name of input imagery group
   - Used as: input, group, name

2. **`subgroup : str, optional`**
   - Name of input imagery subgroup
   - Used as: input, subgroup, name

3. **`raster : str | list[str], optional`**
   - Name of input raster map(s)
   - Used as: input, raster, name

4. **`coordinates : list[tuple[float, float]] | tuple[float, float] | list[float] | str, required`**
   - Coordinates
   - Used as: input, coords, east,north

5. **`output : str, optional`**
   - Name for output image is valid for -g (or text file for -t flag)
   - Used as: output, file, name

6. **`format : str, optional`**
   - Graphics format for output file (valid for -g flag)
   - Allowed values: png, eps, svg
   - Default: png

7. **`flags : str, optional`**
   - Allowed values: c, g, t
   - c
   - Show sampling coordinates instead of numbering in the legend (valid for -g flag)
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/i.spectral.html#__tabbed_2_3) for all details)*

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


*Showing 10 of 11 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/i.spectral.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

i.spectral displays spectral response at user specified locations in
images.

---

## See Also

Related tools:
- [`d.where`](https://grass.osgeo.org/grass-devel/manuals/d.where.html)
- [`r.what`](https://grass.osgeo.org/grass-devel/manuals/r.what.html)

---

## Authors

Markus Neteler Francesco Pirotti

---

## Resources

- [Official i.spectral manual](https://grass.osgeo.org/grass-devel/manuals/i.spectral.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/i.spectral.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
