# t.rast3d.extract

**Category**: temporal

## Description

Extracts a subset of a space time 3D raster dataset.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.t_rast3d_extract(input,where=None,expression=None,output,basename=None,suffix="gran",nprocs=1,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str, required`**
   - Name of the input space time raster3d dataset
   - Used as: input, str3ds, name

2. **`where : str, optional`**
   - WHERE conditions of SQL statement without 'where' keyword used in the temporal GIS framework
   - Example: start_time > '2001-01-01 12:30:00'
   - Used as: sql_query

3. **`expression : str, optional`**
   - The r3.mapcalc expression assigned to all extracted 3D raster maps

4. **`output : str, required`**
   - Name of the output space time raster3d dataset
   - Used as: output, str3ds, name

5. **`basename : str, optional`**
   - Basename of the new generated 3D raster maps

6. **`suffix : str, optional`**
   - Suffix to add at basename: set 'gran' for granularity, 'time' for the full time format, 'num' for numerical suffix with a specific number of digits (default %05)
   - Default: gran

7. **`nprocs : int, optional`**
   - Number of r3.mapcalc processes to run in parallel
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


*Showing 10 of 12 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/t.rast3d.extract.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

t.rast3d.extract is used to extract a subset of a space time 3D raster
dataset and to store that subset in a different space time 3D raster
dataset. It has exactly the same functionality as t.rast.extract . The only difference is the that
this module works on STR3DS and 3D raster maps.

Please refer to t.rast.extract for documentation
and examples.

---

## See Also

Related tools:
- [`t.rast.extract`](https://grass.osgeo.org/grass-devel/manuals/t.rast.extract.html)
- [`t.create`](https://grass.osgeo.org/grass-devel/manuals/t.create.html)
- [`t.info`](https://grass.osgeo.org/grass-devel/manuals/t.info.html)

---

## Resources

- [Official t.rast3d.extract manual](https://grass.osgeo.org/grass-devel/manuals/t.rast3d.extract.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/t.rast3d.extract.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
