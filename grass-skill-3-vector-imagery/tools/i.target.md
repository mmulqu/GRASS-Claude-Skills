# i.target

**Category**: imagery

## Description

Targets an imagery group to a GRASS location and mapset.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.i_target(group,location=None,mapset=None,flags=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`group : str, required`**
   - Name of input imagery group
   - Used as: group, name

2. **`location : str, optional`**
   - Name of imagery target location

3. **`mapset : str, optional`**
   - Name of target mapset

4. **`flags : str, optional`**
   - Allowed values: c
   - c
   - Set current location and mapset as target for imagery group

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

i.target targets an imagery group to a GRASS data base
project name and mapset. A project name and mapset are required for the i.rectify imagery module, into which to write the
rectified map just prior to completion of the program; i.target enables the user to specify this project. i.target must be run before g.gui.gcp and i.rectify .

---

## See Also

Related tools:

---

## Authors

Michael Shapiro, U.S. Army Construction Engineering Research Laboratory
Parser support: Bob Covill

---

## Resources

- [Official i.target manual](https://grass.osgeo.org/grass-devel/manuals/i.target.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/i.target.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
