# t.rast.gapfill

**Category**: temporal

## Description

Replaces gaps in a space time raster dataset with interpolated raster maps.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.t_rast_gapfill(input,where=None,basename,suffix="gran",nprocs=1,flags=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str, required`**
   - Name of the input space time raster dataset
   - Used as: input, strds, name

2. **`where : str, optional`**
   - WHERE conditions of SQL statement without 'where' keyword used in the temporal GIS framework
   - Example: start_time > '2001-01-01 12:30:00'
   - Used as: sql_query

3. **`basename : str, required`**
   - Basename of the new generated output maps
   - A numerical suffix separated by an underscore will be attached to create a unique identifier

4. **`suffix : str, optional`**
   - Suffix to add at basename: set 'gran' for granularity, 'time' for the full time format, 'num' for numerical suffix with a specific number of digits (default %05)
   - Default: gran

5. **`nprocs : int, optional`**
   - Number of interpolation processes to run in parallel
   - Default: 1

6. **`flags : str, optional`**
   - Allowed values: t
   - t
   - Assign the space time raster dataset start and end time to the output map

7. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

8. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

9. **`superquiet : bool, optional`**
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

t.rast.gapfill fills temporal gaps in space time raster datasets using
linear interpolation. Temporal all gaps will be detected in the input
space time raster dataset automatically. The predecessor and successor
maps of the gaps will be identified and used to linear interpolate the
raster map between them.

---

## See Also

Related tools:
- [`r.series.interp`](https://grass.osgeo.org/grass-devel/manuals/r.series.interp.html)
- [`t.create`](https://grass.osgeo.org/grass-devel/manuals/t.create.html)
- [`t.info`](https://grass.osgeo.org/grass-devel/manuals/t.info.html)

---

## Resources

- [Official t.rast.gapfill manual](https://grass.osgeo.org/grass-devel/manuals/t.rast.gapfill.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/t.rast.gapfill.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
