# r.mapcalc

**Category**: raster

## Description

Raster map calculator.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_mapcalc(expression=None,region="current",file=None,seed=None,nprocs=0,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`expression : str, optional`**
   - Expression to evaluate

2. **`region : str, optional`**
   - The computational region that should be used.
   - Allowed values: current, intersect, union
   - current: current uses the current region of the mapset

3. **`intersect: intersect computes the intersection region between all input maps and uses the smallest resolution`**
   - union: union computes the union extent of all map regions and uses the smallest resolution
   - Default: current

4. **`file : str | io.StringIO, optional`**
   - File containing expression(s) to evaluate
   - Used as: input, file, name

5. **`seed : int, optional`**
   - Seed value for the random number generator
   - Using the same seed ensures identical results, while a randomly generated seed produces different outcomes in each run.

6. **`nprocs : int, optional`**
   - Number of threads for parallel computing
   - 0: use OpenMP default; >0: use nprocs; <0: use MAX-nprocs
   - Default: 0

7. **`flags : str, optional`**
   - Allowed values: s, l
   - s
   - Generate random seed (result is non-deterministic)
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/r.mapcalc.html#__tabbed_2_3) for all details)*

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


*Showing 10 of 11 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/r.mapcalc.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

r.mapcalc performs arithmetic on raster map layers. New raster map
layers can be created which are arithmetic expressions involving
existing raster map layers, integer or floating point constants, and
functions.

r.mapcalc expression have the form:

result = expression

where result is the name of a raster map layer to contain the result
of the calculation and expression is any legal arithmetic expression
involving existing raster map layers (except result itself), integer
or floating point constants, and functions known to the calculator.
Parentheses are allowed in the expression and may be nested to any
depth. result will be created in the user's current mapset.

As expression= is the first option, it is the default. This means
that passing an expression on the command line is possible as long as
the expression is quoted and a space is included before the first = sign. Example ('foo' is the resulting map):

or:

An unquoted expression (i.e. split over multiple arguments) won't work,
nor will omitting the space before the = sign:

To read command from the file, use file= explicitly, e.g.:

or:

or:

The formula entered to r.mapcalc by the user is recorded both in the result map title (which appears in the category file for result ) and
in the history file for result .

Some characters have special meaning to the command shell. If the user
is entering input to r.mapcalc on the command line, expressions should
be enclosed within single quotes. See NOTES, below.

By default r.mapcalc uses the current region as computational region
that was set with g.region for processing. Sometimes it
is necessary to use a region that is derived from the raster maps in the
expression to set the computational region. This is of high importance
for modules that use r.mapcalc internally to process time series of
satellite images that all have different spatial extents. A module that
requires this feature is t.rast.algebra . The region option of r.mapcalc was implemented to address this
requirement. It allows computing and using a region based on all raster
maps in an expression. Three modes are supported:

The following operators are supported:

(modulus is the remainder upon division)

[1] The &&& and ||| operators handle null values differently to
other operators. See the section entitled NULL support below for
more details.

The operators are applied from left to right, with those of higher
precedence applied before those with lower precedence. Division by 0 and
modulus by 0 are acceptable and give a NULL result. The logical
operators give a 1 result if the comparison is true, 0 otherwise.

Anything in the expression which is not a number, operator, or function
name is taken to be a raster map layer name. Examples:

Most GRASS raster map layers meet this naming convention. However, if a
raster map layer has a name which conflicts with the above rule, it
should be quoted. For example, the expression

would be interpreted as: x equals a minus b, whereas

would be interpreted as: x equals the raster map layer named a-b

Also

would create x filled with the number 3107, while

would copy the raster map layer 3107 to the raster map layer x .

Quotes are not required unless the raster map layer names look like
numbers or contain operators, OR unless the program is run
non-interactively. Examples given here assume the program is run
interactively. See NOTES, below.

r.mapcalc will look for the raster map layers according to the user's
current mapset search path. It is possible to override the search path
and specify the mapset from which to select the raster map layer. This
is done by specifying the raster map layer name in the form:

For example, the following is a legal expression:

The mapset specified does not have to be in the mapset search path.
(This method of overriding the mapset search path is common to all GRASS
commands, not just r.mapcalc .)

Maps and images are data base files stored in raster format, i.e.,
two-dimensional matrices of integer values. In r.mapcalc , maps may be
followed by a neighborhood modifier that specifies a relative offset
from the current cell being evaluated. The format is map[r,c] , where r is the row offset and c is the column offset. For example, map[1,2] refers to the cell one row below and two columns to the
right of the current cell, map[-2,-1] refers to the cell two rows
above and one column to the left of the current cell, and map[0,1] refers to the cell one column to the right of the current cell. This
syntax permits the development of neighborhood-type filters within a
single map or across multiple maps.

The neighborhood modifier cannot be used on maps generated within same r.mapcalc command run (see "KNOWN ISSUES" section).

Sometimes it is desirable to use a value associated with a category's label instead of the category value itself. If a raster map layer name
is preceded by the @ operator, then the labels in the category file
for the raster map layer are used in the expression instead of the
category value.

For example, suppose that the raster map layer soil.ph (representing
soil pH values) has a category file with labels as follows:

Then the expression:

would produce a result with category values 0, 1.4, 2.4, 3.5, 5.8, 7.2,
8.8 and 9.4.

Note that this operator may only be applied to raster map layers and
produces a floating point value in the expression. Therefore, the
category label must start with a valid number. If the category label is
integer, it will be represented by a floating point number. I the
category label does not start with a number or is missing, it will be
represented by NULL (no data) in the resulting raster map.

It is often helpful to manipulate the colors assigned to map categories.
This is particularly useful when the spectral properties of cells have
meaning (as with imagery data), or when the map category values
represent real quantities (as when category values reflect true
elevation values). Map color manipulation can also aid visual
recognition, and map printing.

The # operator can be used to either convert map category values to
their grey scale equivalents or to extract the red, green, or blue
components of a raster map layer into separate raster map layers.

converts each category value in map to a value in the range 0-255
which represents the grey scale level implied by the color for the
category. If the map has a grey scale color table, then the grey level
is what #map evaluates to. Otherwise, it is computed as:

Alternatively, you can use:

to use the NTSC weightings:

Or, you can use:

to use equal weightings:

The # operator has three other forms: r#map, g#map, b#map. These
extract the red, green, or blue components in the named raster map,
respectively. The GRASS shell script r.blend extracts
each of these components from two raster map layers, and combines them
by a user-specified percentage. These forms allow color separates to be
made. For example, to extract the red component from map and store it
in the new 0-255 map layer red , the user could type:

To assign this map grey colors type:

To assign this map red colors type:

The functions currently supported are listed in the table below. The
type of the result is indicated in the last column. F means that the
functions always results in a floating point value, I means that the
function gives an integer result, and * indicates that the result is
float if any of the arguments to the function are floating point values
and integer if all arguments are integer.

Type legend: F : always floating point result I : always integer result * : float if any argument is float, integer if all arguments are integer

Note, that the row() and col() indexing starts with 1.

There are three data types that can be used within the mapcalc
expression. They are defined with certain precision and within certain
value range. The following table reports precision and value range info
on AMD64 (x86-64) architectures compiled with GCC/CLANG. Note that
although this setting is the most frequent one, the ranges could differ
for different architectures.

Note that the value counter wraps around when the value overflows its
range. E.g., if your expression is a = int(2147483648) , you will get
NULL value. For expression a = int(2147483649) , you will reach the
lowest value possible instead, i.e. -2147483647.

Floating point numbers are allowed in the expression. A floating point
number is a number which contains a decimal point:

Floating point values in the expression are handled in a special way.
With arithmetic and logical operators, if either operand is float, the
other is converted to float and the result of the operation is float.
This means, in particular that division of integers results in a
(truncated) integer, while division of floats results in an accurate
floating point value. With functions of type * (see table above), the
result is float if any argument is float, integer otherwise.

Note: If you calculate with integer numbers, the resulting map will be
integer. If you want to get a float result, add the decimal point to
integer number(s).

If you want floating point division, at least one of the arguments has
to be a floating point value. Multiplying one of them by 1.0 will
produce a floating-point result, as will using float():

NULL support: Please note that any math performed with NULL cells always
results in a NULL value for these cells. If you want to replace a NULL
cell on-the-fly, use the isnull() test function in a if-statement.

Example: The users wants the NULL-valued cells to be treated like zeros.
To add maps A and B (where B contains NULLs) to get a map C the user can
use a construction like:

NULL and conditions:

For the one argument form:

For the two argument form:

For the three argument form:

For the four argument form:

More generally, all operators and most functions return NULL if *any*
of their arguments are NULL. The functions if(), isnull() and eval() are exceptions. The function isnull() returns 1 if its argument is NULL and 0 otherwise.
If the user wants the opposite, the ! operator, e.g. "!isnull(x)" must
be used.

All forms of if() return NULL if the first argument is NULL. The 2, 3
and 4 argument forms of if() return NULL if the "selected" argument is
NULL, e.g.:

eval() always returns its last argument, so it only returns NULL if the
last argument is NULL.

Note : The user cannot test for NULL using the == operator, as that
returns NULL if either or both arguments are NULL, i.e. if x and y are
both NULL, then "x == y" and "x != y" are both NULL rather than 1 and 0
respectively. The behaviour makes sense if the user considers NULL as representing an
unknown quantity. E.g. if x and y are both unknown, then the values of
"x == y" and "x != y" are also unknown; if they both have unknown
values, the user doesn't know whether or not they both have the same
value.

---

## See Also

Related tools:
- [`g.region`](https://grass.osgeo.org/grass-devel/manuals/g.region.html)
- [`r.bitpattern`](https://grass.osgeo.org/grass-devel/manuals/r.bitpattern.html)
- [`r.blend`](https://grass.osgeo.org/grass-devel/manuals/r.blend.html)
- [`r.colors`](https://grass.osgeo.org/grass-devel/manuals/r.colors.html)
- [`r.fillnulls`](https://grass.osgeo.org/grass-devel/manuals/r.fillnulls.html)
- [`r.mapcalc.simple`](https://grass.osgeo.org/grass-devel/manuals/r.mapcalc.simple.html)

---

## Authors

Michael Shapiro, U.S.Army Construction Engineering Research Laboratory
Glynn Clements

---

## Resources

- [Official r.mapcalc manual](https://grass.osgeo.org/grass-devel/manuals/r.mapcalc.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.mapcalc.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
