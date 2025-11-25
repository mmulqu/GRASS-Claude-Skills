# v.to.rast

**Category**: vector

## Description

Converts (rasterize) a vector map into a raster map.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.v_to_rast(input,layer="1",type="point,line,area",cats=None,where=None,output,use,attribute_column=None,rgb_column=None,label_column=None,value=1,memory=300,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
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

3. **`type : str | list[str], optional`**
   - Input feature type
   - Allowed values: point, line, boundary, centroid, area
   - Default: point,line,area

4. **`cats : str, optional`**
   - Category values
   - Example: 1,3,7-9,13
   - Used as: input, cats, range

5. **`where : str, optional`**
   - WHERE conditions of SQL statement without 'where' keyword
   - Example: income < 1000 and population >= 10000
   - Used as: input, sql_query, sql_query

6. **`output : str | type(np.ndarray) | type(np.array) | type(gs.array.array), required`**
   - Name for output raster map
   - Used as: output, raster, name

7. **`use : str, required`**
   - Source of raster values
   - Allowed values: attr, cat, value, z, dir
   - attr: read values from attribute table
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/v.to.rast.html#__tabbed_2_3) for all details)*

8. **`attribute_column : str, optional`**
   - Name of column for 'attr' parameter (data type must be numeric)
   - Used as: input, dbcolumn, name

9. **`rgb_column : str, optional`**
   - Name of color definition column (with RRR:GGG:BBB entries)
   - Used as: input, dbcolumn, name

10. **`label_column : str, optional`**
   - Name of column used as raster category labels
   - Used as: input, dbcolumn, name

11. **`value : float, optional`**
   - Raster value (for use=value)
   - Default: 1

12. **`memory : int, optional`**
   - Maximum memory to be used (in MB)
   - Cache size for raster rows
   - Used as: memory in MB

13. **`flags : str, optional`**
   - Allowed values: d
   - d
   - Create densified lines (default: thin lines)

14. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

15. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

16. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

17. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 17 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/v.to.rast.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | np.ndarray | tuple[np.ndarray] | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned. If an array type (e.g., np.ndarray) is used for one of the raster outputs, the result will be an array and will have the shape corresponding to the computational region. If an array type is used for more than one raster output, the result will be a tuple of arrays.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

v.to.rast transforms GRASS vector map layers into GRASS raster map
layer format. Optionally, attributes can be converted to raster category
labels.

---

## See Also

Related tools:
- [`db.describe`](https://grass.osgeo.org/grass-devel/manuals/db.describe.html)
- [`v.category`](https://grass.osgeo.org/grass-devel/manuals/v.category.html)

---

## Authors

Original code: Michael Shapiro, U.S. Army Construction Engineering
Research Laboratory GRASS 6.0 updates: Radim Blazek, ITC-irst, Trento, Italy Stream directions: Jaro Hofierka and Helena Mitasova GRASS 6.3 code cleanup and label support: Brad Douglas

---

## Resources

- [Official v.to.rast manual](https://grass.osgeo.org/grass-devel/manuals/v.to.rast.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/v.to.rast.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
