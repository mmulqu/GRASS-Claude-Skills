# r.colors

**Category**: raster

## Description

Creates/modifies the color table associated with a raster map.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_colors(map=None,file=None,color=None,raster=None,raster_3d=None,rules=None,offset=0,scale=1,flags=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`map : str | list[str], optional`**
   - Name of raster map(s)
   - Used as: input, raster, name

2. **`file : str | io.StringIO, optional`**
   - Input file with one map name per line
   - Input map names can be defined in an input file in case a large amount of maps must be specified. This option is mutual exclusive to the map option.
   - Used as: input, file, name

3. **`color : str, optional`**
   - Name of color table
   - Used as: input, colortable, style
   - Allowed values: aspect, aspectcolr, bcyr, bgyr, blues, byg, byr, celsius, corine, curvature, differences, elevation, etopo2, evi, fahrenheit, forest_cover, gdd, grass, greens, grey, grey.eq, grey.log, grey1.0, grey255, gyr, haxby, inferno, kelvin, magma, ndvi, ndwi, nlcd, oranges, plasma, population, population_dens, precipitation, precipitation_daily, precipitation_monthly, rainbow, ramp, random, reds, roygbiv, rstcurv, ryb, ryg, sepia, slope, soilmoisture, srtm, srtm_percent, srtm_plus, terrain, viridis, water, wave
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/r.colors.html#__tabbed_2_3) for all details)*

4. **`raster : str | np.ndarray, optional`**
   - Raster map from which to copy color table
   - Used as: input, raster, name

5. **`raster_3d : str, optional`**
   - 3D raster map from which to copy color table
   - Used as: input, raster_3d, name

6. **`rules : str | io.StringIO, optional`**
   - Path to rules file
   - "-" to read rules from stdin
   - Used as: input, file, name

7. **`offset : float, optional`**
   - Offset for color rule values
   - New value = (old value + offset) * scale
   - Default: 0

8. **`scale : float, optional`**
   - Scale for color rule values
   - New value = (old value + offset) * scale
   - Default: 1

9. **`flags : str, optional`**
   - Allowed values: r, w, l, d, n, g, a, e
   - r
   - Remove existing color table
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/r.colors.html#__tabbed_2_3) for all details)*

10. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

11. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

12. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 12 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/r.colors.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

r.colors allows the user to create and/or modify the color table for a
raster map or several raster maps at once. The raster maps (specified on
the command line by map or as file using an input file with one
map name per line) must exist in the user's current mapset search path.

The raster option allows user to specify a raster map name from
which to copy the color map.

The raster_3d option allows user to specify a 3D raster map name from which to copy the color map.

The -e flag equalizes the original raster's color table. It can
preclude the need for grey.eq rule, when used as -e color = grey .
Note however, that this will not yield a color table identical to color=grey.eq , because grey.eq scales the fraction by 256 to get a
grey level, while -e uses it to interpolate the original color
table. If the original color table is a 0-255 grey scale, -e is
effectively scaling the fraction by 255. Different algorithms are used. -e is designed to work with any color table, both the floating point
and the integer raster maps.

The -g flag divides the raster's grey value range into 100
logarithmically equal steps (where "step" is a rule with the same grey
level for the start and end points). It can preclude the need for grey.log rule, when used as -g color = grey . Note however, that
this will not yield a color table identical to color=grey.log .
Different algorithms are used. Unlike color = grey.log , -g is
designed to work with both floating point and integer rasters, without
performance issues with large datasets, of any original color table.
Logarithmic scaling doesn't work on negative values. In the case when
the value range includes zero, there's no realistic solution.

The -e and -g flags are not mutually exclusive.

offset and scale modify color rules to match the values of a
raster map using the formula new_value = (old_value + offset) x scale .
For example, if the units of a raster map are Kelvin x 50, the color
rules celsius can be applied with offset=273.15 and scale=50 .

If the user specifies the -w flag, the current color table file for
the input map will not be overwritten. This means that the color table
is created only if the map does not already have a color table. If
this option is not specified, the color table will be created if one
does not exist, or modified if it does.

Color table types aspect, grey, grey.eq (histogram-equalized grey
scale), byg (blue-yellow-green), byr (blue-yellow-red), gyr (green-yellow-red), rainbow, ramp, ryg (red-yellow-green), random ,
and wave are pre-defined color tables that r.colors knows how to
create without any further input.

In case several input raster maps are provided the range (min, max) of
all maps will be used for color table creation. Hence the created color
table will span from the smallest minimum to the largest maximum value
of all input raster maps and will be applied to all input raster maps.

In general, tables which associate colors with percentages (aspect,
bcyr, byg, byr, elevation, grey, gyr, rainbow, ramp, ryb, ryg and wave)
can be applied to any data, while those which use absolute values
(aspectcolr, curvature, etopo2, evi, ndvi, population, slope, srtm, and
terrain) only make sense for data with certain ranges. One can get a
rough idea of the applicability of a colour table by reading the
corresponding rules file ( $GISBASE/etc/colors/<name> ). For example the slope rule is defined as:

This is designed for the slope map generated by r.slope.aspect , where the value is a slope angle
between 0 and 90 degrees.

Similarly, the aspectcolr rule:

is designed for the aspect maps produced by r.slope.aspect , where the value is a heading
between 0 and 360 degrees.

The rules color table type will cause r.colors to read color table
specifications from standard input (stdin) and will build the color
table accordingly.

Using color table type rules , there are two ways to build a color
table: by category values and by "percent" values.

To build a color table by category values' indices, the user should
determine the range of category values in the raster map with which the
color table will be used. Specific category values will then be
associated with specific colors. Note that a color does not have to be
assigned for every valid category value because r.colors will
interpolate a color ramp to fill in where color specification rules have
been left out. The format of such a specification is as follows:

Each category value must be valid for the raster map, category values
must be in ascending order and only use standard GRASS color names
(aqua, black, blue, brown, cyan, gray, green, grey, indigo, magenta,
orange, purple, red, violet, white, yellow).

Colors can also be specified by color numbers each in the range 0-255.
The format of a category value color table specification using color
numbers instead of color names is as follows:

Specifying a color table by "percent" values allows one to treat a color
table as if it were numbered from 0 to 100. The format of a "percent"
value color table specification is the same as for a category value
color specification, except that the category values are replaced by
"percent" values, each from 0-100, in ascending order. The format is as
follows:

Using "percent" value color table specification rules, colors can also
be specified by color numbers each in the range 0-255. The format of a
percent value color table specification using color numbers instead of
color names is as follows:

Note that you can also mix these two methods of color table
specification; for example:

To set the NULL (no data) color, use the "nv" (null values) parameter:

To set the color to used for undefined values (beyond the range of the
color rules) use the "default" parameter:

---

## See Also

Related tools:
- [`d.colortable`](https://grass.osgeo.org/grass-devel/manuals/d.colortable.html)
- [`d.histogram`](https://grass.osgeo.org/grass-devel/manuals/d.histogram.html)
- [`d.legend`](https://grass.osgeo.org/grass-devel/manuals/d.legend.html)
- [`r.colors.out`](https://grass.osgeo.org/grass-devel/manuals/r.colors.out.html)
- [`r.colors.stddev`](https://grass.osgeo.org/grass-devel/manuals/r.colors.stddev.html)
- [`r.support`](https://grass.osgeo.org/grass-devel/manuals/r.support.html)
- [`r.univar`](https://grass.osgeo.org/grass-devel/manuals/r.univar.html)
- [`v.colors`](https://grass.osgeo.org/grass-devel/manuals/v.colors.html)
- [`v.colors.out`](https://grass.osgeo.org/grass-devel/manuals/v.colors.out.html)
- [`r3.colors`](https://grass.osgeo.org/grass-devel/manuals/r3.colors.html)
- [`r3.colors.out`](https://grass.osgeo.org/grass-devel/manuals/r3.colors.out.html)

---

## Authors

Michael Shapiro and David Johnson Support for 3D rasters by Soeren Gebbert

---

## Resources

- [Official r.colors manual](https://grass.osgeo.org/grass-devel/manuals/r.colors.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.colors.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
