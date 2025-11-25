# g.gisenv

**Category**: general

## Description

Outputs and modifies the user's current GRASS variable settings. Prints all defined GRASS variables if no option is given.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.g_gisenv(get=None,set=None,unset=None,store="gisrc",separator="newline",flags=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`get : str | list[str], optional`**
   - GRASS variable to get
   - Used as: variable

2. **`set : str, optional`**
   - GRASS variable to set
   - Used as: "variable=value"

3. **`unset : str | list[str], optional`**
   - GRASS variable to unset
   - Used as: variable

4. **`store : str, optional`**
   - Where GRASS variable is stored
   - Allowed values: gisrc, mapset
   - Default: gisrc

5. **`separator : str, optional`**
   - Separator for multiple GRASS variables
   - Special characters: pipe, comma, space, tab, newline
   - Used as: input, separator, character

6. **`flags : str, optional`**
   - Allowed values: s, n
   - s
   - Use shell syntax (for "eval")
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/g.gisenv.html#__tabbed_2_3) for all details)*

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

g.gisenv outputs and modifies the user's current GRASS variable
settings. When a user runs GRASS, certain variables are set specifying
the GRASS data base, project, mapset, peripheral device drivers, etc.,
being used in the current GRASS session. These variable name settings
are recognized as long as the user is running a GRASS session.

---

## See Also

Related tools:
- [`g.access`](https://grass.osgeo.org/grass-devel/manuals/g.access.html)
- [`g.filename`](https://grass.osgeo.org/grass-devel/manuals/g.filename.html)
- [`g.findfile`](https://grass.osgeo.org/grass-devel/manuals/g.findfile.html)
- [`g.mapsets`](https://grass.osgeo.org/grass-devel/manuals/g.mapsets.html)

---

## Resources

- [Official g.gisenv manual](https://grass.osgeo.org/grass-devel/manuals/g.gisenv.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/g.gisenv.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
