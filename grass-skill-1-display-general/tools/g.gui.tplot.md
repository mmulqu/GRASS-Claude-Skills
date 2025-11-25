# g.gui.tplot

**Category**: general

## Description

Plots the values of temporal datasets.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.g_gui_tplot(stvds=None,strds=None,coordinates=None,cats=None,attr=None,output=None,csv=None,title=None,xlabel=None,ylabel=None,size=None,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`stvds : str | list[str], optional`**
   - Name of the input space time vector datasets
   - Used as: input, stvds, name

2. **`strds : str | list[str], optional`**
   - Name of the input space time raster datasets
   - Used as: input, strds, name

3. **`coordinates : tuple[float, float] | list[float] | str, optional`**
   - Coordinates
   - Used as: input, coords, east,north

4. **`cats : str, optional`**
   - Categories of vectors features
   - To use only with stvds

5. **`attr : str, optional`**
   - Name of attribute
   - Name of attribute which represent data for plotting

6. **`output : str, optional`**
   - Name for output graphical file
   - Full path for output file containing the plot, ddd extension to specify format (.png, .pdf, .svg)
   - Used as: output, file, name

7. **`csv : str, optional`**
   - Name for output CSV file
   - Full path for the CSV file containing the plotted data
   - Used as: output, file, name

8. **`title : str, optional`**
   - Title for plot
   - The title for the output plot

9. **`xlabel : str, optional`**
   - Label for x axis
   - The x axis label for the output plot

10. **`ylabel : str, optional`**
   - Label for y axis
   - The y axis label for the output plot

11. **`size : str, optional`**
   - Size of output image as width,height in pixels
   - It works only with output parameter

12. **`flags : str, optional`**
   - Allowed values: h, l
   - h
   - Set the header of CSV file, to be used with csv option
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/g.gui.tplot.html#__tabbed_2_3) for all details)*

13. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

14. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

15. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

16. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 16 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/g.gui.tplot.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

The Temporal Plot Tool is a wxGUI component that
queries and plots the values of a point, defined by a coordinate pair,
in one or more temporal datasets (strds, stvds, str3ds).

Supported features:

because these software packages use a reference date other than the
  UNIX Epoch time (00:00:00 UTC on 1 January 1970)).

Figure: Temporal Plot Tool

To optionally add a title to the temporal plot and/or change the x and y
axes labels, first type the desired text and then click Draw as showed
below.

Figure: Add title and labels to a time series plot

To export the time series data to a text file (date and data values),
type a name for the file and click Draw again. Optionally, set the
check-box to print headers, as well.

g.gui.tplot export time series as csv file Figure: Export time series values to a text file

---

## See Also

Related tools:

---

## Resources

- [Official g.gui.tplot manual](https://grass.osgeo.org/grass-devel/manuals/g.gui.tplot.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/g.gui.tplot.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
