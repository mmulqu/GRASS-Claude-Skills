# t.rast.out.vtk

**Category**: temporal

## Description

Exports space time raster dataset as VTK time series.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.t_rast_out_vtk(input,directory,elevation=None,where=None,null=-99999.99,flags=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str, required`**
   - Name of the input space time raster dataset
   - Used as: input, strds, name

2. **`directory : str, required`**
   - Path to the export directory

3. **`elevation : str | np.ndarray, optional`**
   - Name of input elevation raster map
   - Used as: input, raster, name

4. **`where : str, optional`**
   - WHERE conditions of SQL statement without 'where' keyword used in the temporal GIS framework
   - Example: start_time > '2001-01-01 12:30:00'
   - Used as: sql_query

5. **`null : float, optional`**
   - Value to represent no data cell
   - Default: -99999.99

6. **`flags : str, optional`**
   - Allowed values: p, c, g
   - p
   - Create VTK point data instead of VTK cell data (if no elevation map is given)
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/t.rast.out.vtk.html#__tabbed_2_3) for all details)*

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

t.rast.out.vtk exports all maps registered in a space time raster
datasets as VTK legacy files using a numerical numbering scheme. The VTK
files can be visualized with any VTK based visualize. Our preferred tool
is ParaView. The VTK legacy files are created using r.out.vtk .

---

## See Also

Related tools:
- [`r.out.vtk`](https://grass.osgeo.org/grass-devel/manuals/r.out.vtk.html)

---

## Resources

- [Official t.rast.out.vtk manual](https://grass.osgeo.org/grass-devel/manuals/t.rast.out.vtk.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/t.rast.out.vtk.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
