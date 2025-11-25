# i.signatures

**Category**: imagery

## Description

Manage imagery classification signature files

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.i_signatures(type=None,format="plain",mapset=None,remove=None,rename=None,copy=None,flags=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`type : str, optional`**
   - Type of signature file
   - Used as: input, sigtype, name
   - Allowed values: sig, sigset, libsvm

2. **`format : str, required`**
   - Output format
   - Used as: name
   - Allowed values: plain, json
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/i.signatures.html#__tabbed_2_3) for all details)*

3. **`mapset : str | list[str], optional`**
   - Name of mapset to list
   - Default: current search path
   - Used as: input, mapset, name

4. **`remove : str | list[str], optional`**
   - Name of file(s) to remove
   - Used as: input, sigfile, name

5. **`rename : list[tuple[str, str]] | tuple[str, str] | list[str] | str, optional`**
   - Name of file to rename
   - Used as: input, sigfile, from,to

6. **`copy : list[tuple[str, str]] | tuple[str, str] | list[str] | str, optional`**
   - Name of file to copy
   - Used as: input, sigfile, from,to

7. **`flags : str, optional`**
   - Allowed values: p
   - p
   - Print signature files

8. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

9. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

10. **`superquiet : bool, optional`**
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

i.signatures module allows managing signature files:

---

## See Also

Related tools:
- [`i.gensig`](https://grass.osgeo.org/grass-devel/manuals/i.gensig.html)
- [`i.gensigset`](https://grass.osgeo.org/grass-devel/manuals/i.gensigset.html)
- [`i.svm.predict`](https://grass.osgeo.org/grass-devel/manuals/i.svm.predict.html)

---

## Resources

- [Official i.signatures manual](https://grass.osgeo.org/grass-devel/manuals/i.signatures.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/i.signatures.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
