# d.font

**Category**: display

## Description

Selects the font in which text will be displayed on the user's graphics monitor.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.d_font(font="romans",path=None,charset="UTF-8",flags=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`font : str, optional`**
   - Choose new current font
   - Default: romans

2. **`path : str, optional`**
   - Path to Freetype-compatible font including file name
   - Used as: input, file, name

3. **`charset : str, optional`**
   - Character encoding
   - Default: UTF-8

4. **`flags : str, optional`**
   - Allowed values: l, v
   - l
   - List fonts
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/d.font.html#__tabbed_2_3) for all details)*

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

d.font allows the user to select use of a specific text font for
display of text on the graphics monitor. If the user does not specify a
font when using other GRASS programs that display text, the font type romans is used by default.

The user can run this program either non-interactively or interactively.
If the user specifies a font type name on the command line the program
will run non-interactively. Alternately, the user can simply type d.font on the command line; in this case, the program will prompt
the user for a display text font type.

Font options (italized):

---

## See Also

Related tools:
- [`d.text`](https://grass.osgeo.org/grass-devel/manuals/d.text.html)
- [`d.title`](https://grass.osgeo.org/grass-devel/manuals/d.title.html)

---

## Resources

- [Official d.font manual](https://grass.osgeo.org/grass-devel/manuals/d.font.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/d.font.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
