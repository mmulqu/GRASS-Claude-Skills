# r.recode

**Category**: raster

## Description

Recodes categorical raster maps.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_recode(input,output,rules,title=None,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str | np.ndarray, required`**
   - Name of raster map to be recoded
   - Used as: input, raster, name

2. **`output : str | type(np.ndarray) | type(np.array) | type(gs.array.array), required`**
   - Name for output raster map
   - Used as: output, raster, name

3. **`rules : str | io.StringIO, required`**
   - File containing recode rules
   - '-' for standard input
   - Used as: input, file, name

4. **`title : str, optional`**
   - Title for output raster map

5. **`flags : str, optional`**
   - Allowed values: a, d
   - a
   - Align the current region to the input raster map
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/r.recode.html#__tabbed_2_3) for all details)*

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

result : grass.tools.support.ToolResult | np.ndarray | tuple[np.ndarray] | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned. If an array type (e.g., np.ndarray) is used for one of the raster outputs, the result will be an array and will have the shape corresponding to the computational region. If an array type is used for more than one raster output, the result will be a tuple of arrays.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

r.recode creates an output raster map by recoding input raster map
based on recode rules . A title for the output raster map may be
(optionally) specified by the user.

The recode rules can be read from standard input (i.e., from the
keyboard, redirected from a file, or piped through another program) by
entering rules=- .

Rules are defined in one of these formats:

r.recode is loosely based on r.reclass and uses the
GRASS Reclass Library to convert the rasters. It has routines for
converting to every possible combination of raster (eg. CELL to DCELL,
DCELL to FCELL, etc). Standard floating point raster precision is float
(FCELL), with -d double precision (DCELL) will be written.

There are four basic routines that it accepts:

These four sets of arguments can be given on the command line, or piped
via stdin or a file. More than one set of arguments is accepted.

---

## See Also

Related tools:
- [`r.reclass`](https://grass.osgeo.org/grass-devel/manuals/r.reclass.html)

---

## Resources

- [Official r.recode manual](https://grass.osgeo.org/grass-devel/manuals/r.recode.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.recode.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
