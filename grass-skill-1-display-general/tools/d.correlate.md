# d.correlate

**Category**: display

## Description

Prints a graph of the correlation between raster maps (in pairs).

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.d_correlate(map,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`map : str | list[str], required`**
   - Name of raster map(s)
   - Used as: input, raster, name

2. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

3. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

4. **`superquiet : bool, optional`**
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

d.correlate displays graphically the results of a r.stats analysis
run on two raster map layers. This module highlights the correlation (or
lack of it) among data layers (scattergram).

The results are displayed in the active display frame on the user's
graphics monitor. d.correlate erases the active frame before
displaying results. If no graphics monitor is open, a file map.png is
generated in the current directory.

---

## See Also

Related tools:
- [`d.text`](https://grass.osgeo.org/grass-devel/manuals/d.text.html)
- [`d.graph`](https://grass.osgeo.org/grass-devel/manuals/d.graph.html)
- [`r.coin`](https://grass.osgeo.org/grass-devel/manuals/r.coin.html)
- [`r.regression.line`](https://grass.osgeo.org/grass-devel/manuals/r.regression.line.html)
- [`r.stats`](https://grass.osgeo.org/grass-devel/manuals/r.stats.html)

---

## Authors

Michael Shapiro, U.S.Army Construction Engineering Research
Laboratory
Rewritten to GRASS 6 (from csh to sh) by Markus Neteler; from sh to
Python by Glynn Clements

---

## Resources

- [Official d.correlate manual](https://grass.osgeo.org/grass-devel/manuals/d.correlate.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/d.correlate.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
