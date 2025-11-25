# g.rename

**Category**: general

## Description

Renames data base element files in the user's current mapset.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.g_rename(raster=None,raster_3d=None,vector=None,label=None,region=None,group=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`raster : tuple[str | np.ndarray, str | np.ndarray] | list[str | np.ndarray] | str, optional`**
   - raster map(s) to be renamed
   - Used as: input, raster, from,to

2. **`raster_3d : tuple[str, str] | list[str] | str, optional`**
   - 3D raster map(s) to be renamed
   - Used as: input, 3D raster, from,to

3. **`vector : tuple[str, str] | list[str] | str, optional`**
   - vector map(s) to be renamed
   - Used as: input, vector, from,to

4. **`label : tuple[str, str] | list[str] | str, optional`**
   - paint label file(s) to be renamed
   - Used as: input, label, from,to

5. **`region : tuple[str, str] | list[str] | str, optional`**
   - region definition(s) to be renamed
   - Used as: input, region definition, from,to

6. **`group : tuple[str, str] | list[str] | str, optional`**
   - imagery group(s) to be renamed
   - Used as: input, imagery group, from,to

7. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

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

g.rename allows the user to rename data base element files in the
user's current mapset. The user can specify all necessary information to g.rename on the command line, by specifying: the type of data base
element to be renamed (one or more of: raster , raster_3d , vector , icon , labels , region , and group ); the
specific file element in the current mapset to be renamed ( old ); and
the new name to be assigned to this file element ( new ) in the current
mapset. The file element old is then renamed to new .

Users can also simply type g.rename --help without arguments on the
command line, to receive a menu of existing data base element types and
files from which to choose for possible renaming:

---

## See Also

Related tools:
- [`g.copy`](https://grass.osgeo.org/grass-devel/manuals/g.copy.html)
- [`g.list`](https://grass.osgeo.org/grass-devel/manuals/g.list.html)
- [`g.remove`](https://grass.osgeo.org/grass-devel/manuals/g.remove.html)

---

## Resources

- [Official g.rename manual](https://grass.osgeo.org/grass-devel/manuals/g.rename.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/g.rename.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
