# v.category

**Category**: vector

## Description

Attaches, deletes or reports vector categories to/from/of map geometry.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.v_category(input,layer="1",type="point,line,centroid,face",ids=None,output=None,option,cat=1,step=1,format="plain",separator=None,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str, required`**
   - Name of input vector map
   - Or data source for direct OGR access
   - Used as: input, vector, name

2. **`layer : str | list[str], optional`**
   - Layer number or name
   - Vector features can have category values in different layers. This number determines which layer to use. When used with direct OGR access this is the layer name.
   - Used as: input, layer

3. **`type : str | list[str], optional`**
   - Input feature type
   - Allowed values: point, line, boundary, centroid, area, face, kernel
   - Default: point,line,centroid,face

4. **`ids : str, optional`**
   - Feature ids (by default all features are processed)
   - Example: 1,3,7-9,13
   - Used as: range

5. **`output : str, optional`**
   - Name for output vector map
   - Used as: output, vector, name

6. **`option : str, required`**
   - Action to be done
   - Allowed values: add, del, chlayer, sum, report, print, layers, transfer
   - add: add a category to features without category in the given layer
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/v.category.html#__tabbed_2_3) for all details)*

7. **`cat : int, optional`**
   - Category value
   - Used as: input, cats
   - Default: 1

8. **`step : int, optional`**
   - Category increment
   - Default: 1

9. **`format : str, required`**
   - Output format
   - Used as: name
   - Allowed values: plain, csv, json
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/v.category.html#__tabbed_2_3) for all details)*

10. **`separator : str, optional`**
   - Field separator
   - Special characters: pipe, comma, space, tab, newline
   - Used as: input, separator, character

11. **`flags : str, optional`**
   - Allowed values: g, t
   - g
   - CSV style output, currently only for report [deprecated]
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/v.category.html#__tabbed_2_3) for all details)*

12. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

13. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

14. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

15. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 15 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/v.category.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

v.category attaches, copies, deletes or reports categories to/from/of
vector geometry objects. Further on, v.category adds a number given by
the cat option to categories of the selected layer. These categories
(IDs) are used to assign IDs or to group geometry objects into
categories (several different geometry objects share the same category).
These categories are also used to link geometry object(s) to attribute
records (from an attribute table linked to vector map).

---

## See Also

Related tools:
- [`v.centroids`](https://grass.osgeo.org/grass-devel/manuals/v.centroids.html)
- [`v.db.connect`](https://grass.osgeo.org/grass-devel/manuals/v.db.connect.html)
- [`v.edit`](https://grass.osgeo.org/grass-devel/manuals/v.edit.html)
- [`v.to.db`](https://grass.osgeo.org/grass-devel/manuals/v.to.db.html)

---

## Resources

- [Official v.category manual](https://grass.osgeo.org/grass-devel/manuals/v.category.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/v.category.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
