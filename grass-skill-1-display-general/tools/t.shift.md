# t.shift

**Category**: temporal

## Description

Shifts temporally the maps of a space time dataset.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.t_shift(input,type="strds",granularity,verbose=None,quiet=None,superquiet=None)
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

4. **`granularity : str, required`**
   - Shift granularity
   - Format absolute time: "x years, x months, x weeks, x days, x hours, x minutes, x seconds", relative time is of type integer

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

t.shift is designed to temporally shift all registered maps in a space
time dataset with a user defined granularity. Raster, 3D raster and
vector space time datasets are supported.

The format of the absolute time granularity is "number unit". Number is
an integer, unit is the temporal unit that can be one of year(s),
month(s), week(s), day(s), hour(s), minute(s) or second(s).

The granularity in case of relative time is an integer. The temporal
unit is the unit of the space time dataset and can not be modified.

---

## See Also

Related tools:
- [`t.create`](https://grass.osgeo.org/grass-devel/manuals/t.create.html)
- [`t.register`](https://grass.osgeo.org/grass-devel/manuals/t.register.html)
- [`t.snap`](https://grass.osgeo.org/grass-devel/manuals/t.snap.html)

---

## Resources

- [Official t.shift manual](https://grass.osgeo.org/grass-devel/manuals/t.shift.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/t.shift.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
