# g.message

**Category**: general

## Description

Prints a message, warning, progress info, or fatal error in the GRASS way. This module should be used in scripts for messages served to user.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.g_message(message,debug=1,flags=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`message : str, required`**
   - Text of the message to be printed
   - Message is printed on GRASS_VERBOSE>=2
   - Used as: string

2. **`debug : int, optional`**
   - Level to use for debug messages
   - Allowed values: 0-5
   - Default: 1

3. **`flags : str, optional`**
   - Allowed values: w, e, d, p, i, v
   - w
   - Print message as warning
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/g.message.html#__tabbed_2_3) for all details)*

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

g.message prints a message, warning, progress info, or fatal error in
the GRASS way. This program is to be used in Shell/Perl/Python
scripts, so the author does not need to use the echo program. The
advantage of g.message is that it formats messages just like other
GRASS modules do and that its functionality is influenced by the GRASS_VERBOSE and GRASS_MESSAGE_FORMAT environment variables.

The program can be used for standard informative messages as well as
warnings ( -w flag) and fatal errors ( -e flag). For debugging
purposes, the -d flag will cause g.message to print a debugging
message at the given level.

---

## See Also

Related tools:
- [`g.gisenv`](https://grass.osgeo.org/grass-devel/manuals/g.gisenv.html)
- [`g.parser`](https://grass.osgeo.org/grass-devel/manuals/g.parser.html)

---

## Resources

- [Official g.message manual](https://grass.osgeo.org/grass-devel/manuals/g.message.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/g.message.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
