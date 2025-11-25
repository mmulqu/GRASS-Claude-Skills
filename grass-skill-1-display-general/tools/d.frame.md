# d.frame

**Category**: display

## Description

Manages display frames on the user's graphics monitor.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.d_frame(frame,at=None,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`frame : str, required`**
   - Frame to be selected or created (if -c flag is given)
   - Used as: name

2. **`at : tuple[float, float, float, float] | list[float] | str, optional`**
   - Screen coordinates in percent where to place the frame (0,0 is lower-left)
   - Implies only when -c or --overwrite flag is given
   - Used as: bottom,top,left,right

3. **`flags : str, optional`**
   - Allowed values: c, e, p, a
   - c
   - Create a new frame if doesn't exist and select
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/d.frame.html#__tabbed_2_3) for all details)*

4. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

5. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

6. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

7. **`superquiet : bool, optional`**
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

d.frame manages display frames on the current user's graphics monitor.
Graphics are displayed in rectangular frames on whatever graphics
monitor the user is currently directing GRASS display output to (defined
by d.mon module). These frames are created and managed
with this module.

Note that GRASS frame contents are not retained when one frame covers
another. You cannot shuffle frames from top to bottom and then back
again. They simply define rectangular areas on the screen where
subsequent drawing will occur.

---

## See Also

Related tools:
- [`d.erase`](https://grass.osgeo.org/grass-devel/manuals/d.erase.html)
- [`d.info`](https://grass.osgeo.org/grass-devel/manuals/d.info.html)
- [`d.mon`](https://grass.osgeo.org/grass-devel/manuals/d.mon.html)
- [`d.redraw`](https://grass.osgeo.org/grass-devel/manuals/d.redraw.html)

---

## Authors

Martin Landa, Czech Technical University in Prague, Czech Republic
Based on d.frame from GRASS 6: James Westervelt, U.S. Army Construction Engineering Research
Laboratory Michael Shapiro, U.S. Army Construction Engineering Research Laboratory

---

## Resources

- [Official d.frame manual](https://grass.osgeo.org/grass-devel/manuals/d.frame.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/d.frame.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
