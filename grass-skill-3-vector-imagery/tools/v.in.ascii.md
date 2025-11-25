# v.in.ascii

**Category**: vector

## Description

Creates a vector map from an ASCII points file or ASCII vector file.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.v_in_ascii(input,output,format="point",separator="pipe",text=None,skip=0,columns=None,x=1,y=2,z=0,cat=0,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str | io.StringIO, required`**
   - Name of input file to be imported
   - '-' for standard input
   - Used as: input, file, name

2. **`output : str, required`**
   - Name for output vector map
   - Used as: output, vector, name

3. **`format : str, optional`**
   - Input file format
   - Allowed values: point, standard
   - point: simple x,y[,z] list
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/v.in.ascii.html#__tabbed_2_3) for all details)*

4. **`separator : str, optional`**
   - Field separator
   - Special characters: pipe, comma, space, tab, newline
   - Used as: input, separator, character

5. **`text : str, optional`**
   - Text delimiter
   - Special characters: doublequote, singlequote, none
   - Used as: input, separator, character

6. **`skip : int, optional`**
   - Number of header lines to skip at top of input file (points mode)
   - Default: 0

7. **`columns : str, optional`**
   - Column definition in SQL style (points mode)
   - For example: 'x double precision, y double precision, cat int, name varchar(10)'

8. **`x : int, optional`**
   - Number of column used as x coordinate (points mode)
   - First column is 1
   - Default: 1

9. **`y : int, optional`**
   - Number of column used as y coordinate (points mode)
   - First column is 1
   - Default: 2

10. **`z : int, optional`**
   - Number of column used as z coordinate (points mode)
   - First column is 1. If 0, z coordinate is not used
   - Default: 0

11. **`cat : int, optional`**
   - Number of column used as category (points mode)
   - First column is 1. If 0, unique category is assigned to each row and written to new column 'cat'
   - Default: 0

12. **`flags : str, optional`**
   - Allowed values: z, e, n, t, b, r, i
   - z
   - Create 3D vector map
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/v.in.ascii.html#__tabbed_2_3) for all details)*

13. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

14. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

15. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

16. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 16 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/v.in.ascii.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

v.in.ascii converts a vector map in GRASS ASCII vector
format to a vector map in binary format. The module may
import two formats:

v.out.ascii performs the function of v.in.ascii in
reverse; i.e., it converts vector maps in binary format to GRASS ASCII
vector format. These two companion programs are useful both for
importing and exporting vector maps between GRASS and other software,
and for transferring data between machines.

---

## See Also

Related tools:
- [`db.execute`](https://grass.osgeo.org/grass-devel/manuals/db.execute.html)
- [`r.in.ascii`](https://grass.osgeo.org/grass-devel/manuals/r.in.ascii.html)
- [`r.in.poly`](https://grass.osgeo.org/grass-devel/manuals/r.in.poly.html)
- [`r.in.xyz`](https://grass.osgeo.org/grass-devel/manuals/r.in.xyz.html)
- [`v.build`](https://grass.osgeo.org/grass-devel/manuals/v.build.html)
- [`v.build.polylines`](https://grass.osgeo.org/grass-devel/manuals/v.build.polylines.html)
- [`v.centroids`](https://grass.osgeo.org/grass-devel/manuals/v.centroids.html)
- [`v.clean`](https://grass.osgeo.org/grass-devel/manuals/v.clean.html)
- [`v.db.connect`](https://grass.osgeo.org/grass-devel/manuals/v.db.connect.html)
- [`v.import`](https://grass.osgeo.org/grass-devel/manuals/v.import.html)
- [`v.info`](https://grass.osgeo.org/grass-devel/manuals/v.info.html)
- [`v.in.lines`](https://grass.osgeo.org/grass-devel/manuals/v.in.lines.html)
- [`v.in.mapgen`](https://grass.osgeo.org/grass-devel/manuals/v.in.mapgen.html)
- [`v.out.ascii`](https://grass.osgeo.org/grass-devel/manuals/v.out.ascii.html)

---

## Authors

Michael Higgins, U.S.Army Construction Engineering Research Laboratory James Westervelt, U.S.Army Construction Engineering Research
Laboratory Radim Blazek, ITC-Irst, Trento, Italy

---

## Resources

- [Official v.in.ascii manual](https://grass.osgeo.org/grass-devel/manuals/v.in.ascii.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/v.in.ascii.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
