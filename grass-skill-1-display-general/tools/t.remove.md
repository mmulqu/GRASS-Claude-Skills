# t.remove

**Category**: temporal

## Description

Removes space time datasets from temporal database.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.t_remove(inputs=None,type="strds",file=None,flags=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`inputs : str | list[str], optional`**
   - Name of the input space time datasets
   - Used as: input, stds, name

2. **`type : str, optional`**
   - Type of the space time dataset, default is strds
   - Allowed values: strds,  str3ds,  stvds

3. **`Default: strds`**

4. **`file : str | io.StringIO, optional`**
   - Input file with dataset names, one per line
   - Used as: input, file, name

5. **`flags : str, optional`**
   - Allowed values: r, f, d
   - r
   - Remove stds and unregister maps from temporal database
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/t.remove.html#__tabbed_2_3) for all details)*

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

The module t.remove removes space time datasets (STRDS, STR3DS, STVDS)
from the temporal database. In other words, by default it deletes the
relevant database entries. It can also unregister maps from temporal
database using the recursive mode -r (recursive).

Optionally, also the raster, 3D raster and vector maps of the space time
datasets can be removed from the current mapset using the -d (delete) flag. All removals only work if -f (force) flag is used.

---

## See Also

Related tools:
- [`t.create`](https://grass.osgeo.org/grass-devel/manuals/t.create.html)
- [`t.info`](https://grass.osgeo.org/grass-devel/manuals/t.info.html)
- [`t.register`](https://grass.osgeo.org/grass-devel/manuals/t.register.html)

---

## Resources

- [Official t.remove manual](https://grass.osgeo.org/grass-devel/manuals/t.remove.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/t.remove.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
