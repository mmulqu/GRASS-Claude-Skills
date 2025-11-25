# t.rast.contour

**Category**: temporal

## Description

Produces a space time vector dataset of specified contours from a space time raster dataset.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.t_rast_contour(input,output,where=None,basename,suffix="gran",step=None,levels=None,minlevel=None,maxlevel=None,cut=0,nprocs=1,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str, required`**
   - Name of the input space time raster dataset
   - Used as: input, strds, name

2. **`output : str, required`**
   - Name of the output space time vector dataset
   - Used as: output, stvds, name

3. **`where : str, optional`**
   - WHERE conditions of SQL statement without 'where' keyword used in the temporal GIS framework
   - Example: start_time > '2001-01-01 12:30:00'
   - Used as: sql_query

4. **`basename : str, required`**
   - Basename of the new generated output maps
   - A numerical suffix separated by an underscore will be attached to create a unique identifier

5. **`suffix : str, optional`**
   - Suffix to add at basename: set 'gran' for granularity, 'time' for the full time format, 'num' for numerical suffix with a specific number of digits (default %05)
   - Default: gran

6. **`step : float, optional`**
   - Increment between contour levels

7. **`levels : float | list[float] | str, optional`**
   - List of contour levels

8. **`minlevel : float, optional`**
   - Minimum contour level

9. **`maxlevel : float, optional`**
   - Maximum contour level

10. **`cut : int, optional`**
   - Minimum number of points for a contour line (0 -> no limit)
   - Default: 0

11. **`nprocs : int, optional`**
   - Number of r.contour processes to run in parallel, more than 1 process works only in conjunction with flag -t
   - Default: 1

12. **`flags : str, optional`**
   - Allowed values: n, t
   - n
   - Register empty vector maps
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/t.rast.contour.html#__tabbed_2_3) for all details)*

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


*Showing 10 of 16 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/t.rast.contour.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

t.rast.contour is designed to produce a space time vector dataset of
specified contours from a space time raster dataset. This module works
as a front-end to r.contour and therefore supports all
parameter of this module. Hence, all raster map layers in a space time
raster dataset are successively passed to r.contour that
computes the contour lines. Please refer to the r.contour documentation for a detailed description. The
new generated vector contour map layers will be registered in the output
space time vector dataset, using the same time stamps as their raster
map layer origins.

This module supports the parallel processing of r.contour module instances. The number of parallel
processes can be set with the nprocs option. However, this will only
work in conjunction with the -t flag, that avoids the creation of
attribute tables. The parallel creation of attribute tables is not
supported.

The where option allows selecting subsets of the input space time
raster dataset.

The flag -n can be used to force the registration of empty vector map
layers. Empty vector maps may occur in case that empty raster map layers
should be converted into vector map layers, or in case the chosen steps
or contour levels are not present in the raster map layers.

---

## See Also

Related tools:
- [`r.contour`](https://grass.osgeo.org/grass-devel/manuals/r.contour.html)
- [`t.rast.db.select`](https://grass.osgeo.org/grass-devel/manuals/t.rast.db.select.html)
- [`t.info`](https://grass.osgeo.org/grass-devel/manuals/t.info.html)

---

## Resources

- [Official t.rast.contour manual](https://grass.osgeo.org/grass-devel/manuals/t.rast.contour.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/t.rast.contour.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
