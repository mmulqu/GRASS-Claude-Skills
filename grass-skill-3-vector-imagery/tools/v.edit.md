# v.edit

**Category**: vector

## Description

Edits a vector map, allows adding, deleting and modifying selected vector features.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.v_edit(map,layer="1",type="point,line,boundary,centroid",tool,input=None,move=None,threshold=-1,0,0,ids=None,cats=None,coords=None,bbox=None,polygon=None,where=None,query=None,bgmap=None,snap="no",zbulk=None,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`map : str, required`**
   - Name of vector map to edit
   - Or data source for direct OGR access
   - Used as: input, vector, name

2. **`layer : str, optional`**
   - Layer number or name
   - Vector features can have category values in different layers. This number determines which layer to use. When used with direct OGR access this is the layer name.
   - Used as: input, layer

3. **`type : str | list[str], optional`**
   - Input feature type
   - Allowed values: point, line, boundary, centroid
   - Default: point,line,boundary,centroid

4. **`tool : str, required`**
   - Tool
   - Allowed values: create, add, delete, copy, move, flip, catadd, catdel, merge, break, snap, connect, extend, extendstart, extendend, chtype, vertexadd, vertexdel, vertexmove, areadel, zbulk, select
   - create: Create new (empty) vector map
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/v.edit.html#__tabbed_2_3) for all details)*

5. **`input : str | io.StringIO, optional`**
   - Name of file containing data in GRASS ASCII vector format
   - '-' for standard input
   - Used as: input, file, name

6. **`move : tuple[float, float, float] | list[float] | str, optional`**
   - Difference in x,y,z direction for moving feature or vertex
   - Used as: x,y,z

7. **`threshold : float | list[float] | str, optional`**
   - Threshold distance (coords,snap,query)
   - '-1' for threshold based on the current resolution settings
   - Default: -1,0,0

8. **`ids : str, optional`**
   - Feature ids
   - Example: 1,3,7-9,13
   - Used as: range

9. **`cats : str, optional`**
   - Category values
   - Example: 1,3,7-9,13
   - Used as: input, cats, range

10. **`coords : list[tuple[float, float]] | tuple[float, float] | list[float] | str, optional`**
   - List of point coordinates
   - Used as: x,y

11. **`bbox : tuple[float, float, float, float] | list[float] | str, optional`**
   - Bounding box for selecting features
   - Used as: x1,y1,x2,y2

12. **`polygon : list[tuple[float, float]] | tuple[float, float] | list[float] | str, optional`**
   - Polygon for selecting features
   - Used as: x,y

13. **`where : str, optional`**
   - WHERE conditions of SQL statement without 'where' keyword
   - Example: income < 1000 and population >= 10000
   - Used as: input, sql_query, sql_query

14. **`query : str, optional`**
   - Query tool
   - For 'shorter' use negative threshold value, positive value for 'longer'
   - Allowed values: length, dangle
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/v.edit.html#__tabbed_2_3) for all details)*

15. **`bgmap : str | list[str], optional`**
   - Name of background vector map(s)
   - Used as: input, vector, name

16. **`snap : str, optional`**
   - Snap added or modified features in the given threshold to the nearest existing feature
   - Allowed values: no, node, vertex
   - no: Not apply snapping
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/v.edit.html#__tabbed_2_3) for all details)*

17. **`zbulk : tuple[float, float] | list[float] | str, optional`**
   - Starting value and step for z bulk-labeling
   - Pair: value,step (e.g. 1100,10)
   - Used as: value,step

18. **`flags : str, optional`**
   - Allowed values: r, c, n, b, 1, p
   - r
   - Reverse selection
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/v.edit.html#__tabbed_2_3) for all details)*

19. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

20. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

21. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

22. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 22 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/v.edit.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

The module v.edit allows the user to edit a vector map via command
line interface.

v.edit supports only "simple" vector features: points, centroids,
lines and boundaries. Currently, only 2D vector features (except of tool=zbulk ) are supported.

Provides editing features' geometry. Attribute data connected to the
vector map are not modified at all.

Vector features can be selected either by internal id , category
number cats , coordinates coords , bounding box bbox , polygon , where statement (attribute data) or by query .
Selecting features by coordinates is affected by the current 2D
resolution or by the threshold distance given by threshold . The
options are orthogonal , i.e. can be used in various combinations. For
example:

selects all features (and prints their id's to standard output) covered
by two bounding boxes (center at 599505,4921010 and
603389.0625,4918292.1875, size 2*10000) with attribute label='interstate' .

---

## See Also

Related tools:
- [`v.in.ascii`](https://grass.osgeo.org/grass-devel/manuals/v.in.ascii.html)
- [`v.info`](https://grass.osgeo.org/grass-devel/manuals/v.info.html)
- [`v.build`](https://grass.osgeo.org/grass-devel/manuals/v.build.html)
- [`v.build.polylines`](https://grass.osgeo.org/grass-devel/manuals/v.build.polylines.html)
- [`v.clean`](https://grass.osgeo.org/grass-devel/manuals/v.clean.html)
- [`v.extrude`](https://grass.osgeo.org/grass-devel/manuals/v.extrude.html)
- [`v.split`](https://grass.osgeo.org/grass-devel/manuals/v.split.html)

---

## Authors

Original author: Wolf Bergenheim - independent developer Initial updates: Jachym Cepicky, Mendel University of Agriculture and
Forestry in Brno, Czech Republic Major update by Martin Landa, FBK-irst (formerly ITC-irst), Trento,
Italy Extend tools by Huidae Cho

---

## Resources

- [Official v.edit manual](https://grass.osgeo.org/grass-devel/manuals/v.edit.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/v.edit.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
