# d.labels

**Category**: display

## Description

Displays text labels (created with v.label) to the active frame on the graphics monitor.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.d_labels(labels,minreg=None,maxreg=None,flags=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`labels : str, required`**
   - Name of label file
   - Used as: input, paint labels

2. **`minreg : float, optional`**
   - Minimum region size (diagonal) when labels are displayed

3. **`maxreg : float, optional`**
   - Maximum region size (diagonal) when labels are displayed

4. **`flags : str, optional`**
   - Allowed values: i
   - i
   - Ignore rotation setting and draw horizontally

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

d.labels displays a paint label file in the active display frame on
the graphics monitor. Each label has components which determine the
text, the location of the text on the image, its size, and the
background for the text. This file can be generated with the v.label program or simply created by the user as an
ASCII file (using a text editor) and placed in the appropriate directory
under the user's current mapset and project (i.e. $MAPSET/paint/labels/ ).

---

## See Also

Related tools:
- [`d.font`](https://grass.osgeo.org/grass-devel/manuals/d.font.html)
- [`d.text`](https://grass.osgeo.org/grass-devel/manuals/d.text.html)
- [`d.title`](https://grass.osgeo.org/grass-devel/manuals/d.title.html)
- [`ps.map`](https://grass.osgeo.org/grass-devel/manuals/ps.map.html)
- [`v.label`](https://grass.osgeo.org/grass-devel/manuals/v.label.html)

---

## Resources

- [Official d.labels manual](https://grass.osgeo.org/grass-devel/manuals/d.labels.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/d.labels.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
