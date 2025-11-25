# t.info

**Category**: temporal

## Description

Lists information about space time datasets and maps.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.t_info(input,type="strds",flags=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str, required`**
   - Name of an existing space time dataset or map
   - Used as: input, stds, name

2. **`type : str, optional`**
   - Type of the input space time dataset
   - Used as: name
   - Allowed values: strds,  str3ds,  stvds,  raster,  raster_3d,  vector

3. **`Default: strds`**

4. **`flags : str, optional`**
   - Allowed values: g, h, d
   - g
   - Print in shell script style
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/t.info.html#__tabbed_2_3) for all details)*

5. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

6. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

7. **`superquiet : bool, optional`**
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

t.info reports information about any dataset that is registered in the
temporal database in human readable or shell script style. Datasets are
raster, 3D raster and vector maps as well as their corresponding space
time datasets (STRDS, STR3DS and STVDS). This module reports the
information that are stored in the temporal database. These are basic
information (id, name, mapset, creator, creation time, temporal type),
the temporal and spatial extent and dataset type specific metadata. The
user has to utilize r.info , r3.info , v.info to report detailed
information about raster, 3D raster and vector maps, since not all map
specific information and metadata are stored in the temporal database.

In addition, information about the chosen temporal database backend can
be reported.

---

## See Also

Related tools:
- [`t.create`](https://grass.osgeo.org/grass-devel/manuals/t.create.html)
- [`t.list`](https://grass.osgeo.org/grass-devel/manuals/t.list.html)
- [`t.register`](https://grass.osgeo.org/grass-devel/manuals/t.register.html)
- [`r.info`](https://grass.osgeo.org/grass-devel/manuals/r.info.html)
- [`r3.info`](https://grass.osgeo.org/grass-devel/manuals/r3.info.html)
- [`v.info`](https://grass.osgeo.org/grass-devel/manuals/v.info.html)

---

## Resources

- [Official t.info manual](https://grass.osgeo.org/grass-devel/manuals/t.info.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/t.info.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
