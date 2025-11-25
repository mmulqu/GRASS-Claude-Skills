# g.gui.mapswipe

**Category**: general

## Description

Interactively compares two maps by swiping a visibility bar.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.g_gui_mapswipe(first=None,second=None,mode="swipe",verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`first : str | np.ndarray, optional`**
   - First (top/right) raster map
   - Used as: input, raster, name

2. **`second : str | np.ndarray, optional`**
   - Second (bottom/left) raster map
   - Used as: input, raster, name

3. **`mode : str, optional`**
   - View mode
   - Allowed values: swipe, mirror
   - swipe: swiping the upper map layer to show the map layer below
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/g.gui.mapswipe.html#__tabbed_2_3) for all details)*

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

The Map Swipe is a wxGUI component which allows the
user to interactively compare two raster maps of the same area by
revealing different parts of the raster maps. It is useful e.g. for
comparing raster maps from different time periods. Map Swipe can be
launched from the menu File -> Map Swipe .

Map Swipe allows you to:

Figure: Pre and post disaster images of the tsunami in Japan in 2011. The upper
MODIS image taken on February 26, 2011, shows the coastline under normal
conditions while the lower MODIS image on March 13, 2011, shows a clear
view of tsunami flooding along the coastline. Water, black and dark blue
in these false-color images, still covers the ground as much as five
kilometers (three miles) from the coast. Source: Earth
Observatory/NASA

---

## See Also

Related tools:

---

## Resources

- [Official g.gui.mapswipe manual](https://grass.osgeo.org/grass-devel/manuals/g.gui.mapswipe.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/g.gui.mapswipe.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
