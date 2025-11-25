# g.copy

**Category**: general

## Description

Creates copies of maps and other elements Copies available data files in the current mapset search path to the user's current mapset.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.g_copy(raster=None,raster_3d=None,vector=None,label=None,region=None,group=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`raster : tuple[str | np.ndarray, str | np.ndarray] | list[str | np.ndarray] | str, optional`**
   - raster map(s) to be copied
   - Used as: input, raster, from,to

2. **`raster_3d : tuple[str, str] | list[str] | str, optional`**
   - 3D raster map(s) to be copied
   - Used as: input, 3D raster, from,to

3. **`vector : tuple[str, str] | list[str] | str, optional`**
   - vector map(s) to be copied
   - Used as: input, vector, from,to

4. **`label : tuple[str, str] | list[str] | str, optional`**
   - paint label file(s) to be copied
   - Used as: input, label, from,to

5. **`region : tuple[str, str] | list[str] | str, optional`**
   - region definition(s) to be copied
   - Used as: input, region definition, from,to

6. **`group : tuple[str, str] | list[str] | str, optional`**
   - imagery group(s) to be copied
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

The g.copy module creates a copy of existing raster maps, vector maps,
or other elements. The copy is always created in the current mapset. The
source data can be in the current mapset, in an explicitly specified
mapset, or in a mapset which is in the current mapset search path
(typically the PERMANENT mapset).

The maps and other elements to copy are specified in pairs from , to according to their types. Although typically only one
map is copied in one module call, multiple pairs can be provided for
each type and multiple types can be provided at the same time.

A user may access data stored under the other mapsets listed in their
mapset search path. However, the user may only modify data stored under
their own current mapset. g.copy allows the user to copy existing data
files from other mapsets to the user's current mapset
( g.mapset -p ). The files to be copied must exist in the user's current
mapset search path ( g.mapsets -p ) and project; output is sent to the
relevant data element directory(ies) under the user's current mapset.

Errors typically occur when a map or other element does not exist, from and to are the same, to element already exists and
overwriting (e.g., by --overwrite ) is not enabled, or the to element has an illegal name. When only one map or other element is
requested to be copied and the copying is not possible or fails, an
error is reported.

If multiple maps or other elements are copied in one command, g.copy attempts to copy as much as possible even when problems occur with one
of the elements. In that case, copying of the element causing problems
is skipped, and g.copy proceeds with copying the remaining elements.
If nothing can be copied or an error occurred during one of the copy
operations, an error message is reported after other possible copy
operations were performed.

---

## See Also

Related tools:
- [`g.access`](https://grass.osgeo.org/grass-devel/manuals/g.access.html)
- [`g.list`](https://grass.osgeo.org/grass-devel/manuals/g.list.html)
- [`g.mapsets`](https://grass.osgeo.org/grass-devel/manuals/g.mapsets.html)
- [`g.remove`](https://grass.osgeo.org/grass-devel/manuals/g.remove.html)
- [`g.rename`](https://grass.osgeo.org/grass-devel/manuals/g.rename.html)

---

## Resources

- [Official g.copy manual](https://grass.osgeo.org/grass-devel/manuals/g.copy.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/g.copy.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
