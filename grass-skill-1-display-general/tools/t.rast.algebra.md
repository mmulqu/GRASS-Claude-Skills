# t.rast.algebra

**Category**: temporal

## Description

Apply temporal and spatial operations on space time raster datasets using temporal raster algebra.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.t_rast_algebra(expression,basename,suffix="num",nprocs=1,flags=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`expression : str, required`**
   - r.mapcalc expression for temporal and spatial analysis of space time raster datasets

2. **`basename : str, required`**
   - Basename of the new generated output maps
   - A numerical suffix separated by an underscore will be attached to create a unique identifier

3. **`suffix : str, optional`**
   - Suffix to add at basename: set 'gran' for granularity, 'time' for the full time format, 'num' for numerical suffix with a specific number of digits (default %05)
   - Default: num

4. **`nprocs : int, optional`**
   - Number of r.mapcalc processes to run in parallel
   - Default: 1

5. **`flags : str, optional`**
   - Allowed values: s, n, g, d
   - s
   - Check the spatial topology of temporally related maps and process only spatially related maps
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/t.rast.algebra.html#__tabbed_2_3) for all details)*

6. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

7. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

8. **`superquiet : bool, optional`**
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

t.rast.algebra performs temporal and spatial map algebra operations on
space time raster datasets (STRDS) using the temporal raster algebra.

The module expects an expression as input parameter in the following
form:

The statement structure is similar to that of r.mapcalc .
In this statement, result represents the name of the space time
raster dataset (STRDS) that will contain the result of the calculation
that is given as expression on the right side of the equality sign.
These expressions can be any valid or nested combination of temporal
operations and spatial overlay or buffer functions that are provided by
the temporal algebra.

The temporal raster algebra works only with space time raster datasets
(STRDS). The algebra provides methods for map selection based on their
temporal relations. It is also possible to temporally shift maps, to
create temporal buffer and to snap time instances to create a valid
temporal topology. Furthermore, expressions can be nested and evaluated
in conditional statements (if, else statements). Within if-statements,
the algebra provides temporal variables like start time, end time, day
of year, time differences or number of maps per time interval to build
up conditions. In addition the algebra provides a subset of the spatial operations from r.mapcalc . All these operations can be assigned to STRDS
or to the map lists resulting of operations between STRDS.

By default, only temporal topological relations among space time
datasets (STDS) are evaluated. The -s flag can be used to
additionally activate the evaluation of the spatial topology based on
the spatial extent of maps.

The expression option must be passed as quoted expression, for
example:

Where C is the new space time raster dataset that will contain maps
with the basename "result" and a numerical suffix separated by an
underscore that represent the sum of maps from the STRDS A and
temporally equal maps (i.e., maps with equal temporal topology relation)
from the STRDS B .

The map basename for the result STRDS must always be specified.

---

## See Also

Related tools:
- [`r.mapcalc`](https://grass.osgeo.org/grass-devel/manuals/r.mapcalc.html)
- [`t.vect.algebra`](https://grass.osgeo.org/grass-devel/manuals/t.vect.algebra.html)
- [`t.rast3d.algebra`](https://grass.osgeo.org/grass-devel/manuals/t.rast3d.algebra.html)
- [`t.select`](https://grass.osgeo.org/grass-devel/manuals/t.select.html)
- [`t.rast3d.mapcalc`](https://grass.osgeo.org/grass-devel/manuals/t.rast3d.mapcalc.html)
- [`t.rast.mapcalc`](https://grass.osgeo.org/grass-devel/manuals/t.rast.mapcalc.html)

---

## Authors

Thomas Leppelt, Sören Gebbert, Thünen Institute of Climate-Smart
Agriculture

---

## Resources

- [Official t.rast.algebra manual](https://grass.osgeo.org/grass-devel/manuals/t.rast.algebra.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/t.rast.algebra.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
