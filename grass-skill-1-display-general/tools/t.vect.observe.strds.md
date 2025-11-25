# t.vect.observe.strds

**Category**: temporal

## Description

Observes specific locations in a space time raster dataset over a period of time using vector points.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.t_vect_observe_strds(input,strds,output,vector_output,columns,where=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str, required`**
   - Name of input vector map
   - Or data source for direct OGR access
   - Used as: input, vector, name

2. **`strds : str | list[str], required`**
   - Name of the input space time raster datasets
   - Used as: input, strds, name

3. **`output : str, required`**
   - Name of the output space time vector dataset
   - Used as: output, stvds, name

4. **`vector_output : str, required`**
   - Name of the new created vector map that stores the sampled values in different layers
   - Used as: output, vector, name

5. **`columns : str | list[str], required`**
   - Names of the vector columns to be created and to store sampled raster values, one name for each STRDS

6. **`where : str, optional`**
   - WHERE conditions of SQL statement without 'where' keyword
   - Example: income < 1000 and population >= 10000
   - Used as: input, sql_query, sql_query

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

The module t.vect.observe.strds is used to observe specific locations
in a space time raster dataset over a period of time using vector
points. The first input is a vector map layer with vector points. The
second input is one or several space time raster datasets (STRDS) that
should be sampled over time at the vector point positions. The space
time raster dataset will be sampled over its whole temporal extent (from
start to end). A column name must be specified for each input space time
raster dataset.

The result is a new space time vector dataset that contains a single
(new) vector map which links to as many time-stamped attribute tables as
raster map layers are present in the input space time raster dataset.
Hence, for each time step in the space time raster dataset a new
attribute table is created. The GRASS Temporal Framework allows to
time stamp attribute tables that can be linked to a single vector map
layer.

The module v.what.rast is used internally for sampling the time
stamped raster map layers. All sampled values of a single time stamped
raster map layer are written into a new time stamped attribute table.

Use t.vect.db.select to print attribute values of the space time
vector dataset to stdout.

---

## See Also

Related tools:
- [`t.create`](https://grass.osgeo.org/grass-devel/manuals/t.create.html)
- [`t.info`](https://grass.osgeo.org/grass-devel/manuals/t.info.html)
- [`t.vect.db.select`](https://grass.osgeo.org/grass-devel/manuals/t.vect.db.select.html)
- [`t.vect.what.strds`](https://grass.osgeo.org/grass-devel/manuals/t.vect.what.strds.html)

---

## Resources

- [Official t.vect.observe.strds manual](https://grass.osgeo.org/grass-devel/manuals/t.vect.observe.strds.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/t.vect.observe.strds.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
