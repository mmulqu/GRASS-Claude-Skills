# g.mkfontcap

**Category**: general

## Description

Generates the font configuration file by scanning various directories for fonts.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.g_mkfontcap(extradirs=None,flags=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`extradirs : str, optional`**
   - List of extra directories to scan
   - Comma-separated list of extra directories to scan for Freetype-compatible fonts as well as the defaults (see documentation)

2. **`flags : str, optional`**
   - Allowed values: s
   - s
   - Write font configuration file to standard output instead of $GISBASE/etc

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

g.mkfontcap is a utility to generate a GRASS font configuration file
("fontcap") containing details of the fonts available on the current
system. If Freetype is not installed, the font
list will be limited to the set of Hershey stroke fonts supplied with
GRASS. With Freetype enabled however, the module will recursively scan
all files within a predefined hierarchy to find Freetype-compatible
scalable fonts. The list of directories scanned is currently:

These correspond to directories where fonts can be found on some common
operating systems. Extra directories to search can easily by added using
the extradirs parameter, which accepts a comma-separated list. An
extra directory may optionally contain an environment variable at the
start of the string, if enclosed in ${xxx} syntax (see examples
above).

The module will normally write to the standard fontcap file location, $GISBASE/etc/fontcap . If the environment variable GRASS_FONT_CAP is
set, the output will instead be written to the file specified by that
variable. This is useful if you don't have permission to modify $GISBASE/etc/fontcap : in this case you can use e.g.

to create a personal copy and then to make GRASS use that file instead
of the system copy.

The output list of fonts is sorted first by type (Stroke fonts first,
followed by Freetype) and within each type by the short name of the
font.

---

## See Also

Related tools:
- [`d.font`](https://grass.osgeo.org/grass-devel/manuals/d.font.html)

---

## Resources

- [Official g.mkfontcap manual](https://grass.osgeo.org/grass-devel/manuals/g.mkfontcap.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/g.mkfontcap.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
