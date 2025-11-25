# v.what

**Category**: vector

## Description

Queries a vector map at given locations.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.v_what(map,layer="-1",type="point,line,area,face",coordinates,distance=0,columns=None,format=None,flags=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`map : str | list[str], required`**
   - Name of vector map(s)
   - Used as: input, vector, name

2. **`layer : str | list[str], optional`**
   - Layer number or name ('-1' for all layers)
   - A single vector map can be connected to multiple database tables. This number determines which table to use. When used with direct OGR access this is the layer name.
   - Used as: input, layer

3. **`type : str | list[str], optional`**
   - Input feature type
   - Allowed values: point, line, boundary, centroid, area, face, kernel
   - Default: point,line,area,face

4. **`coordinates : tuple[float, float] | list[float] | str, required`**
   - Coordinates for query
   - '-' for standard input
   - Used as: input, coords, east,north

5. **`distance : float, optional`**
   - Query threshold distance
   - Default: 0

6. **`columns : str | list[str], optional`**
   - Name of attribute column(s)
   - Default: all columns
   - Used as: input, dbcolumn, name

7. **`format : str, optional`**
   - Output format
   - Used as: name
   - Allowed values: plain, shell, json
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/v.what.html#__tabbed_2_3) for all details)*

8. **`flags : str, optional`**
   - Allowed values: a, i, d, g, j, m
   - a
   - Print attribute information
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/v.what.html#__tabbed_2_3) for all details)*

9. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

10. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

11. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 11 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/v.what.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

v.what outputs the features associated with
user-specified location(s) in user-specified vector map(s).
The tool operates on features which are vector geometry objects,
such as point or area. The result is a list of these features
along with their associated categories for the layer specified by layer .
If there are no categories for the specified layer, the feature
is not included in the result. With layer=-1 (all layers), all features
are included in the result regardless of their categories.

By default, the closest feature is returned for each coordinate and each
vector map if the feature fulfills the geometry query and layer selection
criteria. With the -m flag, all matching features are returned, not just
the closest one.

If an attribute database connection is defined for a given layer
and the -a flag is specified, attributes from the associated attribute table
will be returned for each category associated with the feature.

The tool operates on features defined as vector geometry objects as opposed
to features defined by categories. Consequently, the output is organized
by geometry IDs, to which possible categories and attributes are attached.
If multiple geometries have the same category, the same set of attributes
is repeated for each geometry.

The output also includes the coordinates used in the query,
the vector map name, and the mapset. For vector lines,
the length is returned. The -d flag returns internal topological
information.

With format="json" , a list of matching features is returned.
Each feature includes the geometry ID ( id ), geometry type ( type ),
vector map name ( map and mapset ), and the relevant part of the spatial
query ( coordinates ).
If the feature has associated categories for the given layer ,
they are included under data in a list of items with layer and category values.
With -a , data will also include attributes for each category .

A feature is not included in the result if there are no categories
for the specified layer. For layer=-1 , all features
are included in the result and each feature's data will contain all
associated categories in all layers.

With the -m flag, each list item contains coordinates, a vector map name,
and a list of matching features under the features key.
In other words, rather than being organized by feature, the list now contains
lists of features nested under each combination of coordinate pair and vector map.

---

## See Also

Related tools:
- [`d.what.rast`](https://grass.osgeo.org/grass-devel/manuals/d.what.rast.html)
- [`d.what.vect`](https://grass.osgeo.org/grass-devel/manuals/d.what.vect.html)
- [`v.rast.stats`](https://grass.osgeo.org/grass-devel/manuals/v.rast.stats.html)
- [`v.vect.stats`](https://grass.osgeo.org/grass-devel/manuals/v.vect.stats.html)
- [`v.what.rast`](https://grass.osgeo.org/grass-devel/manuals/v.what.rast.html)
- [`v.what.rast3`](https://grass.osgeo.org/grass-devel/manuals/v.what.rast3.html)
- [`v.what.vect`](https://grass.osgeo.org/grass-devel/manuals/v.what.vect.html)
- [`r.what`](https://grass.osgeo.org/grass-devel/manuals/r.what.html)

---

## Resources

- [Official v.what manual](https://grass.osgeo.org/grass-devel/manuals/v.what.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/v.what.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
