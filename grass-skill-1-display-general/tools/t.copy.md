# t.copy

**Category**: temporal

## Description

Creates a copy of a space time raster dataset.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.t_copy(input,type="strds",output,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str, required`**
   - Name of the input space time dataset
   - Used as: input, stds, name

2. **`type : str, optional`**
   - Type of the input space time dataset
   - Used as: name
   - Allowed values: strds,  str3ds,  stvds

3. **`Default: strds`**

4. **`output : str, required`**
   - Name of the output space time dataset
   - Used as: output, stds, name

5. **`flags : str, optional`**
   - Allowed values: c
   - c
   - Also copy maps of the space-time dataset

6. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

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

The purpose of t.copy is to create a copy of a space time dataset.
The new space time dataset will be located in the current mapset,
whereas the old space time dataset can be located in a different mapset
as long as this mapset is in the search path.

If the -c flag is given, the maps of the old space time dataset will
also be copied to the current mapset, otherwise the original maps will
be simply registered in the temporal database. The new copies will have
the same name as the old maps.

---

## See Also

Related tools:
- [`t.rast.extract`](https://grass.osgeo.org/grass-devel/manuals/t.rast.extract.html)
- [`t.rast3d.extract`](https://grass.osgeo.org/grass-devel/manuals/t.rast3d.extract.html)
- [`t.vect.extract`](https://grass.osgeo.org/grass-devel/manuals/t.vect.extract.html)
- [`t.info`](https://grass.osgeo.org/grass-devel/manuals/t.info.html)

---

## Resources

- [Official t.copy manual](https://grass.osgeo.org/grass-devel/manuals/t.copy.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/t.copy.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
