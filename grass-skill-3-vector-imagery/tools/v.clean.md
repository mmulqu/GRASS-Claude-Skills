# v.clean

**Category**: vector

## Description

Toolset for cleaning topology of vector map.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.v_clean(input,layer="-1",type="point,line,boundary,centroid,area,face,kernel",output,error=None,tool,threshold=None,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str, required`**
   - Name of input vector map
   - Or data source for direct OGR access
   - Used as: input, vector, name

2. **`layer : str, optional`**
   - Layer number or name ('-1' for all layers)
   - A single vector map can be connected to multiple database tables. This number determines which table to use. When used with direct OGR access this is the layer name.
   - Used as: input, layer

3. **`type : str | list[str], optional`**
   - Input feature type
   - Allowed values: point, line, boundary, centroid, area, face, kernel
   - Default: point,line,boundary,centroid,area,face,kernel

4. **`output : str, required`**
   - Name for output vector map
   - Used as: output, vector, name

5. **`error : str, optional`**
   - Name of output map where errors are written
   - Used as: output, vector, name

6. **`tool : str | list[str], required`**
   - Cleaning tool
   - Allowed values: break, snap, rmdangle, chdangle, rmbridge, chbridge, rmdupl, rmdac, bpol, prune, rmarea, rmline, rmsa
   - break: break lines at each intersection
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/v.clean.html#__tabbed_2_3) for all details)*

7. **`threshold : float | list[float] | str, optional`**
   - One value for each tool; for threshold units, see each tool
   - Default: 0.0[,0.0,...])

8. **`flags : str, optional`**
   - Allowed values: b, c
   - b
   - Do not build topology for the output vector
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/v.clean.html#__tabbed_2_3) for all details)*

9. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

10. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

11. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

12. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 12 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/v.clean.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

v.clean allows the user to automatically fix topology of vector maps.
Several tools may be listed to be executed sequentially. In this case,
also the threshold parameter requires several values to be listed
accordingly. An error map is optionally written which stores the
erroneous geometries.

Setting tool=break breaks lines/boundaries at intersections and it also
breaks lines/boundaries forming a collapsed loop. For example,
0.0;1.0;0.0 is broken at 1.0.

Threshold does not apply (it is ignored), use an arbitrary value (e.g.,
0) if v.clean is run with several tools.

Hint: Breaking lines should be followed by removing duplicates, e.g. v.clean ... tool=break,rmdupl . If the -c flag is used with v.clean
... tool=break , duplicates are automatically removed.

Setting tool=rmdupl removes geometry features with identical coordinates.
Categories are merged. If a point and a centroid have identical
coordinates, one of them will be removed if both points and centroids
are selected with v.clean ... type=point,centroid . The same applies
for lines and boundaries.

Threshold does not apply (it is ignored), use an arbitrary value (e.g.,
0) if v.clean is run with several tools.

The rmdupl tool should be used after breaking lines and breaking
polygons.

A line/boundary is considered to be a dangle if no other line of given type is on at least one end node. If a dangle is formed by several
lines, such a string of lines is taken as one dangle and line lengths
are summarized. Setting tool=rmdangle deletes a dangle if the (combined)
length is shorter than thresh or thresh \< 0. If the combined length
is larger than thresh , nothing is deleted.

Threshold has to be given as maximum line/boundary length in map units;
for latitude-longitude projects in degrees. Dangles shorter than thresh are removed sequentially. All dangles will be removed if thresh \< 0.

With thresh \< 0, only closed loops and lines connecting loops will
remain. This is useful to remove all incorrect boundaries after other
cleaning operations with thres is \< 0. Areas can then be successfully
built.

To preferentially remove shortest dangles first, a first pass with a
small thresh value can be followed by subsequent passes with higher thresh values. This can be done as one v.clean job by listing the
tool several times and by defining a list of increasing thresh values.

Setting tool=chdangle is similar to the rmdangle tool, but works only on
boundaries and changes dangling boundaries to lines instead of removing
them.

A bridge is an area type connection of an island (polygon in a polygon)
to the outer polygon. This is topologically incorrect (but OGC Simple
Features allow it). Setting tool=rmbridge removes bridges and setting tool=chbridge changes bridges to type line:

Islands and areas must be already clean, i.e. without dangles or small
angles, e.g. v.clean ... type=boundary
tool=rmdangle,rmsa,break,rmdupl,rmbridge thresh=-1,0,0,0,0 .

Threshold does not apply (it is ignored), use an arbitrary value (e.g.,
0) if v.clean is run with several tools.

Setting tool=snap snaps vertices to another vertex not farther away than thresh . If there is no other vertex within thresh , no snapping will
be done. The type option can have a strong influence on the result. A
too large threshold and type=boundary can severely damage area
topology, beyond repair.

Threshold gives maximum distance to another vertex in map units, for
latitude-longitude projects in degrees.

Snapped boundaries may need to be cleaned with break,rmdupl,rmsa . If
the -c flag is used with v.clean tool=snap , the sequence of break,rmdupl,rmsa is automatically repeated after snapping until no
more small angles a left. Additional cleaning with e.g. tool=rmdangle may be necessary.

Setting tool=rmdac removes duplicate area centroids that can result from
deleting boundaries.

Threshold does not apply (it is ignored), use an arbitrary value (e.g.,
0) if v.clean is run with several tools.

Setting tool=bpol breaks boundaries on each point shared between 2 and
more areas where angles of boundary segments are different and on all
boundary nodes (start and end points of each boundary). The bpol tool
behaves similar to break for boundaries, but does not break collapsed
loops. The bpol tool is faster than the break tool but needs more
memory.

Threshold does not apply (it is ignored), use an arbitrary value (e.g.,
0) if v.clean is run with several tools.

The bpol tool should be followed by rmdupl . If the -c flag is used
with v.clean ... tool=bpol , duplicates are automatically removed.

Setting tool=prune simplifies lines and boundaries by removing vertices
according to threshold. This tool preserves area topology, areas are
never deleted and centroid attachment is never changed. v.generalize offers much more functionality for
line simplification but does not preserve area topology.

Setting tool=rmarea removes all areas \<= thresh . The longest boundary
with an adjacent area is removed or all boundaries if there is no
adjacent area. Area categories are not combined when a small area is
merged with a larger area.

Threshold must always be in square meters, also for latitude-longitude
projects or projects with units other than meters.

Setting tool=rmline removes all lines or boundaries of zero length that
may have resulted from other cleaning operations. Zero length boundaries
are redundant and do not influence area topology.

Threshold does not apply (it is ignored), use an arbitrary value (e.g.,
0) if v.clean is run with several tools.

Setting tool=rmsa only concerns angles which are so small that the
calculated angle is 0. The following figure should help demonstrate what
the tool does.

Threshold does not apply, use dummy value if v.clean is run with
several tools.

tool=rmsa

The rmsa tool should be followed by break,rmdupl . The rmsa tool
followed by break,rmdupl may need to be run more than once to remove
all small angles. If the -c flag is used with v.clean ... tool=rmsa ,
the sequence of rmsa,break,rmdupl is automatically repeated until no
more small angles a left.

---

## See Also

Related tools:
- [`v.info`](https://grass.osgeo.org/grass-devel/manuals/v.info.html)
- [`v.build`](https://grass.osgeo.org/grass-devel/manuals/v.build.html)
- [`g.gui.vdigit`](https://grass.osgeo.org/grass-devel/manuals/g.gui.vdigit.html)
- [`v.edit`](https://grass.osgeo.org/grass-devel/manuals/v.edit.html)
- [`v.fill.holes`](https://grass.osgeo.org/grass-devel/manuals/v.fill.holes.html)
- [`v.generalize`](https://grass.osgeo.org/grass-devel/manuals/v.generalize.html)

---

## Authors

David Gerdes, U.S. Army Construction Engineering Research Laboratory Radim Blazek, ITC-irst, Trento, Italy Martin Landa, FBK-irst (formerly ITC-irst), Trento, Italy

---

## Resources

- [Official v.clean manual](https://grass.osgeo.org/grass-devel/manuals/v.clean.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/v.clean.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
