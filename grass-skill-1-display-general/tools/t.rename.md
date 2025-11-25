# t.rename

**Category**: temporal

## Description

Renames a space time dataset

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.t_rename(input,output,type="strds",overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str, required`**
   - Name of the input space time dataset
   - Used as: input, stds, name

2. **`output : str, required`**
   - Name of the output space time dataset
   - Used as: output, stds, name

3. **`type : str, optional`**
   - Type of the input space time dataset
   - Used as: name
   - Allowed values: strds, stvds, str3ds

4. **`Default: strds`**

5. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

6. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

7. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

8. **`superquiet : bool, optional`**
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

The t.rename module renames space time datasets of different types
(STRDS, STVDS, STR3DS) and updates the space time dataset register
entries of the registered maps.

---

## See Also

Related tools:
- [`t.create`](https://grass.osgeo.org/grass-devel/manuals/t.create.html)
- [`t.support`](https://grass.osgeo.org/grass-devel/manuals/t.support.html)
- [`t.register`](https://grass.osgeo.org/grass-devel/manuals/t.register.html)

---

## Resources

- [Official t.rename manual](https://grass.osgeo.org/grass-devel/manuals/t.rename.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/t.rename.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
