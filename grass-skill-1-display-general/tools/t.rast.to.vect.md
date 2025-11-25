# t.rast.to.vect

**Category**: temporal

## Description

Converts a space time raster dataset into a space time vector dataset

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.t_rast_to_vect(input,output,where=None,type,basename,suffix="gran",column="value",nprocs=1,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
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

4. **`type : str, required`**
   - Output feature type
   - Allowed values: point, line, area

5. **`basename : str, required`**
   - Basename of the new generated output maps
   - A numerical suffix separated by an underscore will be attached to create a unique identifier

6. **`suffix : str, optional`**
   - Suffix to add at basename: set 'gran' for granularity, 'time' for the full time format, 'num' for numerical suffix with a specific number of digits (default %05)
   - Default: gran

7. **`column : str, optional`**
   - Name of attribute column to store value
   - Default: value

8. **`nprocs : int, optional`**
   - Number of r.to.vect processes to run in parallel, more than 1 process works only in conjunction with flag -t
   - Default: 1

9. **`flags : str, optional`**
   - Allowed values: n, t, s, z, b, v
   - n
   - Register empty vector maps
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/t.rast.to.vect.html#__tabbed_2_3) for all details)*

10. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

11. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

12. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

13. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 13 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/t.rast.to.vect.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

t.rast.to.vect is designed to convert a space time raster dataset into
a space time vector dataset. This module works as a front-end to r.to.vect and therefore supports all parameter of this
module. Hence, all raster map layers in a space time raster dataset are
passed to r.to.vect that converts them into vector map
layers (using point,line or area as conversion criteria). Please refer
to the r.to.vect documentation for a detailed
description of the raster to vector conversion options. The new
generated vector map layers will be registered in the output space time
vector dataset, using the same time stamps as their raster map layer
origins.

This module supports the parallel processing of r.to.vect module instances. The number of parallel
processes can be set with the nprocs option. However, this will only
work in conjunction with the -t flag, that avoids the creation of
attribute tables. The parallel creation of attribute tables is not
supported.

The where option allows selecting subsets of the input space time
raster dataset.

The flag -n can be used to force the registration of empty vector map
layers. Empty vector maps may occur in case that empty raster map layers
should be converted into vector map layers.

---

## See Also

Related tools:
- [`r.to.vect`](https://grass.osgeo.org/grass-devel/manuals/r.to.vect.html)
- [`t.rast.db.select`](https://grass.osgeo.org/grass-devel/manuals/t.rast.db.select.html)
- [`t.info`](https://grass.osgeo.org/grass-devel/manuals/t.info.html)

---

## Resources

- [Official t.rast.to.vect manual](https://grass.osgeo.org/grass-devel/manuals/t.rast.to.vect.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/t.rast.to.vect.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
