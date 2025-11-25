# t.vect.import

**Category**: temporal

## Description

Imports a space time vector dataset from a GRASS specific archive file.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.t_vect_import(input,output,basename=None,directory,title=None,description=None,project=None,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str | io.StringIO, required`**
   - Name of input file
   - Used as: input, file, name

2. **`output : str, required`**
   - Name of the output space time vector dataset
   - Used as: output, stvds, name

3. **`basename : str, optional`**
   - Basename of the new generated output maps
   - A numerical suffix separated by an underscore will be attached to create a unique identifier

4. **`directory : str, required`**
   - Path to the extraction directory
   - Used as: input, dir, name

5. **`title : str, optional`**
   - Title of the new space time dataset

6. **`description : str, optional`**
   - Description of the new space time dataset

7. **`project : str, optional`**
   - Create a new project (location) and import the data into it. Do not run this module in parallel or interrupt it when a new project should be created

8. **`flags : str, optional`**
   - Allowed values: e, o, c
   - e
   - Extend project extents based on new dataset
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/t.vect.import.html#__tabbed_2_3) for all details)*

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


*Showing 10 of 12 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/t.vect.import.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

t.vect.import imports a space time vector dataset archive that was
exported with t.vect.export .

---

## See Also

Related tools:
- [`t.vect.export`](https://grass.osgeo.org/grass-devel/manuals/t.vect.export.html)
- [`t.create`](https://grass.osgeo.org/grass-devel/manuals/t.create.html)
- [`t.info`](https://grass.osgeo.org/grass-devel/manuals/t.info.html)
- [`v.in.ogr`](https://grass.osgeo.org/grass-devel/manuals/v.in.ogr.html)
- [`v.pack`](https://grass.osgeo.org/grass-devel/manuals/v.pack.html)
- [`t.rast.import`](https://grass.osgeo.org/grass-devel/manuals/t.rast.import.html)

---

## Resources

- [Official t.vect.import manual](https://grass.osgeo.org/grass-devel/manuals/t.vect.import.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/t.vect.import.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
