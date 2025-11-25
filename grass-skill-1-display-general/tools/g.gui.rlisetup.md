# g.gui.rlisetup

**Category**: general

## Description

Configuration tool for r.li modules.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.g_gui_rlisetup(verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

2. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

3. **`superquiet : bool, optional`**
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

The g.gui.rlisetup is a wxGUI component which allows
the user to create a configuration file for the analytical r.li modules. For a general introduction, see the r.li overview. The configurations are raster map independent, it means that you can use
a file created on a raster map for analyze any other you have. The program is completely interactive and uses a GUI to help you in your
choices.

Definition of creation of sampling area:



Definition of region for analysis:

The startup window shows your configuration files, you can:

---

## See Also

Related tools:
- [`r.li`](https://grass.osgeo.org/grass-devel/manuals/r.li.html)
- [`r.li.daemon`](https://grass.osgeo.org/grass-devel/manuals/r.li.daemon.html)

---

## Authors

Luca Delucchi Rewritten from r.li.setup by Claudio Porta and Lucio Davide Spano

---

## Resources

- [Official g.gui.rlisetup manual](https://grass.osgeo.org/grass-devel/manuals/g.gui.rlisetup.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/g.gui.rlisetup.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
