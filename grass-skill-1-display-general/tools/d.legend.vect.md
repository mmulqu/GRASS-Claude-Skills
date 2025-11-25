# d.legend.vect

**Category**: display

## Description

Displays a vector legend in the active graphics frame.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.d_legend_vect(at="10,40",columns=1,title=None,symbol_size=20,border_color="black",bgcolor="white",border_width=2,font=None,fontsize=None,title_font=None,title_fontsize=None,sub_font=None,sub_fontsize=None,fontcolor="black",separator="pipe",input=None,output=None,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`at : tuple[float, float] | list[float] | str, optional`**
   - Screen position of legend to be drawn (percentage, [0,0] is lower left)
   - Used as: left,top
   - Allowed values: 0-100

2. **`columns : int, optional`**
   - Number of legend columns
   - Default: 1

3. **`title : str, optional`**
   - Legend title

4. **`symbol_size : int, optional`**
   - Symbol size
   - Default: 20

5. **`border_color : str, optional`**
   - Border color
   - Either a standard color name, R:G:B triplet, or "none"
   - Used as: input, color, name

6. **`bgcolor : str, optional`**
   - Background color
   - Either a standard color name, R:G:B triplet, or "none"
   - Used as: input, color, name

7. **`border_width : int, optional`**
   - Background border width
   - Default: 2

8. **`font : str, optional`**
   - Font name

9. **`fontsize : float, optional`**
   - Font size
   - Default: 12
   - Allowed values: 1-360

10. **`title_font : str, optional`**
   - Title font name

11. **`title_fontsize : float, optional`**
   - Title font size
   - Default: 18
   - Allowed values: 1-360

12. **`sub_font : str, optional`**
   - Subtitle font name

13. **`sub_fontsize : float, optional`**
   - Subtitle font size
   - Default: 14
   - Allowed values: 1-360

14. **`fontcolor : str, optional`**
   - Font color
   - Either a standard color name or R:G:B triplet
   - Used as: input, color, name

15. **`separator : str, optional`**
   - Field separator for input file
   - Special characters: pipe, comma, space, tab, newline
   - Used as: input, separator, character

16. **`input : str | io.StringIO, optional`**
   - Input legend file
   - Path to legend file
   - Used as: input, file, name

17. **`output : str, optional`**
   - Output csv file
   - Path to output file or '-' for standard output
   - Used as: output, file, name

18. **`flags : str, optional`**
   - Allowed values: b
   - b
   - Display legend background

19. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

20. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

21. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

22. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 22 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/d.legend.vect.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

d.legend.vect draws vector legend of currently displayed vector maps.

Parameter at defines the screen position of upper-left legend
corner. Parameter columns defines the number of legend columns. User
can specify a title of the legend using parameter title . The font of
the title can be changed with title_font , title_fontsize . Flag -b is used to draw background of specified color ( bgcolor ),
border color and border width ( border_color and border_width ).
Parameter symbol_size defines the size of line and area symbols. The
size of point symbols is based on currently set symbology of vector maps
using d.vect or d.vect.thematic .

Module d.vect.legend supports subtitles (see section Notes). Their
font and font size can be set using parameters sub_font and sub_fontsize .

Symbols for vector areas and lines, and labels for individual vector
labels can be changed in the symbology setting of each vector map in d.vect or d.vect.thematic module
(in Legend tab). Use its parameters icon_area and icon_line to
pick from available symbols. By using parameter legend_label of d.vect module, users can change the default label, which is the map
name.

Modules d.vect and d.vect.thematic have a flag -s which removes
the particular vector or thematic vector from vector legend.

The order of entries is defined by the order in Layer Manager (if used
in GRASS GUI). If that's not desired, one can export the legend file
into a text file using parameter output , change the order of entries
(see section Notes for format description) and then upload the modified
file with parameter input . Parameter output defines path to the
file where the internal legend file will be saved to, input defines
the input file which the vector legend will be based on (input file must
have correct format).

---

## See Also

Related tools:
- [`d.vect`](https://grass.osgeo.org/grass-devel/manuals/d.vect.html)
- [`d.vect.thematic`](https://grass.osgeo.org/grass-devel/manuals/d.vect.thematic.html)
- [`d.legend`](https://grass.osgeo.org/grass-devel/manuals/d.legend.html)

---

## Authors

Adam Laza, during GSoC 2016 Mentors: Anna Petrasova, Vaclav Petras,
Martin Landa

---

## Resources

- [Official d.legend.vect manual](https://grass.osgeo.org/grass-devel/manuals/d.legend.vect.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/d.legend.vect.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
