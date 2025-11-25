# v.distance

**Category**: vector

## Description

Finds the nearest element in vector map 'to' for elements in vector map 'from'.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.v_distance(from,from_layer="1",from_type="point,line,area",to,to_layer="1",to_type="point,line,area",output=None,dmax=-1,dmin=-1,upload,column=None,to_column=None,table=None,separator="pipe",format="plain",flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`from : str, required`**
   - Name of existing vector map (from)
   - Or data source for direct OGR access
   - Used as: input, vector, name

2. **`from_layer : str, optional`**
   - Layer number or name (from)
   - Vector features can have category values in different layers. This number determines which layer to use. When used with direct OGR access this is the layer name.
   - Used as: input, layer

3. **`from_type : str | list[str], optional`**
   - Feature type (from)
   - Input feature type
   - Allowed values: point, line, boundary, centroid, area

4. **`to : str, required`**
   - Name of existing vector map (to)
   - Or data source for direct OGR access
   - Used as: input, vector, name

5. **`to_layer : str, optional`**
   - Layer number or name (to)
   - Vector features can have category values in different layers. This number determines which layer to use. When used with direct OGR access this is the layer name.
   - Used as: input, layer

6. **`to_type : str | list[str], optional`**
   - Feature type (to)
   - Input feature type
   - Allowed values: point, line, boundary, centroid, area

7. **`output : str, optional`**
   - Name for output vector map containing lines connecting nearest elements
   - Used as: output, vector, name

8. **`dmax : float, optional`**
   - Maximum distance or -1 for no limit
   - Map units, meters for ll
   - Default: -1

9. **`dmin : float, optional`**
   - Minimum distance or -1 for no limit
   - Map units, meters for ll
   - Default: -1

10. **`upload : str | list[str], required`**
   - Values describing the relation between two nearest features
   - Allowed values: cat, dist, to_x, to_y, to_along, to_angle, to_attr
   - cat: category of the nearest feature
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/v.distance.html#__tabbed_2_3) for all details)*

11. **`column : str | list[str], optional`**
   - Column name(s) where values specified by 'upload' option will be uploaded
   - Used as: input, dbcolumn, name

12. **`to_column : str, optional`**
   - Column name of nearest feature (used with upload=to_attr)
   - Used as: input, dbcolumn, name

13. **`table : str, optional`**
   - Name for new attribute table
   - Used as: dbtable, name

14. **`separator : str, optional`**
   - Field separator for printing output to stdout
   - Special characters: pipe, comma, space, tab, newline
   - Used as: input, separator, character

15. **`format : str, required`**
   - Output format
   - Used as: name
   - Allowed values: plain, json
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/v.distance.html#__tabbed_2_3) for all details)*

16. **`flags : str, optional`**
   - Allowed values: p, a, s
   - p
   - Print output to stdout, don't update attribute table
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/v.distance.html#__tabbed_2_3) for all details)*

17. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

18. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

19. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

20. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 20 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/v.distance.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

v.distance finds the nearest element in vector map ( to ) for
elements in vector map ( from ). Various information about the
vectors' relationships (distance, category, etc.) may be uploaded to the
attribute table attached to the first vector map, or printed to
'stdout'. A new vector map may be created where lines connecting nearest
points on features are written. dmin and/or dmax can be used to
limit the search radius (in lat-long projects to be given in meters
since they are calculated as geodesic distances on a sphere).

For lines to lines, say line A to line B, v.distance calculates the
shortest distance of each vertex in A with each segment (not vertex) in
B. The module then calculates the shortest distance of each vertex in B
to each segment in A. The overall shortest distance of A points to B
segments and B points to A segments is used. Additionally, v.distance checks for intersections. In case of intersections, the first
intersection found is used and the distance set to zero.

For lines to areas, the distance is set to zero if a line is (partially)
inside an area. The first point of the line that is inside the area is
used as common point. The distance is also set to zero if the line
intersects with the outer ring or any of the inner rings (isles), in
which case the fist intersection is used as common point.

For areas to areas, the module checks first for overlap or if one area
is (partially) inside the other area. This is computationally quite
intensive. If the outer rings of the two areas do not overlap, the
distance is calculated as above for lines to lines, treating the outer
rings as two lines. Again, the first point encountered falling into an
area is used as common point, or the first intersection point.

For anything else than points to lines, there can be several common
locations with zero distance, and the common location would then be the
result of an overlay consisting of several points, lines, or areas. v.distance selects in these cases a single point, and does not create
an overlay like v.overlay . In this implementation, any
shared point is as good as any other. Calculating an intersection is
costlier than to check if a vertex is inside a polygon. For example, if
a vertex of the boundary of the 'to' area is inside the 'from' area, it
is a common location. For speed reasons, the distance is then set to
zero and no further tests are done.

---

## See Also

Related tools:
- [`r.distance`](https://grass.osgeo.org/grass-devel/manuals/r.distance.html)
- [`v.db.addcolumn`](https://grass.osgeo.org/grass-devel/manuals/v.db.addcolumn.html)
- [`v.what.vect`](https://grass.osgeo.org/grass-devel/manuals/v.what.vect.html)

---

## Authors

Janne Soimasuo 1994, University of Joensuu, Faculty of Forestry,
Finland Cmd line coordinates support: Markus Neteler, ITC-irst, Trento, Italy Updated for 5.1: Radim Blazek, ITC-irst, Trento, Italy Matrix-like output by Martin Landa, FBK-irst, Trento, Italy Improved processing speed: Markus Metz Distance from any feature to any feature: Markus Metz New table without the -p flag: Huidae Cho Make linear matrix the default
for all outputs: Moritz Lennert

---

## Resources

- [Official v.distance manual](https://grass.osgeo.org/grass-devel/manuals/v.distance.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/v.distance.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
