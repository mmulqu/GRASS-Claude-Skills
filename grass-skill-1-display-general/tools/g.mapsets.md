# g.mapsets

**Category**: general

## Description

Modifies or reports the user's current mapset search path. Affects the user's access to data existing under the other mapsets in the current project.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.g_mapsets(mapset,operation="add",format="plain",separator=None,flags=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`mapset : str | list[str], required`**
   - Name of mapset (default: current search path)
   - Name(s) of existing mapset(s) to add/remove or set
   - Used as: input, mapset, name

2. **`operation : str, required`**
   - Operation to be performed
   - Allowed values: set, add, remove
   - Default: add

3. **`format : str, required`**
   - Output format
   - Used as: name
   - Allowed values: plain, json
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/g.mapsets.html#__tabbed_2_3) for all details)*

4. **`separator : str, optional`**
   - Field separator
   - Special characters: pipe, comma, space, tab, newline
   - Used as: input, separator, character

5. **`flags : str, optional`**
   - Allowed values: l, p, s
   - l
   - List all available mapsets in alphabetical order
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/g.mapsets.html#__tabbed_2_3) for all details)*

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

g.mapsets modifies/prints the user's current mapset search path. For
basic information about GRASS mapset , project and data base refer
to GRASS Quickstart .

A mapset holds a distinct set of data layers, each relevant to the
same (or a subset of the same) geographic region, and each drawn in the
same map coordinate system. At the outset of every GRASS session, the
user identifies a GRASS data base, project (previously called location),
and mapset that are to be the user's current data base , current
project , and current mapset for the duration of the session; any maps
created by the user during the session will be stored under the current
mapset set at the session's outset (see g.mapset [without an "s"] and g.gisenv for changing the mapset
with a session).

The user can add, modify, and delete data layers that exist under their current mapset . Although the user can also access (i.e., use) data
that are stored under other mapsets in the same GRASS project using
the mapname@mapsetname notation or mapset search path, the user can
only make permanent changes (create or modify data) located in the current mapset . The user's mapset search path lists the order in
which other mapsets in the same GRASS project can be searched and their
data accessed by the user. The user can modify the listing and order in
which these mapsets are accessed by modifying the mapset search path;
this can be done using the g.mapsets command. This program allows the
user to use other's relevant map data without altering the original data
layer, and without taking up disk space with a copy of the original map.
The mapname@mapsetname notation may be used irrespective of the mapset
search path, i.e., any map found in another mapset with sufficient g.access privileges may be called in such a manner.

g.mapsets shows the user available mapsets under the current GRASS
project, lists mapsets to which the user currently has access, and lists
the order in which accessible mapsets will be accessed by GRASS programs
searching for data files. The user is then given the opportunity to add
or delete mapset names from the search path, or modify the order in
which mapsets will be accessed.

When the user specifies the name of a data base element file (e.g., a
particular vector map, raster map, imagery group file,
etc.) to a GRASS program, the program searches for the named file under
each of the mapsets listed in the user's mapset search path in the order
listed there until the program finds a file of the given name. Users can
also specify a file by its mapset, to make explicit the mapset from
which the file is to be drawn; e.g., the command:

ensures that a new file named my_soils is to be a copy of the file soils from the mapset PERMANENT.

In each project there is the special mapset PERMANENT included in
the mapset search path, as this mapset typically contains base maps
relevant to many applications. Often, other mapsets which contain sets
of interpreted maps will be likewise included in the user's mapset
search path. Suppose, for example, that the mapset Soil_Maps contains
interpreted soils map layers to which the user wants access. The mapset Soil_Maps should then be included in the user's search path variable.

The mapset search path is saved as part of the current mapset. When
the user works with that mapset in subsequent GRASS sessions, the
previously saved mapset search path will be used (and will continue to
be used until it is modified by the user with g.mapsets ).

---

## See Also

Related tools:
- [`g.access`](https://grass.osgeo.org/grass-devel/manuals/g.access.html)
- [`g.copy`](https://grass.osgeo.org/grass-devel/manuals/g.copy.html)
- [`g.gisenv`](https://grass.osgeo.org/grass-devel/manuals/g.gisenv.html)
- [`g.list`](https://grass.osgeo.org/grass-devel/manuals/g.list.html)
- [`g.mapset`](https://grass.osgeo.org/grass-devel/manuals/g.mapset.html)

---

## Authors

Michael Shapiro, U.S.Army Construction Engineering Research Laboratory Greg Koerper, ManTech Environmental Technology, Inc. Updated to GRASS 7 by Martin Landa, Czech Technical University in
Prague, Czech Republic

---

## Resources

- [Official g.mapsets manual](https://grass.osgeo.org/grass-devel/manuals/g.mapsets.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/g.mapsets.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
