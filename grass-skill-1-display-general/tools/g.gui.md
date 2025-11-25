# g.gui

**Category**: general

## Description

Launches a GRASS graphical user interface (GUI) session. Optionally updates default user interface settings.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.g_gui(ui="wxpython",workspace=None,flags=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`ui : str, optional`**
   - User interface
   - Allowed values: wxpython, text, gtext
   - wxpython: wxPython based GUI (wxGUI)
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/g.gui.html#__tabbed_2_3) for all details)*

2. **`workspace : str | io.StringIO, optional`**
   - Name of workspace file to load on start-up
   - This is valid only for wxGUI (wxpython)
   - Used as: input, file, name.gxw

3. **`flags : str, optional`**
   - Allowed values: f, d, n
   - f
   - Start GUI in the foreground
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/g.gui.html#__tabbed_2_3) for all details)*

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

The g.gui module allows user to start the Graphical User Interface
(GUI) from the command line prompt or to change the default User
Interface (UI) settings.

GRASS comes with both a wxPython-based GUI aka wxGUI ( ui=wxpython ) and command line text-based UI ( ui=text ).

---

## See Also

Related tools:
- [`g.gisenv`](https://grass.osgeo.org/grass-devel/manuals/g.gisenv.html)

---

## Authors

Martin Landa, FBK-irst, Trento, Italy Hamish Bowman, Otago University, Dunedin, New Zealand (fine tuning)

---

## Resources

- [Official g.gui manual](https://grass.osgeo.org/grass-devel/manuals/g.gui.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/g.gui.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
