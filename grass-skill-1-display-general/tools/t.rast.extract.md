# t.rast.extract

**Category**: temporal

## Description

Extracts a subset of a space time raster datasets.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.t_rast_extract(input,where=None,expression=None,output,basename=None,suffix="gran",nprocs=1,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str, required`**
   - Name of the input space time raster dataset
   - Used as: input, strds, name

2. **`where : str, optional`**
   - WHERE conditions of SQL statement without 'where' keyword used in the temporal GIS framework
   - Example: start_time > '2001-01-01 12:30:00'
   - Used as: sql_query

3. **`expression : str, optional`**
   - r.mapcalc expression assigned to all extracted raster maps

4. **`output : str, required`**
   - Name of the output space time raster dataset
   - Used as: output, strds, name

5. **`basename : str, optional`**
   - Basename of the new generated output maps
   - A numerical suffix separated by an underscore will be attached to create a unique identifier

6. **`suffix : str, optional`**
   - Suffix to add at basename: set 'gran' for granularity, 'time' for the full time format, 'num' for numerical suffix with a specific number of digits (default %05)
   - Default: gran

7. **`nprocs : int, optional`**
   - Number of r.mapcalc processes to run in parallel
   - Default: 1

8. **`flags : str, optional`**
   - Allowed values: n
   - n
   - Register Null maps

9. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

10. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

11. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

12. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 12 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/t.rast.extract.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

The purpose of t.rast.extract is to extract a subset of a space time
raster dataset and to store that subset in a different space time raster
dataset. The where condition is used to select the subset. In
addition a r.mapcalc sub-expression can be specified that performs
operations on all maps of the selected subset. In this expression the
name of the input space time raster dataset can be used as simple map
name. Other STRDS than the input STRDS can not be specified, but any
raster map. In case a r.mapcalc sub-expression is defined, the base
name of the resulting raster maps must be specified. The r.mapcalc expression can be used to select maps as well, since by default
resulting empty maps are not registered in the output space time raster
dataset and removed after processing. The number of parallel GRASS
processes can be specified to speed up the processing.

If no r.mapcalc expression is defined, the selected maps are simply
registered in the new created output space time raster dataset to avoid
data duplication.

---

## See Also

Related tools:
- [`t.create`](https://grass.osgeo.org/grass-devel/manuals/t.create.html)
- [`t.info`](https://grass.osgeo.org/grass-devel/manuals/t.info.html)

---

## Resources

- [Official t.rast.extract manual](https://grass.osgeo.org/grass-devel/manuals/t.rast.extract.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/t.rast.extract.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
