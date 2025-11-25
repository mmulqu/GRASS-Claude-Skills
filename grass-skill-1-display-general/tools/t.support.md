# t.support

**Category**: temporal

## Description

Modifies the metadata of a space time dataset.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.t_support(input,semantictype="mean",type="strds",title=None,description=None,aggr_type=None,flags=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str, required`**
   - Name of the input space time dataset
   - Used as: input, stds, name

2. **`semantictype : str, optional`**
   - Semantic type of the space time dataset
   - Allowed values: min, max, sum, mean
   - Default: mean

3. **`type : str, optional`**
   - Type of the input space time dataset
   - Used as: name
   - Allowed values: strds, stvds, str3ds

4. **`Default: strds`**

5. **`title : str, optional`**
   - Title of the space time dataset

6. **`description : str, optional`**
   - Description of the space time dataset

7. **`aggr_type : str, optional`**
   - Aggregation type of the space time raster or 3D raster dataset

8. **`flags : str, optional`**
   - Allowed values: m, u
   - m
   - Update the metadata information and spatial extent of registered maps from the GRASS spatial database
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/t.support.html#__tabbed_2_3) for all details)*

9. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

10. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

11. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 11 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/t.support.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

The t.support module is dedicated to modify and update the metadata of
a space time dataset.

The title, description and the semantic type can be modified.

The flag -u allows updating the STDS metadata from registered map
layers. This is useful in case the map layers have been modified without
using temporal commands.

The flag -m will update the metadata from registered maps, but also
checks if the registered map layers have been removed from the spatial
database. It deletes missing map layers from the space time dataset
register table and the temporal database.

---

## See Also

Related tools:
- [`t.create`](https://grass.osgeo.org/grass-devel/manuals/t.create.html)
- [`t.info`](https://grass.osgeo.org/grass-devel/manuals/t.info.html)

---

## Resources

- [Official t.support manual](https://grass.osgeo.org/grass-devel/manuals/t.support.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/t.support.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
