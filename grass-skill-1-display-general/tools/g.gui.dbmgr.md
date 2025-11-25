# g.gui.dbmgr

**Category**: general

## Description

Launches graphical attribute table manager.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.g_gui_dbmgr(map,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`map : str, required`**
   - Name of vector map
   - Or data source for direct OGR access
   - Used as: input, vector, name

2. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

3. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

4. **`superquiet : bool, optional`**
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

The Attribute Table Manager is a wxGUI component to
query, edit, and manage attribute data for vector maps. The attribute
table manager can be launched by clicking on icon in the toolbar. It's also available as a
stand-alone module g.gui.dbmgr .

Attribute table manager allows you to:

Figure: Simple attribute filtering using Attribute Table Manager.

Figure: Attribute filtering using Attribute Table Manager and SQL
Builder.

---

## See Also

Related tools:

---

## Authors

Martin Landa, FBK-irst (2007-2008), Trento, Italy,
and OSGeoREL at the Czech Technical University in Prague, Czech
Republic Michael Barton, Arizona State University, USA Jachym Cepicky

---

## Resources

- [Official g.gui.dbmgr manual](https://grass.osgeo.org/grass-devel/manuals/g.gui.dbmgr.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/g.gui.dbmgr.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
