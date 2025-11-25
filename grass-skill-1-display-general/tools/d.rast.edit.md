# d.rast.edit

**Category**: display

## Description

Edits cell values in a raster map.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.d_rast_edit(input,output,aspect=None,width=640,height=480,size=12,rows=100,cols=100,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str | np.ndarray, required`**
   - Name of input raster map
   - Used as: input, raster, name

2. **`output : str | type(np.ndarray) | type(np.array) | type(gs.array.array), required`**
   - Name for output raster map
   - Used as: output, raster, name

3. **`aspect : str | np.ndarray, optional`**
   - Name of input aspect raster map
   - Used as: input, raster, name

4. **`width : int, optional`**
   - Width of display canvas
   - Default: 640

5. **`height : int, optional`**
   - Height of display canvas
   - Default: 480

6. **`size : int, optional`**
   - Minimum size of each cell
   - Default: 12

7. **`rows : int, optional`**
   - Maximum number of rows to load
   - Default: 100

8. **`cols : int, optional`**
   - Maximum number of columns to load
   - Default: 100

9. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

10. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

11. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

12. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 12 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/d.rast.edit.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | np.ndarray | tuple[np.ndarray] | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned. If an array type (e.g., np.ndarray) is used for one of the raster outputs, the result will be an array and will have the shape corresponding to the computational region. If an array type is used for more than one raster output, the result will be a tuple of arrays.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

The d.rast.edit program allows users to interactively edit cell
category values in a raster map layer displayed to the graphics monitor
using a mouse cursor.

An overview window shows the entire map with a red box showing the
current editing region. The edit window shows the cells within the
selected area. Click on a new spot on the overview window to move the
editing area.

Cell editing is done using the mouse cursor to indicate the cell(s) on
the displayed raster map that are to be edited.

To change the value of a cell put the new value to use in the "New
value" box at the bottom left of the edit window. A value of "*"
indicates a NULL value should be used.

Important: the new value in the "New value" box must be confirmed
with ENTER, otherwise it is not yet active.

To save the edited map, the "File" menu contains the entry Save . To
leave d.rast.edit , use Exit in the menu.

The map can be shifted using the arrow keys on the keyboard.

---

## See Also

Related tools:
- [`d.rast.arrow`](https://grass.osgeo.org/grass-devel/manuals/d.rast.arrow.html)
- [`d.rast.num`](https://grass.osgeo.org/grass-devel/manuals/d.rast.num.html)
- [`wxGUI.rdigit`](https://grass.osgeo.org/grass-devel/manuals/wxGUI.rdigit.html)

---

## Authors

Tcl/Tk (2007) and wxPython versions (2008): Glynn Clements
Replaces Xdriver version in C by Chris Rewerts, April 1991, Agricultural
Engineering, Purdue University

---

## Resources

- [Official d.rast.edit manual](https://grass.osgeo.org/grass-devel/manuals/d.rast.edit.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/d.rast.edit.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
