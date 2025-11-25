# d.mon

**Category**: display

## Description

Controls graphics display monitors from the command line.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.d_mon(start=None,stop=None,select=None,width=None,height=None,resolution=None,bgcolor="white",output=None,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`start : str, optional`**
   - Name of monitor to start
   - Allowed values: wx0, wx1, wx2, wx3, wx4, wx5, wx6, wx7, png, ps, html, cairo

2. **`stop : str, optional`**
   - Name of monitor to stop
   - Allowed values: wx0, wx1, wx2, wx3, wx4, wx5, wx6, wx7, png, ps, html, cairo

3. **`select : str, optional`**
   - Name of monitor to select
   - Allowed values: wx0, wx1, wx2, wx3, wx4, wx5, wx6, wx7, png, ps, html, cairo

4. **`width : int, optional`**
   - Width for display monitor if not set by GRASS_RENDER_WIDTH
   - Default value: 720
   - Used as: value

5. **`height : int, optional`**
   - Height for display monitor if not set by GRASS_RENDER_HEIGHT
   - Default value: 480
   - Used as: value

6. **`resolution : int, optional`**
   - Dimensions of display monitor versus current size
   - Example: resolution=2 enlarge display monitor twice to 1280x960
   - Used as: value

7. **`bgcolor : str, optional`**
   - Background color
   - Either a standard color name, R:G:B triplet, or "none"
   - Used as: input, color, name

8. **`output : str, optional`**
   - Name for output file (when starting new monitor)
   - Ignored for 'wx' monitors
   - Used as: output, file, name

9. **`flags : str, optional`**
   - Allowed values: l, p, c, g, s, r, t, u, x
   - l
   - List running monitors and exit
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/d.mon.html#__tabbed_2_3) for all details)*

10. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

11. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

12. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

13. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 13 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/d.mon.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

d.mon allows the user to start, select, list, release, and stop
available graphics monitors.

In order to display on-screen GRASS graphics, the user must start and select a graphics monitor. By default, the start command
actually runs two commands, to both start and select whatever monitor is
named by the user. The user can get a list of running monitors by
setting the -l flag on the command line. Note that some monitor drivers use environment variables or the specific driver
documentation .

When a monitor is started , it is therefore also (automatically) selected for output, unless the -s flag is set by the user; the
user can also explicitly select a monitor that has been started.

The desired monitor should be started once and need not be restarted
unless it is stopped for some reason. A monitor may continue to run for
any length of time, even when no GRASS session is being run.

A graphics monitor has two different types of status: monitor program not running , and monitor running . A monitor that has been started
and/or selected will be listed as running; a monitor that has been
stopped (or not started) will be listed as not running. The -l flag
will list all currently running monitors.

When the user starts a monitor, it is also (automatically) selected for graphics output unless the user sets the -s flag. In order to
use (direct graphics output to) a monitor, the user must select that
monitor for use, either by simply starting the monitor without the -s flag or by explicitly selecting the monitor for output. Only
running monitors can be selected for graphics output.

The user can run multiple graphics monitors by simply starting each of
the graphics monitors the user wishes to direct output to.

Currently selected a monitor can be released by -r flag.

---

## See Also

Related tools:
- [`d.erase`](https://grass.osgeo.org/grass-devel/manuals/d.erase.html)
- [`d.redraw`](https://grass.osgeo.org/grass-devel/manuals/d.redraw.html)
- [`d.rast`](https://grass.osgeo.org/grass-devel/manuals/d.rast.html)
- [`d.vect`](https://grass.osgeo.org/grass-devel/manuals/d.vect.html)
- [`d.frame`](https://grass.osgeo.org/grass-devel/manuals/d.frame.html)

---

## Resources

- [Official d.mon manual](https://grass.osgeo.org/grass-devel/manuals/d.mon.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/d.mon.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
