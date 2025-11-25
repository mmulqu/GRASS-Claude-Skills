# d.text

**Category**: display

## Description

Draws text in the active display frame on the graphics monitor using the current font.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.d_text(text=None,input=None,color="gray",bgcolor="none",rotation=0,linespacing=1.25,at=None,line=None,align="ll",font=None,size=5,path=None,charset=None,flags=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`text : str, optional`**
   - Text to display

2. **`input : str | io.StringIO, optional`**
   - Input file
   - Used as: input, file, name

3. **`color : str, optional`**
   - Text color
   - Either a standard color name or R:G:B triplet
   - Used as: input, color, name

4. **`bgcolor : str, optional`**
   - Text background color
   - Either a standard color name, R:G:B triplet, or "none"
   - Used as: input, color, name

5. **`rotation : float, optional`**
   - Rotation angle in degrees (counter-clockwise)
   - Default: 0

6. **`linespacing : float, optional`**
   - Line spacing
   - Default: 1.25

7. **`at : tuple[float, float] | list[float] | str, optional`**
   - Screen position at which text will begin to be drawn (percentage, [0,0] is lower left)
   - Used as: x,y

8. **`line : int, optional`**
   - The screen line number on which text will begin to be drawn
   - Allowed values: 1-1000

9. **`align : str, optional`**
   - Text alignment
   - Allowed values: ll, lc, lr, cl, cc, cr, ul, uc, ur
   - Default: ll

10. **`font : str, optional`**
   - Font name

11. **`size : float, optional`**
   - Height of letters in percentage of available frame height
   - Allowed values: 0-100
   - Default: 5

12. **`path : str, optional`**
   - Path to font file
   - Used as: input, file, name

13. **`charset : str, optional`**
   - Text encoding (only applicable to TrueType fonts)

14. **`flags : str, optional`**
   - Allowed values: p, g, b, r, s
   - p
   - Screen position in pixels ([0,0] is top left)
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/d.text.html#__tabbed_2_3) for all details)*

15. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

16. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

17. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 17 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/d.text.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

d.text draws text in the active display frame on the graphics monitor.
Text can be provided through standard input or redirected from a file
(using the UNIX redirection mechanism). In addition to the options
provided on the command line, colors, text size, font type, rotation
angle, and boldness can be adjusted with commands in the standard input
(i.e., if the user invokes d.text without options on the command line,
and then assigns values to these options on lines within the standard
input).

.C color (where color is one of the available colors) causes text appearing on
subsequent lines to be drawn in that color.

.G color (where color is one of the available colors) causes the background of
text appearing on subsequent lines to be drawn in that color.

.S size (where size is a percentage within the range 0 to 100) adjusts text
size. Note that a size of 10 would allow 10 lines to be drawn in the
active display frame, 5 would allow the drawing of 20 lines, and 50
would allow the drawing of 2 lines.

.F font (where font is one of the fonts known by the GRASS program d.font ) manipulates the font type. Available fonts are
listed in the GRASS manual entry for d.font . The default
font type used (if unspecified by the user) is romans .

.R rotation (where rotation is an angle in degrees, counter-clockwise) to rotate
the text.

.B 1 stipulates that following text be printed in bold . This command
means bold on .

.B 0 turns bold off of all text appearing on lines beneath it. ( Bold off is used by default, if unspecified by the user.)

---

## See Also

Related tools:
- [`d.font`](https://grass.osgeo.org/grass-devel/manuals/d.font.html)
- [`d.title`](https://grass.osgeo.org/grass-devel/manuals/d.title.html)
- [`d.labels`](https://grass.osgeo.org/grass-devel/manuals/d.labels.html)

---

## Authors

James Westervelt, U.S. Army Construction Engineering Research Laboratory
Updates by Huidae Cho

---

## Resources

- [Official d.text manual](https://grass.osgeo.org/grass-devel/manuals/d.text.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/d.text.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
