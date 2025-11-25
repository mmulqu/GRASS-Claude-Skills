# g.gui.vdigit

**Category**: general

## Description

Interactive editing and digitization of vector maps.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.g_gui_vdigit(map,flags=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`map : str, required`**
   - Name of vector map to edit
   - Or data source for direct OGR access
   - Used as: input, vector, name

2. **`flags : str, optional`**
   - Allowed values: c
   - c
   - Create new vector map if doesn't exist

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

The vector digitizer is a wxGUI component intended for
interactive editing and digitizing vector maps (see v.edit for non-interactive vector editing GRASS
capabilities).

Note that only vector maps stored or generated in the current mapset
can be opened for editing.

The digitizer allows editing of 2D vector features (points, lines,
centroids, boundaries, and areas).

Vector features can be selected by mouse (bounding box or simply by
mouse click, see select threshold in Settings→General→Select
threshold ), or by query (eg. by line length, see Settings→Query
Tool ).

The vector digitizer can be launched from Map Display toolbar by
selecting "Digitize" from Tools combobox. Vector map is selectable for
editing from Digitizer toolbar ("Select vector map" combobox, note that
only vector maps from the current layer tree in Layer Manager are
listed). The vector digitizer can alternatively be activated from the
contextual menu in the Layer Manager by selecting "Start editing" on
selected vector map in the layer tree, or directly from the Layer
Manager toolbar . The vector digitizer also can
also be launched from the command line as a stand-alone application g.gui.vdigit .

A new vector map can be easily created from the digitizer toolbar by
selecting "New vector map" in "Select vector map" combobox. A new vector
map is created, added to the current layer tree in Layer Manager and
opened for editing. "Select vector map" combobox in the digitizer
toolbar also allows easily switching between vector maps to be edited.

An existing vector map selected in the digitizer toolbar in the "Select
vector map" combobox. This map is then opened for editing and added to
the current layer tree in the Layer Manager . This "Select vector map"
combobox in the digitizer toolbar also allows to easily switch between
vector maps to be edited.

In order to digitize from a raster map, simply load the map into the Map Display using the Layer Manager . Then start digitizing, see
below for details.

The vector digitizer allows you to select a "background" vector map.
Loading it within the digitizer is different from simply loading it via Layer Manager since direct interaction with single vector features
then becomes possible. Vector features may be copied from the background map by "Copy features
from (background) vector map" tool from the "Additional tools" of the
digitizer toolbar. Newly digitized vector features are snapped in the
given threshold to the features from the background map.



Digitize new point :
Add new point to vector map and optionally define its attributes
(Ctrl+P).

Digitize new line :
Add new line to vector map and optionally define its attributes
(Ctrl+L).

Digitize new boundary :
Add new boundary to vector map and optionally define its attributes
(Ctrl+B).

Digitize new centroid :
Add new centroid to vector map and optionally define its attributes
(Ctrl+C).

Digitize new area :
Add new area (closed boundary and one centroid inside) to vector map and
optionally define its attributes (Ctrl+A).

Move vertex :
Move selected vertex of linear feature. Thus shape of linear feature is
changed (Ctrl+G).

Add vertex :
Add new vertex to selected linear feature (shape not changed) (Ctrl+V).

Remove vertex :
Remove selected vertex from linear feature (Ctrl+X). Thus shape of
selected feature can be changed.

Edit line/boundary :
Edit selected linear feature, add new segments or remove existing
segments of linear feature (Ctrl+E).

Move feature(s) :
Move selected vector features (Ctrl+M.) Selection can be done by mouse
or by query.

Delete feature(s) :
Delete selected vector features (point, line, centroid, or boundary)
(Ctrl+D). Selection can be done by mouse or by query.

Delete areas(s) :
Delete selected vector areas (Ctrl+F). Selection can be done by mouse or
by query.

Display/update categories :
Display categories of selected vector feature (Ctrl+J). Category
settings can be modified, new layer/category pairs added or already
defined pairs removed.

Display/update attributes :
Display attributes of selected vector feature (based on its category
settings) (Ctrl+K). Attributes can be also modified. Same functionality
is accessible from Main toolbar "Query vector map (editable mode)".

Additional tools :

Undo :
Undo previous operations (Ctrl+Z).

Redo :
Redo previous operations (Ctrl+Y).

Settings :
Digitizer settings (Ctrl+T).

Show help :
Show help page for the Digitizer (Ctrl+H).

Quit digitizing tool :
Changes in vector map can be optionally discarded when digitizing
session is quited (Ctrl+Q).

---

## See Also

Related tools:

---

## Resources

- [Official g.gui.vdigit manual](https://grass.osgeo.org/grass-devel/manuals/g.gui.vdigit.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/g.gui.vdigit.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
