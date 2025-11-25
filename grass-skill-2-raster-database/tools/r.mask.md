# r.mask

**Category**: raster

## Description

Creates a raster mask for limiting raster operation.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_mask(raster=None,maskcats="*",vector=None,layer="1",cats=None,where=None,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`raster : str | np.ndarray, optional`**
   - Name of raster map to use as mask
   - Used as: input, raster, name

2. **`maskcats : str, optional`**
   - Raster values to use for mask
   - Format: 1 2 3 thru 7 *
   - Default: *

3. **`vector : str, optional`**
   - Name of vector map to use as mask
   - Or data source for direct OGR access
   - Used as: input, vector, name

4. **`layer : str, optional`**
   - Layer number or name (vector)
   - Vector features can have category values in different layers. This number determines which layer to use. When used with direct OGR access this is the layer name.
   - Used as: input, layer

5. **`cats : str, optional`**
   - Category values (vector)
   - Example: 1,3,7-9,13
   - Used as: input, cats, range

6. **`where : str, optional`**
   - WHERE conditions of SQL statement without 'where' keyword (vector)
   - Example: income < 1000 and population >= 10000
   - Used as: input, sql_query, sql_query

7. **`flags : str, optional`**
   - Allowed values: i, r
   - i
   - Create inverse mask
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/r.mask.html#__tabbed_2_3) for all details)*

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


*Showing 10 of 11 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/r.mask.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

r.mask facilitates the creation and management of a raster mask to
control raster operations. While the computational region specifies the
extent (rectangular bounding box) and resolution, the mask specifies the
area that should be considered for the operations and area which should
be ignored. The mask is represented as a raster map called MASK by
default.

The mask is applied when reading an existing GRASS raster map, for
example when used as an input map in a module. The mask will block out
certain areas of a raster map from analysis and/or display, by "hiding"
them from sight of other GRASS modules. Data falling within the
boundaries of the mask can be modified and operated upon by other GRASS
raster modules; data falling outside the mask is treated as if it were
NULL.

By default, r.mask converts any non-NULL value in the input map,
including zero, to 1. All these areas will be part of the mask (see the
notes for more details). To only convert specific values (or range of
values) to 1 and the rest to NULL, use the maskcats parameter.

Because the mask raster map created with r.mask is actually only a
reclass map named MASK by default, it can be copied, renamed, removed,
and used in analyses, just like other GRASS raster maps.

The user should be aware that a mask remains in place until it is
removed or renamed. To remove a mask and restore raster operations to
normal (i.e., all cells of the current region), remove the mask by
setting the -r flag ( r.mask -r ). Alternatively, a mask can be
removed using g.remove or by renaming it to any other name with g.rename .

The GRASS_MASK environment variable can be used to specify the raster
map which will be used as a mask. If the environment variable is not
defined, the name MASK is used instead.

---

## See Also

Related tools:
- [`g.region`](https://grass.osgeo.org/grass-devel/manuals/g.region.html)
- [`r.mapcalc`](https://grass.osgeo.org/grass-devel/manuals/r.mapcalc.html)
- [`r.reclass`](https://grass.osgeo.org/grass-devel/manuals/r.reclass.html)
- [`g.remove`](https://grass.osgeo.org/grass-devel/manuals/g.remove.html)
- [`g.rename`](https://grass.osgeo.org/grass-devel/manuals/g.rename.html)
- [`r.quant`](https://grass.osgeo.org/grass-devel/manuals/r.quant.html)

---

## Resources

- [Official r.mask manual](https://grass.osgeo.org/grass-devel/manuals/r.mask.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.mask.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
