# d.graph

**Category**: display

## Description

Program for generating and displaying simple graphics on the display monitor.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.d_graph(input=None,color="black",flags=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str | io.StringIO, optional`**
   - Name of file containing graphics commands, if not given reads from standard input
   - Used as: input, file, name

2. **`color : str, optional`**
   - Color to draw with, either a standard GRASS color or R:G:B triplet
   - Used as: color
   - Default: black

3. **`flags : str, optional`**
   - Allowed values: m
   - m
   - Coordinates are given in map units

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

d.graph draws graphics that are described either from standard input
(default), or within a file (if an input file name is identified on
the command line). If graphics commands are entered from standard input,
a CTRL-d is used to signal the end of input to d.graph . Coordinates
are given either as a percentage of frame height and width (default) or
in geographic coordinates (with the -m flag).

The program can be run interactively or non-interactively. The user can
run the program completely non-interactively by specifying the name of a
graphics file containing the d.graph graphics commands. If run
non-interactively the d.graph command is saved to the display's dedraw
history. The user can also elect to run the program partially
interactively, by specifying any/all of the parameters except the
graphics file input= name parameter on the command line. In this
case, d.graph will expect the user to input d.graph graphics
commands from standard input (i.e., the keyboard) and will (silently)
prompt the user for these graphics commands.

Alternately, the user can simply type d.graph on the command line,
and be prompted for the values of all parameters. In this case, the user
is presented with the standard GRASS GUI interface.

The default coordinate system used is 0-100 percent of the active frame
in x and similarly 0-100 in y, regardless of the graphics monitor
display frame size and aspect. The (0,0) location is the lower left
corner of the active graphics monitor display frame. All values may be
floating point. If the -m flag is given, geographic coordinates will
be used instead.

---

## See Also

Related tools:
- [`d.font`](https://grass.osgeo.org/grass-devel/manuals/d.font.html)
- [`d.labels`](https://grass.osgeo.org/grass-devel/manuals/d.labels.html)
- [`d.polar`](https://grass.osgeo.org/grass-devel/manuals/d.polar.html)
- [`d.text`](https://grass.osgeo.org/grass-devel/manuals/d.text.html)
- [`d.where`](https://grass.osgeo.org/grass-devel/manuals/d.where.html)

---

## Resources

- [Official d.graph manual](https://grass.osgeo.org/grass-devel/manuals/d.graph.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/d.graph.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
