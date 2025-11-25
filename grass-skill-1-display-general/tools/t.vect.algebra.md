# t.vect.algebra

**Category**: temporal

## Description

Apply temporal and spatial operations on space time vector datasets using temporal vector algebra.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.t_vect_algebra(expression,basename,flags=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`expression : str, required`**
   - Spatio-temporal mapcalc expression
   - Used as: expression

2. **`basename : str, required`**
   - Basename of the new generated output maps
   - A numerical suffix separated by an underscore will be attached to create a unique identifier
   - Used as: basename

3. **`flags : str, optional`**
   - Allowed values: s
   - s
   - Check the spatial topology of temporally related maps and process only spatially related maps

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

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

t.vect.algebra performs temporal and spatial overlay and buffer
functions on space time vector datasets (STVDS) by using the temporal
vector algebra. New STVDS can be created, which are expressions of
existing STVDS.

The module expects an expression as input parameter in the following
form:

The statement structure is similar to r.mapcalc, see r.mapcalc . Where result represents the name of a
space time dataset (STVDS) that will contain the result of the
calculation that is given as expression on the right side of the
equality sign. These expression can be any valid or nested combination
of temporal operations and functions that are provided by the temporal
vector algebra. The algebra provides methods for map selection from STDS based on their
temporal relations. It is also possible to temporally shift maps, to
create temporal buffer and to snap time instances to create a valid
temporal topology. Furthermore expressions can be nested and evaluated
in conditional statements (if, else statements). Within if-statements
the algebra provides temporal variables like start time, end time, day
of year, time differences or number of maps per time interval to build
up conditions. These operations can be assigned to space time datasets
or to the results of operations between space time datasets.

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
- [`t.select`](https://grass.osgeo.org/grass-devel/manuals/t.select.html)

---

## Authors

Thomas Leppelt, Soeren Gebbert, Thünen Institute of Climate-Smart
Agriculture

---

## Resources

- [Official t.vect.algebra manual](https://grass.osgeo.org/grass-devel/manuals/t.vect.algebra.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/t.vect.algebra.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
