# t.unregister

**Category**: temporal

## Description

Unregisters raster, vector and raster3d maps from the temporal database or a specific space time dataset.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.t_unregister(input=None,file=None,type="raster",maps=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str, optional`**
   - Name of the input space time dataset
   - Used as: input, stds, name

2. **`file : str | io.StringIO, optional`**
   - Input file with map names, one per line
   - Used as: input, file, name

3. **`type : str, optional`**
   - Type of the input map
   - Used as: name
   - Allowed values: raster, vector, raster_3d

4. **`maps : str | list[str], optional`**
   - Name(s) of existing raster, vector or raster3d map(s) to unregister
   - Used as: input, map, name

5. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

6. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

7. **`superquiet : bool, optional`**
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

The t.unregister module is designed to unregister raster, 3D raster
and vector map layers from space time datasets and the temporal
database.

Map layer that should be unregistered from the temporal database can be
specified as a list of comma separated map names or using a text file,
that contains one map layer name per line. By default the map type that
should be unregistered is set to raster. The option type must be used
to specify 3D raster or vector map layer types.

---

## See Also

Related tools:
- [`t.create`](https://grass.osgeo.org/grass-devel/manuals/t.create.html)
- [`t.info`](https://grass.osgeo.org/grass-devel/manuals/t.info.html)

---

## Resources

- [Official t.unregister manual](https://grass.osgeo.org/grass-devel/manuals/t.unregister.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/t.unregister.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
