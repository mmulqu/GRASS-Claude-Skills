# v.to.rast3

**Category**: vector

## Description

Converts a vector map (only points) into a 3D raster map.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.v_to_rast3(input,layer="1",output,column,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str, required`**
   - Name of input vector map
   - Or data source for direct OGR access
   - Used as: input, vector, name

2. **`layer : str, optional`**
   - Layer number or name
   - Vector features can have category values in different layers. This number determines which layer to use. When used with direct OGR access this is the layer name.
   - Used as: input, layer

3. **`output : str, required`**
   - Name for output 3D raster map
   - Used as: output, raster_3d, name

4. **`column : str, required`**
   - Name of attribute column (data type must be numeric)
   - Used as: input, dbcolumn, name

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

v.to.rast3 converts a GRASS 3D vector point map to a GRASS 3D raster
map.

---

## See Also

Related tools:
- [`g.region`](https://grass.osgeo.org/grass-devel/manuals/g.region.html)

---

## Authors

Original s.to.rast3: Jaro Hofierka, Geomodel s.r.o. Updated by Radim Blazek

---

## Resources

- [Official v.to.rast3 manual](https://grass.osgeo.org/grass-devel/manuals/v.to.rast3.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/v.to.rast3.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
