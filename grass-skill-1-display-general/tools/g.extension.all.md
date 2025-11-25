# g.extension.all

**Category**: general

## Description

Rebuilds or removes all locally installed GRASS Addons extensions. By default only extensions built against different GIS Library are rebuilt.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.g_extension_all(operation="rebuild",flags=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`operation : str, optional`**
   - Operation to be performed
   - Allowed values: rebuild, remove
   - Default: rebuild

2. **`flags : str, optional`**
   - Allowed values: f
   - f
   - Force operation (required for removal)

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

g.extension.rebuild.all reinstalls and updates all locally installed
GRASS Addons extensions in local GRASS installation. The extensions can
be installed by g.extension . List of locally
installed extensions can be printed by g.extension -a .

---

## See Also

Related tools:
- [`g.extension`](https://grass.osgeo.org/grass-devel/manuals/g.extension.html)

---

## Resources

- [Official g.extension.all manual](https://grass.osgeo.org/grass-devel/manuals/g.extension.all.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/g.extension.all.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
