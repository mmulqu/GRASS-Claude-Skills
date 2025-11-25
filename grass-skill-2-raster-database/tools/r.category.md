# r.category

**Category**: raster

## Description

Manages category values and labels associated with user-specified raster map layers.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_category(map,cats=None,values=None,separator="tab",raster=None,rules=None,format=None,label_format=None,coefficients=None,color_format="none",verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`map : str | np.ndarray, required`**
   - Name of raster map
   - Used as: input, raster, name

2. **`cats : str | list[str], optional`**
   - Category values
   - Example: 1,3,7-9,13
   - Used as: input, cats, range

3. **`values : float | list[float] | str, optional`**
   - Comma separated value list
   - Example: 1.4,3.8,13

4. **`separator : str, optional`**
   - Field separator
   - Special characters: pipe, comma, space, tab, newline
   - Used as: input, separator, character

5. **`raster : str | np.ndarray, optional`**
   - Raster map from which to copy category table
   - Used as: input, raster, name

6. **`rules : str | io.StringIO, optional`**
   - File containing category label rules (or "-" to read from stdin)
   - Used as: input, file, name

7. **`format : str, optional`**
   - Output format ('plain', 'json')
   - When the value is not 'plain' or 'json', the value is used as a default label or format string for dynamic labeling. This usage is deprecated and will be removed in a future release. Use parameter 'label_format' instead.

8. **`label_format : str, optional`**
   - Default label or format string for dynamic labeling
   - Used when no explicit label exists for the category

9. **`coefficients : tuple[float, float, float, float] | list[float] | str, optional`**
   - Dynamic label coefficients
   - Two pairs of category multiplier and offsets, for $1 and $2
   - Used as: mult1,offset1,mult2,offset2

10. **`color_format : str, optional`**
   - Color format
   - Color format for output values or none.
   - Used as: name
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/r.category.html#__tabbed_2_3) for all details)*

11. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

12. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

13. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 13 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/r.category.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

r.category prints the category values and labels for the raster map
layer specified by map = name to standard output. You can also use
it to set category labels for a raster map.

The user can specify all needed parameters on the command line, and run
the program non-interactively. If the user does not specify any
categories (e.g., using the optional cats = range [, range ,...]
argument), then all the category values and labels for the named raster
map layer that occur in the map are printed. The entire map is read
using r.describe , to determine which categories occur
in the map . If a listing of categories is specified, then the labels
for those categories only are printed. The cats may be specified as
single category values, or as ranges of values. The user may also
(optionally) specify that a field separator other than a space or tab be
used to separate the category value from its corresponding category
label in the output, by using the separator = character | space | tab option (see example below). If
no field separator is specified by the user, a tab is used to separate
these fields in the output, by default.

The output is sent to standard output in the form of one category per
line, with the category value first on the line, then an ASCII TAB
character (or whatever single character or space is specified using the separator parameter), then the label for the category.

---

## See Also

Related tools:

---

## Authors

Michael Shapiro, U.S. Army Construction Engineering Research
Laboratory Hamish Bowman, University of Otago, New Zealand (label creation options)

---

## Resources

- [Official r.category manual](https://grass.osgeo.org/grass-devel/manuals/r.category.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.category.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
