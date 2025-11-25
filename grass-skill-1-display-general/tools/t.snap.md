# t.snap

**Category**: temporal

## Description

Snaps temporally the maps of a space time dataset.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.t_snap(input,type="strds",verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str, required`**
   - Name of an existing space time dataset
   - Used as: input, stds, name

2. **`type : str, optional`**
   - Type of the input space time dataset
   - Used as: name
   - Allowed values: strds, stvds, str3ds

3. **`Default: strds`**

4. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

5. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

6. **`superquiet : bool, optional`**
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

t.snap is designed to convert time instances of maps into time
intervals or to create valid temporal topologies for space time
datasets. Raster, 3D raster and vector space time datasets are supported
with absolute and relative time.

This module "snaps" the end time of each registered map of a space time
dataset to the start time of the map that is the temporal nearest
neighbour in the future. Maps with equal time stamps are not modified
and must be removed or modified to create a valid temporal topology. In
case the last map in the space time dataset is a time instance, the
granularity of the space time dataset will be used to create the time
interval.

---

## See Also

Related tools:
- [`t.shift`](https://grass.osgeo.org/grass-devel/manuals/t.shift.html)
- [`t.create`](https://grass.osgeo.org/grass-devel/manuals/t.create.html)
- [`t.register`](https://grass.osgeo.org/grass-devel/manuals/t.register.html)

---

## Resources

- [Official t.snap manual](https://grass.osgeo.org/grass-devel/manuals/t.snap.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/t.snap.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
