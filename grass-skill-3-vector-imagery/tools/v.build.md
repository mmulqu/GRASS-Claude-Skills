# v.build

**Category**: vector

## Description

Creates topology for vector map. Optionally also checks for topological errors.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.v_build(map,error=None,option="build",flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`map : str, required`**
   - Name of vector map
   - Used as: input, vector, name

2. **`error : str, optional`**
   - Name for output vector map where erroneous vector features are written to
   - Used as: output, vector, name

3. **`option : str | list[str], required`**
   - Build topology or dump topology or indices to standard output
   - Allowed values: build, dump, sdump, cdump, fdump
   - build: build topology
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/v.build.html#__tabbed_2_3) for all details)*

4. **`flags : str, optional`**
   - Allowed values: e
   - e
   - Extensive checks for topological errors

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

v.build builds support files for GRASS vector maps. These support
files supply topology and category information including spatial index
that are needed by other GRASS modules.

GRASS is generating these support files automatically, only in rare
cases the user has to (re)build them.

Refer to vector data processing in GRASS for more
information on GRASS vector data model.

---

## See Also

Related tools:
- [`v.build.all`](https://grass.osgeo.org/grass-devel/manuals/v.build.all.html)
- [`v.build.polylines`](https://grass.osgeo.org/grass-devel/manuals/v.build.polylines.html)
- [`v.edit`](https://grass.osgeo.org/grass-devel/manuals/v.edit.html)
- [`v.split`](https://grass.osgeo.org/grass-devel/manuals/v.split.html)
- [`v.support`](https://grass.osgeo.org/grass-devel/manuals/v.support.html)

---

## Authors

Dave Gerdes, U.S.Army Construction Engineering Research Laboratory, Michael Higgins, U.S.Army Construction Engineering Research
Laboratory, Radim Blazek, ITC-irst, Trento, Italy

---

## Resources

- [Official v.build manual](https://grass.osgeo.org/grass-devel/manuals/v.build.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/v.build.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
