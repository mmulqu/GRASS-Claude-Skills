# g.gui.gmodeler

**Category**: general

## Description

Graphical Modeler. Allows interactively creating, editing and managing models.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.g_gui_gmodeler(file=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`file : str | io.StringIO, optional`**
   - Name of model file to be loaded
   - Used as: input, file, name.gxm

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

The Graphical Modeler is a wxGUI component which
allows the user to create, edit, and manage simple and complex models
using an easy-to-use interface. When performing analytical operations in
GRASS, the operations are not isolated, but part of a chain of
operations. Using the Graphical Modeler, a chain of processes (i.e.
GRASS modules) can be wrapped into one process (i.e. model).
Subsequently it is easier to execute the model later on even with
slightly different inputs or parameters. Models represent a programming technique used in GRASS to
concatenate single steps together to accomplish a task. It is
advantageous when the user see boxes and ovals that are connected by
lines and represent some tasks rather than seeing lines of coded text.
The Graphical Modeler can be used as a custom tool that automates a
process. Created models can simplify or shorten a task which can be run
many times and it can also be easily shared with others. Important to
note is that models cannot perform specified tasks that one cannot also
manually perform with GRASS. It is recommended to first to develop
the process manually, note down the steps (e.g. by using the Copy button in module dialogs) and later replicate them in model.

The Graphical Modeler allows you to:

The Graphical Modeler can be launched from the Layer Manager menu File -> Graphical modeler or from the main toolbar . It's also available as stand-alone
module g.gui.gmodeler .

The main Graphical Modeler menu contains options which enable the user
to fully control the model. Directly under the main menu one can find
toolbar with buttons (see figure below). There are options including (1)
Create new model, (2) Load model from file, (3) Save current model to
file, (4) Export model to image, (5) Export model to a
(Python/PyWPS/actinia) script, (6) Add command (GRASS module) to model,
(7) Add data to model, (8) Manually define relation between data and
commands, (9) Add loop/series to model, (10) Add comment to model, (11)
Redraw model canvas, (12) Validate model, (13) Run model, (14) Manage
model variables, (15) Model settings, (16) Show manual, (17) Quit
Graphical Modeler.

Figure: Components of Graphical Modeler menu toolbar.

There is also a lower menu bar in the Graphical modeler dialog where one
can manage model items, visualize commands, add or manage model
variables, define default values and descriptions. The Script editor
dialog window allows seeing and exporting workflows as basic Python
scripts, as PyWPS scripts, or as actinia processes. The rightmost tab of
the bottom menu is automatically triggered when the model is activated
and shows all the steps of running GRASS modeler modules; in the case
some errors occur in the calculation process, they are are written at
that place.

Figure: Lower Graphical Modeler menu toolbar.

The workflow is usually established from four types of diagrams. Input
and derived model data are usually represented with oval diagrams. This
type of model elements stores path to specific data on the user's disk.
It is possible to insert vector data, raster data, database tables, etc.
The type of data is clearly distinguishable in the model by its color.
Different model elements are shown in the figures below.

Figure: A model to perform unsupervised classification using MLC
( i.maxlik ) and SMAP ( i.smap ).

Another example:

Figure: A model to perform estimation of average annual soil loss
caused by sheet and rill erosion using The Universal Soil Loss
Equation.

Example as part of landslide prediction process:

Figure: A model to create parametric maps used by geologists to predict
landslides in the area of interest.

---

## See Also

Related tools:

---

## Authors

Martin Landa, GeoForAll Lab, Czech Technical University in Prague, Czech
Republic PyWPS support by Ondrej Pesek, GeoForAll Lab, Czech Technical University
in Prague, Czech Republic Various manual improvements by Ludmila Furkevicova, Slovak University of
Technology in Bratislava, Slovak Republic

---

## Resources

- [Official g.gui.gmodeler manual](https://grass.osgeo.org/grass-devel/manuals/g.gui.gmodeler.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/g.gui.gmodeler.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
