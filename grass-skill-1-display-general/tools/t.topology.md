# t.topology

**Category**: temporal

## Description

Lists temporal topology of a space time dataset.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.t_topology(input,type="strds",where=None,flags=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str, required`**
   - Name of the input space time dataset
   - Used as: input, stds, name

2. **`type : str, optional`**
   - Type of the input space time dataset
   - Used as: name
   - Allowed values: strds, stvds, str3ds

3. **`Default: strds`**

4. **`where : str, optional`**
   - WHERE conditions of SQL statement without 'where' keyword used in the temporal GIS framework
   - Example: start_time > '2001-01-01 12:30:00'
   - Used as: sql_query

5. **`flags : str, optional`**
   - Allowed values: m, s
   - m
   - Print temporal topological relationships and exit
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/t.topology.html#__tabbed_2_3) for all details)*

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

The module t.topology lists temporal relations of the maps in a space
time dataset.

---

## See Also

Related tools:
- [`t.create`](https://grass.osgeo.org/grass-devel/manuals/t.create.html)
- [`t.info`](https://grass.osgeo.org/grass-devel/manuals/t.info.html)

---

## Resources

- [Official t.topology manual](https://grass.osgeo.org/grass-devel/manuals/t.topology.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/t.topology.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
