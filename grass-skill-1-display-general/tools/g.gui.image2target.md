# g.gui.image2target

**Category**: general

## Description

Georectifies a map and allows managing Ground Control Points for 3D correction.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.g_gui_image2target(verbose=None,quiet=None,superquiet=None)
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

The GCP Manager is a wxGUI extension which allows the
user to create, edit, and manage Ground Control Points. It is available
from the menu "File | Manage Ground Control Points".

The GCP Manager provides an interactive graphical interface to
manage and analyze Ground Control Points. A backup copy of the initial
POINTS file is always maintained and updated only on request (Save GCPs
to POINTS file). This guarantees that accidental changes are not
permanent and can be undone by reloading the Ground Control Points.

The GCP Manager must be started in the target project, not in the source
project (project used to be called location).

The GCP Manager is structured into three panels:



Two toolbars are provided with the GCP Manager, one for managing the map
displays and one for managing the GCP list.

The list of Ground Control Points can be sorted by clicking on a column
header. Clicking on a column header will sort the GCPs ascending, a
second click on the same column will sort the GCPs descending. Overall
RMS error and individual RMS errors of all points are often improved if
the GCP with the highest RMS error is adjusted. Individual coordinates
can be edited by double-clicking on a row.

The first column holds a checkbox and displays the point number. A GCP
is only used for RMS error calculation and georectification if its
checkbox on the left is checked. Uncheck to deactivate a GCP (mark as
unused GCP).

The left panel is used to display a map from the source project, the
right panel to display a map from the target project. Zooming in and out
is always possible with the mouse wheel and done for each map canvas
separately.

GCPs are displayed in different colors, depending on whether a GCP has a
high RMS error, is currently unused or is currently selected.
Optionally, currently unused GCPs are not shown on the map display.

At the bottom of the GCP Manager is a statusbar providing several
functions. The default is set to Go to GCP No. (see also below).
Typing a number or using the up/down arrows will center the maps on the
given GCP, useful with a high zoom.

Display map :
Displays maps for source and target canvas and re-renders any layers
that have changed since the last time the display was updated.

Re-render map :
Re-renders both source and target canvas regardless of whether they have
changed or not.

Erase display :
Erases both source and target canvas to a white background.

Define GCP (Ground Control Points) :
On left mouse click, coordinates are defined for the currently selected
GCP.

Pan :
Interactive selection of a new center of view in the active display
monitor. Drag the pan cursor while pressing the left mouse button to
pan. Alternatively left-click on the new center. Panning changes the
location of the region displayed but not the size of the area displayed
or the resolution.

Zoom in :
Interactive zooming with the mouse in the active map canvas (source or
target). Drawing a box or just a left click with the mouse and zoom-in
cursor causes the display to zoom in so that the area defined by the box
fills the display. The map resolution is not changed. Clicking with the
zoom-in cursor causes the display to zoom in by 30%, centered on the
point where the mouse is clicked. Zooming changes the display region
extents (both size and location of area displayed).

Zoom out :
Interactive zooming with the mouse in the active map canvas (source or
target). Drawing a box or just a left click with the mouse and zoom-out
cursor causes the display to zoom out so that the area displayed shrinks
to fill the area defined by the box. The map resolution is not changed.
Clicking with the zoom-out cursor causes the display to zoom out by 30%,
centered on the point where the mouse is clicked. Zooming changes the
display region extents (both size and location of area displayed).

Adjust display zoom :
Source and target display are adjusted by using the current GCPs for
coordinate transformation:

Set active map canvas :
Sets the currently active map canvas (source or target). Click to set
active map canvas for Return to previous zoom or Zoom to extent of
currently displayed map . Alternatively, move the mouse over the map
canvas to be used as active canvas.

Return to previous zoom :
Returns to the previous zoom extent. Up to 10 levels of zoom back are
maintained.

Zoom to extent of currently displayed map :
Zoom to the extent of the currently displayed map in the active map
canvas (source or target).

Settings :
Shows a settings dialog for GCP management and display:

Show Help :
Show help page for the GCP Manager.

Quit :
Quit the GCP Manager.

Save GCPs to POINTS file :
The current list of GCPs is saved to the imagery group's POINTS file and
to a backup copy.

Add new GCP :
Adds a new Ground Control Point to the list and selects it for editing.

Delete selected GCP :
Deletes the currently selected GCP from the list.

Clear selected GCP :
Resets all coordinates of the currently selected GCP to 0 (zero).

Reload GCPs from POINTS file :
Reloads GCPs from the imagery group's POINTS file.

Recalculate RMS error :
Recalculates forward and backward RMS error for all GCP marked for use
(activated checkbox in first row).

Georectify :
Uses i.rectify to georectify all images in the source
imagery group.

The GCP map display statusbar is similar to the statusbar in the regular
GRASS map display with two differences, Go to has been replaced
with Go to GCP No. and Projection has been replaced with RMS
error .

If Go to GCP No. is selected, a GCP number can be given in the left
side of the statusbar and the source and target map canvas will be
centered on the given GCP. Clicking on the map canvas will update
coordinates for this GCP.

If RMS error is selected, the overall forward and backward RMS error
is displayed.

---

## See Also

Related tools:

---

## Authors

Markus Metz
Based on the Georectifier (GRASS 6.4.0) by Michael Barton Martin Landa, Czech Technical University in Prague, Czech Republic

---

## Resources

- [Official g.gui.image2target manual](https://grass.osgeo.org/grass-devel/manuals/g.gui.image2target.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/g.gui.image2target.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
