# g.gui.psmap

**Category**: general

## Description

Tool for creating hardcopy map outputs.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.g_gui_psmap(file=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`file : str | io.StringIO, optional`**
   - File containing mapping instructions to load
   - See ps.map manual for details
   - Used as: input, file, name

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

wxGUI Cartographic Composer also called wx.psmap is a wxGUI extension which allows the user to create
interactively hardcopy map outputs. This tool generates ps.map configuration file and then runs ps.map to create PostScript output. There are two modes - Draft mode for map composing and Preview mode (requires Python
Imaging Library ) to see how
the result will look like. In draft mode map features (like legend or
scalebar) are represented by a colored rectangle with a label.

Possible output files:



Cartographic Composer enables to load in saved instructions file.
Loading instruction files created by Cartographic Composer is more
robust, as opposed to loading files created manually.

Currently supported ps.map instructions:

Generate instructions file :
Generates and saves text file with mapping instructions.

Load instructions file :
Load text file with mapping instructions.

Page setup :
Specify paper size, margins and orientation.

Pointer :
Select object on the paper by clicking, drag the cursor while pressing
the left mouse button to move it or resize object (currently only map
frame) by clicking on a small black box in its bottom right corner.
Double click to show object properties dialog

Pan :
Drag the pan cursor while pressing the left mouse button to move your
view.

Zoom in :
Interactive zooming with the mouse in both draft and preview mode.
Drawing a box or just a left click with the mouse and zoom-in cursor
causes the display to zoom in so that the area defined by the box fills
the display.

Zoom out :
Interactive zooming with the mouse in both draft and preview mode.
Drawing a box or just a left click with the mouse and zoom-out cursor
causes the display to zoom out so that the area displayed shrinks to
fill the area defined by the box.

Zoom to page :
Zoom to display the entire page

Map frame :
Click and drag to place map frame. If map frame is already drawn, open a
dialog to set its properties.

Raster map :
Shows a dialog to add or change the raster map.

Vector map :
Shows a dialog to add or change current vector maps and their
properties:

Add overlays :
Add overlays: vector labels, grid (not yet implemented)

Add map elements :
Add map elements: legend, scalebar, map info, text

Remove selected element :
Select an object and remove it. Pressing Delete key does the same.

Show preview :
Generates output and switches to Preview mode to see the result. Be
patient, it can take a while.

Generate hardcopy map output in PS :
Generates hardcopy map output in PostScript/EPS file.

Generate hardcopy map output in PDF :
Generates hardcopy map output in PDF using ps2pdf or Ghostscript
gswin32c/gswin64c (OS
MS Windows platform only).

---

## See Also

Related tools:

---

## Resources

- [Official g.gui.psmap manual](https://grass.osgeo.org/grass-devel/manuals/g.gui.psmap.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/g.gui.psmap.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
