# g.gui.timeline

**Category**: general

## Description

Allows comparing temporal datasets by displaying their temporal extents in a plot.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.g_gui_timeline(inputs=None,flags=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`inputs : str | list[str], optional`**
   - Name of the input space time datasets
   - Used as: input, stds, name

2. **`flags : str, optional`**
   - Allowed values: 3
   - 3
   - Show also 3D plot of spatio-temporal extents

3. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

4. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

5. **`superquiet : bool, optional`**
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

The Timeline Tool is a wxGUI component which allows
the user to compare the extents of temporal datasets (strds, stvds,
str3ds) in a plot.

Supported features:



---

## See Also

Related tools:

---

## Resources

- [Official g.gui.timeline manual](https://grass.osgeo.org/grass-devel/manuals/g.gui.timeline.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/g.gui.timeline.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
