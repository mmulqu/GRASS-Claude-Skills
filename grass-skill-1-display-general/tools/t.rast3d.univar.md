# t.rast3d.univar

**Category**: temporal

## Description

Calculates univariate statistics from the non-null cells for each registered 3D raster map of a space time 3D raster dataset.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.t_rast3d_univar(input,zones=None,nprocs=0,output=None,where=None,separator="pipe",flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str, required`**
   - Name of the input space time raster3d dataset
   - Used as: input, str3ds, name

2. **`zones : str | np.ndarray, optional`**
   - Raster map with zones to compute statistics for
   - Raster map with zones to compute statistics for (needs to be CELL)
   - Used as: input, raster, name

3. **`nprocs : int, optional`**
   - Number of threads for parallel computing
   - 0: use OpenMP default; >0: use nprocs; <0: use MAX-nprocs
   - Default: 0

4. **`output : str, optional`**
   - Name for output file
   - Used as: output, file, name

5. **`where : str, optional`**
   - WHERE conditions of SQL statement without 'where' keyword used in the temporal GIS framework
   - Example: start_time > '2001-01-01 12:30:00'
   - Used as: sql_query

6. **`separator : str, optional`**
   - Field separator character between the output columns
   - Special characters: pipe, comma, space, tab, newline
   - Used as: input, separator, character

7. **`flags : str, optional`**
   - Allowed values: e, s
   - e
   - Calculate extended statistics
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/t.rast3d.univar.html#__tabbed_2_3) for all details)*

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


*Showing 10 of 11 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/t.rast3d.univar.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

t.rast3d.univar provides the same functionality as t.rast.univar , the only difference is the 3D raster
map layer metadata. Please refer to the manual page of t.rast.univar for documentation and examples.

---

## See Also

Related tools:
- [`t.rast.univar`](https://grass.osgeo.org/grass-devel/manuals/t.rast.univar.html)
- [`t.create`](https://grass.osgeo.org/grass-devel/manuals/t.create.html)
- [`t.info`](https://grass.osgeo.org/grass-devel/manuals/t.info.html)

---

## Resources

- [Official t.rast3d.univar manual](https://grass.osgeo.org/grass-devel/manuals/t.rast3d.univar.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/t.rast3d.univar.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
