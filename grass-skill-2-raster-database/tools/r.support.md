# r.support

**Category**: raster

## Description

Allows creation and/or modification of raster map layer support files.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_support(map,title=None,history=None,units=None,vdatum=None,source1=None,source2=None,description=None,raster=None,loadhistory=None,savehistory=None,semantic_label=None,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`map : str | np.ndarray, required`**
   - Name of raster map
   - Used as: input, raster, name

2. **`title : str, optional`**
   - Title for resultant raster map
   - Used as: phrase

3. **`history : str, optional`**
   - Text to append to the next line of the map's metadata file
   - Used as: phrase

4. **`units : str, optional`**
   - Text to use for map data units

5. **`vdatum : str, optional`**
   - Text to use for map vertical datum

6. **`source1 : str, optional`**
   - Text to use for data source, line 1
   - Used as: phrase

7. **`source2 : str, optional`**
   - Text to use for data source, line 2
   - Used as: phrase

8. **`description : str, optional`**
   - Text to use for data description or keyword(s)
   - Used as: phrase

9. **`raster : str | np.ndarray, optional`**
   - Raster map from which to copy category table
   - Used as: input, raster

10. **`loadhistory : str | io.StringIO, optional`**
   - Text file from which to load history
   - Used as: input, file, name

11. **`savehistory : str, optional`**
   - Text file in which to save history
   - Used as: output, file, name

12. **`semantic_label : str, optional`**
   - Semantic label e.g. S2_8A
   - Used as: phrase

13. **`flags : str, optional`**
   - Allowed values: b, s, n, d
   - b
   - Delete the semantic label
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/r.support.html#__tabbed_2_3) for all details)*

14. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

15. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

16. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

17. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 17 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/r.support.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

r.support allows the user to create and/or edit raster map support
information. Editing of raster map color tables, category labels,
header, history, semantic label elements and title is supported.
Category labels can also be copied from another raster map.

Raster semantic label concept is similar to dimension name in other GIS
and remote sensing applications. Most common usage will be assigning a
remote sensing platform sensor band identifier to the raster map
metadata, although any identifier is supported (see i.band.library ). Raster semantic label is suggested
to work with imagery classification tools.

---

## See Also

Related tools:
- [`i.band.library`](https://grass.osgeo.org/grass-devel/manuals/i.band.library.html)
- [`r.category`](https://grass.osgeo.org/grass-devel/manuals/r.category.html)
- [`r.describe`](https://grass.osgeo.org/grass-devel/manuals/r.describe.html)
- [`r.info`](https://grass.osgeo.org/grass-devel/manuals/r.info.html)
- [`r.null`](https://grass.osgeo.org/grass-devel/manuals/r.null.html)
- [`r.region`](https://grass.osgeo.org/grass-devel/manuals/r.region.html)
- [`r.report`](https://grass.osgeo.org/grass-devel/manuals/r.report.html)
- [`r.semantic.label`](https://grass.osgeo.org/grass-devel/manuals/r.semantic.label.html)
- [`r.timestamp`](https://grass.osgeo.org/grass-devel/manuals/r.timestamp.html)

---

## Authors

Micharl Shapiro, CERL: Original author Brad Douglas : GRASS 6 Port M. Hamish Bowman: command line enhancements Markus Neteler: category copy from other map Maris Nartiss: semantic label management

---

## Resources

- [Official r.support manual](https://grass.osgeo.org/grass-devel/manuals/r.support.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.support.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
