# r.in.mat

**Category**: raster

## Description

Imports a binary MAT-File(v4) to a GRASS raster.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_in_mat(input,output=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str, required`**
   - Name of input MAT-File(v4)
   - Used as: input, file, name

2. **`output : str | type(np.ndarray) | type(np.array) | type(gs.array.array), optional`**
   - Name for output raster map (override)
   - Used as: output, raster, name

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

result : grass.tools.support.ToolResult | np.ndarray | tuple[np.ndarray] | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned. If an array type (e.g., np.ndarray) is used for one of the raster outputs, the result will be an array and will have the shape corresponding to the computational region. If an array type is used for more than one raster output, the result will be a tuple of arrays.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

r.in.mat will import a GRASS raster map from a Version 4 MAT-File
which was created with Matlab or Octave. Attributes such as map title
and bounds will also be imported if they exist.

Specifically, the following array variables will be read:

Any other variables in the MAT-file will be simply skipped over.

The ' map_name ' variable is optional, if it exists, and is valid, the
new map will be thus named. If it doesn't exist or a name is specified
with the output= option, the raster map's name will be set to
" MatFile " or the name specified respectively. (maximum 64 characters;
normal GRASS naming rules apply)

The ' map_title ' variable is optional, the map's title is set if it
exists.

The ' map_northern_edge ' and like variables are mandatory unless the
user is importing to a "XY" non-georeferenced project (e.g. imagery
data). Latitude and longitude values should be in decimal form.

---

## See Also

Related tools:
- [`r.out.mat`](https://grass.osgeo.org/grass-devel/manuals/r.out.mat.html)
- [`r.in.ascii`](https://grass.osgeo.org/grass-devel/manuals/r.in.ascii.html)
- [`r.in.bin`](https://grass.osgeo.org/grass-devel/manuals/r.in.bin.html)
- [`r.mapcalc`](https://grass.osgeo.org/grass-devel/manuals/r.mapcalc.html)
- [`r.null.`](https://grass.osgeo.org/grass-devel/manuals/r.null..html)

---

## Resources

- [Official r.in.mat manual](https://grass.osgeo.org/grass-devel/manuals/r.in.mat.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.in.mat.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
