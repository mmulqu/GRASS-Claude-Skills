# t.create

**Category**: temporal

## Description

Creates a space time dataset.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.t_create(output,type="strds",temporaltype="absolute",semantictype="mean",title,description,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`output : str, required`**
   - Name of the output space time dataset
   - Used as: output, stds, name

2. **`type : str, optional`**
   - Type of the output space time dataset
   - Used as: name
   - Allowed values: strds, stvds, str3ds

3. **`Default: strds`**

4. **`temporaltype : str, optional`**
   - The temporal type of the space time dataset
   - Used as: name
   - Allowed values: absolute, relative

5. **`semantictype : str, required`**
   - Semantic type of the space time dataset
   - Allowed values: min, max, sum, mean
   - Default: mean

6. **`title : str, required`**
   - Title of the new space time dataset

7. **`description : str, required`**
   - Description of the new space time dataset

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


*Showing 10 of 11 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/t.create.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

t.create is used to create space time datasets of type raster (STRDS),
3D raster (STR3DS) and vector (STVDS).

Space time datasets represent spatio-temporal fields in the temporal
GRASS framework. They are designed to collect any amount of time stamped
maps with time intervals and time instances. The temporal type of a
space time dataset can be absolute (means with a fixed date) or relative
(only sequential maps) and must be set during dataset creation along
with the name and the description.

Time stamped maps can registered in and unregistered from space time
datasets. The spatio-temporal extent as well as the metadata of a space
time dataset is derived from its registered maps. Hence the metadata is
dependent from the dataset type (raster, 3D raster, vector).

---

## See Also

Related tools:
- [`t.register`](https://grass.osgeo.org/grass-devel/manuals/t.register.html)
- [`t.remove`](https://grass.osgeo.org/grass-devel/manuals/t.remove.html)
- [`t.info`](https://grass.osgeo.org/grass-devel/manuals/t.info.html)

---

## Resources

- [Official t.create manual](https://grass.osgeo.org/grass-devel/manuals/t.create.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/t.create.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
