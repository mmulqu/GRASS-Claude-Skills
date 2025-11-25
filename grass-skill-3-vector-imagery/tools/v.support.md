# v.support

**Category**: vector

## Description

Updates vector map metadata.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.v_support(map,organization=None,date=None,person=None,map_name=None,map_date=None,scale=None,zone=None,threshold=None,comment=None,cmdhist=None,flags=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`map : str, required`**
   - Name of vector map
   - Or data source for direct OGR access
   - Used as: input, vector, name

2. **`organization : str, optional`**
   - Organization where vector map was created
   - Used as: phrase

3. **`date : str, optional`**
   - Date of vector map digitization (e.g., "15 Mar 2007")
   - Used as: datestring

4. **`person : str, optional`**
   - Person who created vector map
   - Used as: phrase

5. **`map_name : str, optional`**
   - Vector map title
   - Used as: phrase

6. **`map_date : str, optional`**
   - Date when the source map was originally produced
   - Used as: datestring

7. **`scale : int, optional`**
   - Vector map scale number (e.g., 24000)

8. **`zone : int, optional`**
   - Vector map projection zone

9. **`threshold : float, optional`**
   - Vector map digitizing threshold number (e.g., 0.5)

10. **`comment : str, optional`**
   - Text to append to the comment line of the map's metadata file
   - Used as: phrase

11. **`cmdhist : str, optional`**
   - Command line to store into vector map history file (used for vector scripts)
   - Used as: command

12. **`flags : str, optional`**
   - Allowed values: r, h
   - r
   - Replace comment instead of appending it
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/v.support.html#__tabbed_2_3) for all details)*

13. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

14. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

15. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 15 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/v.support.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

v.support is used to set/update vector map metadata. While GRASS
typically generates these metadata entries automatically, v.support allows users to manually edit them when necessary.

---

## See Also

Related tools:
- [`v.build`](https://grass.osgeo.org/grass-devel/manuals/v.build.html)
- [`v.info`](https://grass.osgeo.org/grass-devel/manuals/v.info.html)

---

## Resources

- [Official v.support manual](https://grass.osgeo.org/grass-devel/manuals/v.support.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/v.support.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
