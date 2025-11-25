# r.object.geometry

**Category**: raster

## Description

Calculates geometry parameters for raster objects.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_object_geometry(input,output=None,separator="pipe",format="plain",flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str | np.ndarray, required`**
   - Name of input raster map
   - Used as: input, raster, name

2. **`output : str, optional`**
   - Name for output file
   - Used as: output, file, name

3. **`separator : str, optional`**
   - Field separator
   - Special characters: pipe, comma, space, tab, newline
   - Used as: input, separator, character

4. **`format : str, required`**
   - Output format
   - Used as: name
   - Allowed values: plain, json
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/r.object.geometry.html#__tabbed_2_3) for all details)*

5. **`flags : str, optional`**
   - Allowed values: m
   - m
   - Use meters as units instead of cells

6. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

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

r.object.geometry calculates form statistics of raster objects in the input map and writes it to the output text file (or standard
output if no output filename or '-' is given), with fields separated by
the chosen separator . Objects are defined as clumps of adjacent
cells with the same category value (e.g. output of r.clump or i.segment ).

By default, values are in pixels. If values in meters is desired, the
user can set the -m flag. If the current working region is in
lat-long or has non-square pixels, using meters is recommended.

Statistics currently calculated are exactly the same as in v.to.db (except for compact_square and mean
coordinates):

---

## See Also

Related tools:
- [`i.segment`](https://grass.osgeo.org/grass-devel/manuals/i.segment.html)
- [`r.clump`](https://grass.osgeo.org/grass-devel/manuals/r.clump.html)
- [`v.to.db`](https://grass.osgeo.org/grass-devel/manuals/v.to.db.html)

---

## Authors

Moritz Lennert Markus Metz (diagonal clump tracing)

---

## Resources

- [Official r.object.geometry manual](https://grass.osgeo.org/grass-devel/manuals/r.object.geometry.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.object.geometry.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
