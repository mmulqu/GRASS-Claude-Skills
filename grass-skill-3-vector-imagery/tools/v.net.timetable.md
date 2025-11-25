# v.net.timetable

**Category**: vector

## Description

Finds shortest path using timetables.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.v_net_timetable(input,layer="1",output,arc_layer="1",node_layer="2",arc_column=None,arc_backward_column=None,node_column=None,walk_layer="-1",route_id="route_id",stop_time="stop_time",to_stop="to_stop",walk_length="length",overwrite=None,verbose=None,quiet=None,superquiet=None)
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
   - Name for output vector map
   - Used as: output, vector, name

4. **`arc_layer : str, optional`**
   - Arc layer
   - Vector features can have category values in different layers. This number determines which layer to use. When used with direct OGR access this is the layer name.
   - Used as: input, layer

5. **`node_layer : str, optional`**
   - Node layer
   - Vector features can have category values in different layers. This number determines which layer to use. When used with direct OGR access this is the layer name.
   - Used as: input, layer

6. **`arc_column : str, optional`**
   - Arc forward/both direction(s) cost column (number)

7. **`arc_backward_column : str, optional`**
   - Arc backward direction cost column (number)

8. **`node_column : str, optional`**
   - Node cost column (number)

9. **`walk_layer : str, optional`**
   - Layer number or name with walking connections or -1
   - A single vector map can be connected to multiple database tables. This number determines which table to use. When used with direct OGR access this is the layer name.
   - Used as: input, layer

10. **`route_id : str, required`**
   - Name of column with route ids
   - Used as: input, dbcolumn, name
   - Default: route_id

11. **`stop_time : str, required`**
   - Name of column with stop timestamps
   - Used as: input, dbcolumn, name
   - Default: stop_time

12. **`to_stop : str, required`**
   - Name of column with stop ids
   - Used as: input, dbcolumn, name
   - Default: to_stop

13. **`walk_length : str, required`**
   - Name of column with walk lengths
   - Used as: input, dbcolumn, name
   - Default: length

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


*Showing 10 of 17 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/v.net.timetable.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

v.net.timetable finds the shortest path between two points using
timetables. v.net.timetable reads input, one query per line, from the
standard input and writes output to the standard output as well as to
the output map and to tables linked to layers 1 and 2. Each line of
input must follow one of the following formats:

where PATH_ID is the identifier of a query that is used in the output
map to differentiate between queries. Search begins at START_TIME.
MIN_CHANGE gives the minimum number of time (inclusively) for a change
from one route to another. MAX_CHANGES denotes the maximum number of
changes allowed or -1 if infinity. WALK_CHANGE is 1 or 0 depending
whether walking from a stop to another stop is considered a change or
not. Finally, the path is found from FROM_STOP to TO_STOP in latter case
and from the stop closest to (FROM_X, FROM_Y) coordinates to the stop
closest to (TO_X, TO_Y) coordinates in former case. For each input query, module outputs a description of the shortest path
to the standard output. For example, using the tables given below, for
the following input:

the following output is produced:

Moreover, the module writes the path to the output map and stores
all the information necessary to reconstruct the path to the tables.
Table corresponding to stops/points is linked to layer 1 and looks,
after the query, as follows:

where CAT is the category of a point in the map, PATH_ID is the path
identifier, STOP_ID is the identifier of the stop as used in the input
map, INDEX is the index of the stop on the path (i.e, index=1 is the
first stop visited, ...) and ARR_TIME and DEP_TIME denote the arrival
time and departure time respectively. Arrival time for the first stop on
the path is always equal to START_TIME and departure time for the last
stop is always equal to the arrival time. The table linked to the second layer corresponds to subroutes taken
between stops. The following table is obtained for the above query:

where CAT is the category of lines of subroute between stops FROM_ID to
TO_ID, ROUTE_ID is the identifier of the route taken or -1 if walking,
INDEX and PATH_ID are as above and FROM_TIME and TO_TIME denote the
times between which the route is taken. The output map contains the points on the positions of used stops.
If a subroute is taken between two stops then a line segment is added
between two corresponding points. Finally, instead of straight line
segment, the actual paths of routes can be given in paths layer. If
this parameter is used then each line in the input map must contain
identifiers as category numbers of all routes passing through the line.
The module then finds the path between two stops and writes this path
instead. In case of walking from one stop to another, straight line
between the stops is used.

---

## See Also

Related tools:
- [`v.net`](https://grass.osgeo.org/grass-devel/manuals/v.net.html)
- [`v.net.path`](https://grass.osgeo.org/grass-devel/manuals/v.net.path.html)
- [`v.net.distance`](https://grass.osgeo.org/grass-devel/manuals/v.net.distance.html)

---

## Authors

Daniel Bundala, Google Summer of Code 2009, Student Wolf Bergenheim, Mentor

---

## Resources

- [Official v.net.timetable manual](https://grass.osgeo.org/grass-devel/manuals/v.net.timetable.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/v.net.timetable.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
