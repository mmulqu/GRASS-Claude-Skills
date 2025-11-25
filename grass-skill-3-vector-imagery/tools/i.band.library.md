# i.band.library

**Category**: imagery

## Description

Prints available semantic label information used for multispectral data.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.i_band_library(pattern=None,operation="print",flags=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`pattern : str, optional`**
   - Semantic label search pattern (examples: L, S2, .*_2, S2_1)

2. **`operation : str, optional`**
   - Operation to be performed
   - Allowed values: print
   - Default: print

3. **`flags : str, optional`**
   - Allowed values: e
   - e
   - Print extended metadata information

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

i.band.library prints available band information of multispectral data
defined by GRASS. The following multispectral sensors are supported
by default (other band reference registry files can be added, see
below):

Generic multispectral system:

Landsat-5:

Landsat-7:

Landsat-8:

Sentinel-2:

Band references to be printed can be filtered by a search pattern (or
fully defined band reference identifier) which can be specified by pattern option. For pattern syntax see Python regular expression
operations documentation. By default, i.band.library prints all available band
references.

Extended metadata (central wavelength, spatial resolution, etc.) is
printed only when the -e flag is given.

---

## See Also

Related tools:
- [`r.semantic.label`](https://grass.osgeo.org/grass-devel/manuals/r.semantic.label.html)
- [`r.info`](https://grass.osgeo.org/grass-devel/manuals/r.info.html)

---

## Authors

Martin Landa Development sponsored by mundialis GmbH & Co.
KG (for the openEO EU H2020 grant 776242)

---

## Resources

- [Official i.band.library manual](https://grass.osgeo.org/grass-devel/manuals/i.band.library.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/i.band.library.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
