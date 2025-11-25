# r.profile

**Category**: raster

## Description

Outputs the raster map layer values lying on user-defined line(s).

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_profile(input,output="-",coordinates=None,file=None,resolution=None,null_value="*",units=None,format="plain",color_format=None,separator="comma",flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str | np.ndarray, required`**
   - Name of input raster map
   - Used as: input, raster, name

2. **`output : str, optional`**
   - Name of file for output (use output=- for stdout)
   - Used as: output, file, name
   - Default: -

3. **`coordinates : list[tuple[float, float]] | tuple[float, float] | list[float] | str, optional`**
   - Profile coordinate pairs
   - Used as: input, coords, east,north

4. **`file : str | io.StringIO, optional`**
   - Name of input file containing coordinate pairs
   - Use instead of the 'coordinates' option. "-" reads from stdin.
   - Used as: input, file, name

5. **`resolution : float, optional`**
   - Resolution along profile (default = current region resolution)

6. **`null_value : str, optional`**
   - String representing NULL value
   - Used as: string
   - Default: *

7. **`units : str, optional`**
   - Units
   - If units are not specified, current project units are used. Meters are used by default in geographic (latlon) projects.
   - Allowed values: meters, kilometers, feet, miles

8. **`format : str, required`**
   - Output format
   - Used as: name
   - Allowed values: plain, csv, json
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/r.profile.html#__tabbed_2_3) for all details)*

9. **`color_format : str, optional`**
   - Color format
   - Color format for output values.
   - Used as: name
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/r.profile.html#__tabbed_2_3) for all details)*

10. **`separator : str, optional`**
   - Field separator
   - Special characters: pipe, comma, space, tab, newline
   - Used as: input, separator, character

11. **`flags : str, optional`**
   - Allowed values: g, c
   - g
   - Output easting and northing in first two columns of four column output
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/r.profile.html#__tabbed_2_3) for all details)*

12. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

13. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

14. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

15. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 15 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/r.profile.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

This program outputs two or four column (with -g ) data to stdout or
an ASCII file. The default two column output consists of cumulative
profile length and raster value. The optional four column output
consists of easting, northing, cumulative profile length, and raster
value. Profile end or "turning" points can be set manually with the coordinates argument. The profile resolution, or distance between
profile points, is obtained from the current region resolution, or can
be manually set with the resolution argument.

The coordinates parameter can be set to comma separated geographic
coordinates for profile line endpoints. Alternatively the coordinate
pairs can be piped from the text file specified by file option, or
if set to "-", from stdin . In these cases the coordinate pairs should
be given one comma separated pair per line.

The resolution parameter sets the distance between each profile
point (resolution). The resolution must be provided in GRASS database
units (i.e. decimal degrees for Lat Long databases and meters for UTM).
By default r.profile uses the resolution of the current GRASS region.

The null parameter can optionally be set to change the character
string representing null values.

The optional color output (with -c ) provides the associated GRASS colour
value for each profile point. The format of the color output is controlled by
the color_format option, which can be set to hex, triplet, rgb, or hsv
color formats. The default color format is triplet for plain output, and hex
for JSON output.

---

## See Also

Related tools:
- [`v.in.ascii`](https://grass.osgeo.org/grass-devel/manuals/v.in.ascii.html)
- [`r.what`](https://grass.osgeo.org/grass-devel/manuals/r.what.html)
- [`r.transect`](https://grass.osgeo.org/grass-devel/manuals/r.transect.html)

---

## Resources

- [Official r.profile manual](https://grass.osgeo.org/grass-devel/manuals/r.profile.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.profile.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
