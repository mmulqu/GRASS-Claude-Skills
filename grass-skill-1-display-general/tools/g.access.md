# g.access

**Category**: general

## Description

Controls access to the current mapset for other users on the system. If no option given, prints current status.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.g_access(group=None,other=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`group : str, optional`**
   - Access for group
   - Allowed values: grant, revoke

2. **`other : str, optional`**
   - Access for others
   - Allowed values: grant, revoke

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

This program allows the user to control access to the current mapset.
Normally, any user can read data from any GRASS mapset. But sometimes it
is desirable to prohibit access to certain sensitive data. The g.access command allows a user to restrict read and execute access to
the current mapset (see UNIX chmod command). g.access will not
modify write access to the current mapset.

The user may, for example, allow only users in the same UNIX group to
read data files in the mapset, or restrict the mapset to personal use
only.

---

## See Also

Related tools:
- [`g.mapsets`](https://grass.osgeo.org/grass-devel/manuals/g.mapsets.html)

---

## Resources

- [Official g.access manual](https://grass.osgeo.org/grass-devel/manuals/g.access.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/g.access.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
