# t.select

**Category**: temporal

## Description

Select maps from space time datasets by topological relationships to other space time datasets using temporal algebra.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.t_select(type="strds",expression,flags=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`type : str, optional`**
   - Type of the input space time dataset
   - Used as: name
   - Allowed values: strds, stvds, str3ds

2. **`Default: strds`**

3. **`expression : str, required`**
   - The temporal mapcalc expression
   - Used as: expression

4. **`flags : str, optional`**
   - Allowed values: s, d
   - s
   - Check the spatial topology of temporally related maps and select only spatially related maps
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/t.select.html#__tabbed_2_3) for all details)*

5. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

6. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

7. **`superquiet : bool, optional`**
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

t.select performs selection of maps that are registered in space time
datasets using temporal algebra.

The module expects an expression as input parameter in the following
form:

"result = expression"

The statement structure is similar to r.mapcalc, see r.mapcalc . Where result represents the name of a
space time dataset (STDS)that will contain the result of the calculation
that is given as expression on the right side of the equality sign.
These expression can be any valid or nested combination of temporal
operations and functions that are provided by the temporal algebra. The temporal algebra works with space time datasets of any type (STRDS,
STR3DS and STVDS). The algebra provides methods for map selection from
STDS based on their temporal relations. It is also possible to
temporally shift maps, to create temporal buffer and to snap time
instances to create a valid temporal topology. Furthermore expressions
can be nested and evaluated in conditional statements (if, else
statements). Within if-statements the algebra provides temporal
variables like start time, end time, day of year, time differences or
number of maps per time interval to build up conditions. These
operations can be assigned to space time datasets or to the results of
operations between space time datasets.

The type of the input space time datasets must be defined with the input
parameter type . Possible options are STRDS, STVDS or STR3DS. The
default is set to space time raster datasets (STRDS).

As default, topological relationships between space time datasets will
be evaluated only temporal. Use the s flag to activate the
additionally spatial topology evaluation.

The expression option must be passed as quoted expression, for
example:

Where C is the new space time raster dataset that will contain maps
from A that are selected by equal temporal relationships to the
existing dataset B in this case.

---

## See Also

Related tools:
- [`r.mapcalc`](https://grass.osgeo.org/grass-devel/manuals/r.mapcalc.html)

---

## Authors

Thomas Leppelt, Sören Gebbert, Thünen Institute of Climate-Smart
Agriculture

---

## Resources

- [Official t.select manual](https://grass.osgeo.org/grass-devel/manuals/t.select.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/t.select.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
