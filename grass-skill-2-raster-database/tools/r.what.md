# r.what

**Category**: raster

## Description

Queries raster maps on their category values and category labels.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_what(map,coordinates=None,points=None,null_value="*",output=None,separator="pipe",format="plain",cache=500,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`map : str | list[str], required`**
   - Name of existing raster map(s) to query
   - Used as: input, raster, name

2. **`coordinates : tuple[float, float] | list[float] | str, optional`**
   - Coordinates for query
   - Used as: input, coords, east,north

3. **`points : str, optional`**
   - Name of vector points map for query
   - Or data source for direct OGR access
   - Used as: input, vector, name

4. **`null_value : str, optional`**
   - String representing NULL value
   - Used as: string
   - Default: *

5. **`output : str, optional`**
   - Name for output file (if omitted or "-" output to stdout)
   - Used as: output, file, name

6. **`separator : str, optional`**
   - Field separator
   - Special characters: pipe, comma, space, tab, newline
   - Used as: input, separator, character

7. **`format : str, required`**
   - Output format
   - Used as: name
   - Allowed values: plain, json
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/r.what.html#__tabbed_2_3) for all details)*

8. **`cache : int, optional`**
   - Size of point cache
   - Default: 500

9. **`flags : str, optional`**
   - Allowed values: n, f, r, i, c, v
   - n
   - Output header row
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/r.what.html#__tabbed_2_3) for all details)*

10. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

11. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

12. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

13. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 13 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/r.what.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

r.what outputs the category values and (optionally) the category
labels associated with user-specified locations on raster input map(s).
Locations are specified as geographic x,y coordinate pairs (i.e., pair
of eastings and northings); the user can also (optionally) associate a
label with each location.

The input coordinates can be entered directly on the command line via coordinates parameter, or redirected via stdin from an input text
file, script, or piped from another program (like v.out.ascii ). Coordinates can be given also as a
vector points map ( points ).

If none of the above input methods are used and the module is run from
the terminal prompt, the program will interactively query the user for
point locations and labels.

Each line of the input consists of an easting, a northing, and an
optional label, which are separated by spaces. In interactive mode, the
word " end " must be typed after the last pair of input coordinates.

r.what output consists of the input geographic location and label,
and, for each user-named raster map layer, the category value, and (if
the -f label flag is specified) the category label associated with
the cell(s) at this geographic location.

---

## Note

The maximum number of raster map layers that can be queried at one time
is 400.

---

## See Also

Related tools:
- [`r.category`](https://grass.osgeo.org/grass-devel/manuals/r.category.html)
- [`r.report`](https://grass.osgeo.org/grass-devel/manuals/r.report.html)
- [`r.stats`](https://grass.osgeo.org/grass-devel/manuals/r.stats.html)
- [`r.series`](https://grass.osgeo.org/grass-devel/manuals/r.series.html)
- [`r.univar`](https://grass.osgeo.org/grass-devel/manuals/r.univar.html)
- [`v.what`](https://grass.osgeo.org/grass-devel/manuals/v.what.html)
- [`v.what.rast`](https://grass.osgeo.org/grass-devel/manuals/v.what.rast.html)
- [`v.what.vect`](https://grass.osgeo.org/grass-devel/manuals/v.what.vect.html)

---

## Authors

Michael Shapiro, U.S. Army Construction Engineering Research
Laboratory Vector point input added by Martin Landa, Czech Technical University in
Prague, Czech Republic

---

## Resources

- [Official r.what manual](https://grass.osgeo.org/grass-devel/manuals/r.what.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.what.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
