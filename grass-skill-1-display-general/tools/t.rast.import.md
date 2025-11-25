# t.rast.import

**Category**: temporal

## Description

Imports space time raster dataset.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.t_rast_import(input,output,basename=None,directory="/tmp",title=None,description=None,project=None,memory=300,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str | io.StringIO, required`**
   - Name of input file
   - Used as: input, file, name

2. **`output : str, required`**
   - Name of the output space time raster dataset
   - Used as: output, strds, name

3. **`basename : str, optional`**
   - Basename of the new generated output maps
   - A numerical suffix separated by an underscore will be attached to create a unique identifier

4. **`directory : str, required`**
   - Path to the extraction directory
   - Used as: input, dir, name
   - Default: /tmp

5. **`title : str, optional`**
   - Title of the new space time dataset

6. **`description : str, optional`**
   - Description of the new space time dataset

7. **`project : str, optional`**
   - Create a new project and import the data into it. Do not run this module in parallel or interrupt it when a new project should be created

8. **`memory : int, optional`**
   - Maximum memory to be used (in MB)
   - Cache size for raster rows
   - Used as: memory in MB

9. **`flags : str, optional`**
   - Allowed values: r, l, e, o, c
   - r
   - Set the current region from the last map that was imported
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/t.rast.import.html#__tabbed_2_3) for all details)*

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


*Showing 10 of 13 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/t.rast.import.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

t.rast.import imports a space time raster dataset archive that was
exported with t.rast.export .

---

## See Also

Related tools:
- [`t.rast.export`](https://grass.osgeo.org/grass-devel/manuals/t.rast.export.html)
- [`t.create`](https://grass.osgeo.org/grass-devel/manuals/t.create.html)
- [`t.info`](https://grass.osgeo.org/grass-devel/manuals/t.info.html)
- [`r.in.gdal`](https://grass.osgeo.org/grass-devel/manuals/r.in.gdal.html)
- [`r.unpack`](https://grass.osgeo.org/grass-devel/manuals/r.unpack.html)
- [`t.vect.import`](https://grass.osgeo.org/grass-devel/manuals/t.vect.import.html)

---

## Resources

- [Official t.rast.import manual](https://grass.osgeo.org/grass-devel/manuals/t.rast.import.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/t.rast.import.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
