# r.out.mat

**Category**: raster

## Description

Exports a GRASS raster to a binary MAT-File.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_out_mat(input,output,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str | np.ndarray, required`**
   - Name of input raster map
   - Used as: input, raster, name

2. **`output : str, required`**
   - Name for output binary MAT file
   - Used as: output, file, name

3. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

4. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

5. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

6. **`superquiet : bool, optional`**
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

r.out.mat will export a GRASS raster map to a MAT-File which can be
loaded into Matlab or Octave for plotting or further analysis.
Attributes such as map title and bounds will also be exported into
additional array variables.

Specifically, the following array variables are created:

In addition, r.out.mat makes for a nice binary container format for
transferring georeferenced maps around, even if you don't use Matlab or
Octave.

---

## See Also

Related tools:
- [`r.in.mat`](https://grass.osgeo.org/grass-devel/manuals/r.in.mat.html)
- [`r.out.ascii`](https://grass.osgeo.org/grass-devel/manuals/r.out.ascii.html)
- [`r.out.bin`](https://grass.osgeo.org/grass-devel/manuals/r.out.bin.html)
- [`r.null`](https://grass.osgeo.org/grass-devel/manuals/r.null.html)

---

## Resources

- [Official r.out.mat manual](https://grass.osgeo.org/grass-devel/manuals/r.out.mat.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.out.mat.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
