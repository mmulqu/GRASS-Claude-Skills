# g.remove

**Category**: general

## Description

Removes data base element files from the user's current mapset using the search pattern.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.g_remove(type,name=None,ignore=None,pattern=None,exclude=None,flags=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`type : str | list[str], required`**
   - Data type(s)
   - Used as: datatype
   - Allowed values: raster, raster_3d, vector, label, region, group, all
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/g.remove.html#__tabbed_2_3) for all details)*

2. **`name : str | list[str], optional`**
   - Name of file(s) to remove
   - Used as: input, element

3. **`ignore : str | list[str], optional`**
   - Name of file(s) to ignore (default: none)
   - Used as: input, element

4. **`pattern : str, optional`**
   - File name search pattern

5. **`exclude : str, optional`**
   - File name exclusion pattern (default: none)

6. **`flags : str, optional`**
   - Allowed values: i, r, e, f, b
   - i
   - Ignore case
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/g.remove.html#__tabbed_2_3) for all details)*

7. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

8. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

9. **`superquiet : bool, optional`**
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

g.remove removes data files matching a pattern given by wildcards or
POSIX Extended Regular Expressions. If the -f force flag is not
given then nothing is removed, instead the list of selected file names
is printed to stdout as a preview of the files to be deleted.

---

## Resources

- [Official g.remove manual](https://grass.osgeo.org/grass-devel/manuals/g.remove.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/g.remove.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
