# v.random

**Category**: vector

## Description

Generates random 2D/3D vector points.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.v_random(output,npoints,restrict=None,layer="-1",cats=None,where=None,zmin=0.0,zmax=0.0,seed=None,column=None,column_type="double precision",flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`output : str, required`**
   - Name for output vector map
   - Used as: output, vector, name

2. **`npoints : int, required`**
   - Number of points to be created

3. **`restrict : str, optional`**
   - Name of input vector map
   - Restrict points to areas in input vector
   - Used as: input, vector, name

4. **`layer : str, optional`**
   - Layer number or name ('-1' for all layers)
   - A single vector map can be connected to multiple database tables. This number determines which table to use. When used with direct OGR access this is the layer name.
   - Used as: input, layer

5. **`cats : str, optional`**
   - Category values
   - Example: 1,3,7-9,13
   - Used as: input, cats, range

6. **`where : str, optional`**
   - WHERE conditions of SQL statement without 'where' keyword
   - Example: income < 1000 and population >= 10000
   - Used as: input, sql_query, sql_query

7. **`zmin : float, optional`**
   - Minimum z height (needs -z flag or column name)
   - Default: 0.0

8. **`zmax : float, optional`**
   - Maximum z height (needs -z flag or column name)
   - Default: 0.0

9. **`seed : int, optional`**
   - Seed value for the random number generator
   - Using the same seed ensures identical results, while a randomly generated seed produces different outcomes in each run.

10. **`column : str, optional`**
   - Name of column for z values
   - Writes z values to column
   - Used as: input, dbcolumn, name

11. **`column_type : str, optional`**
   - Type of column for z values
   - Allowed values: integer, double precision
   - Default: double precision

12. **`flags : str, optional`**
   - Allowed values: z, a, b
   - z
   - Create 3D output
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/v.random.html#__tabbed_2_3) for all details)*

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


*Showing 10 of 16 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/v.random.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

v.random randomly generates vector points within the current region
using the selected random number generator.

v.random can generate also 3D vector points or write random value to
the attribute table. Point height range or attribute value range is
controlled by specifying zmin and zmax options. Both z values
are included in range ( zmin \<= z \<= zmax ). Generated random
attribute value type can be controlled by column_type . Use integer column type for integers and double precision for floating point
numbers. Integer values are calculated by rounding random floating point
number.

To produce repeatable results a random seed can be set using the option seed .

If an restrict vector map with areas is specified, the location of
random points is restricted to the selected areas. By default, the
requested number of points are distributed across all areas.

If the -a flag is given, the requested number of points is generated
for each individual area. For example, if 20 points should be generated
and the input map has 100 individual areas, 2000 points will be
generated in total.

Attributes attached to restrict vector map are also transferred if
the layer parameter is defined > 0, see example below.

---

## See Also

Related tools:
- [`g.region`](https://grass.osgeo.org/grass-devel/manuals/g.region.html)
- [`r.random`](https://grass.osgeo.org/grass-devel/manuals/r.random.html)
- [`v.db.addtable`](https://grass.osgeo.org/grass-devel/manuals/v.db.addtable.html)
- [`v.perturb`](https://grass.osgeo.org/grass-devel/manuals/v.perturb.html)
- [`v.sample`](https://grass.osgeo.org/grass-devel/manuals/v.sample.html)
- [`v.univar`](https://grass.osgeo.org/grass-devel/manuals/v.univar.html)
- [`v.what.rast`](https://grass.osgeo.org/grass-devel/manuals/v.what.rast.html)
- [`v.what.vect`](https://grass.osgeo.org/grass-devel/manuals/v.what.vect.html)

---

## Resources

- [Official v.random manual](https://grass.osgeo.org/grass-devel/manuals/v.random.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/v.random.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
