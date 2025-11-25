# r.to.vect

**Category**: raster

## Description

Converts a raster map into a vector map.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_to_vect(input,output,type,column="value",flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str | np.ndarray, required`**
   - Name of input raster map
   - Used as: input, raster, name

2. **`output : str, required`**
   - Name for output vector map
   - Used as: output, vector, name

3. **`type : str, required`**
   - Output feature type
   - Allowed values: point, line, area

4. **`column : str, optional`**
   - Name of attribute column to store value
   - Name must be SQL compliant
   - Used as: input, dbcolumn, name

5. **`flags : str, optional`**
   - Allowed values: s, v, z, b, c, t
   - s
   - Smooth corners of area features
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/r.to.vect.html#__tabbed_2_3) for all details)*

6. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

7. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

8. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

9. **`superquiet : bool, optional`**
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

r.to.vect scans the named input raster map layer, extracts points,
lines or area edge features from it, converts data to GRASS vector
format.

The r.to.vect program extracts data from a GRASS raster map layer and
stores output in a new GRASS vector file.

r.to.vect assumes that the input map has been thinned using r.thin .

r.to.vect extracts vectors (aka, "arcs") from a raster map. These arcs
may represent linear features (like roads or streams), or may represent
area edge features (like political boundaries, or soil mapping units).

r.thin and r.to.vect may create excessive nodes at
every junction, and may create small spurs or "dangling lines" during
the thinning and vectorization process. These excessive nodes and spurs
may be removed using v.clean .

r.to.vect first traces the perimeter of each unique area in the raster
map layer and creates vector data to represent it. The cell category
values for the raster map layer will be used to create attribute
information for the resultant vector area edge data.

A true vector tracing of the area edges might appear blocky, since the
vectors outline the edges of raster data that are stored in rectangular
cells. To produce a better-looking vector map, r.to.vect smoothes the
corners of the vector data as they are being extracted. At each change
in direction (i.e., each corner), the two midpoints of the corner cell
(half the cell's height and width) are taken, and the line segment
connecting them is used to outline this corner in the resultant vector
map. (The cell's cornermost node is ignored.) Because vectors are
smoothed by this program, the resulting vector map will not be "true" to
the raster map from which it was created. The user should check the
resolution of the geographic region (and the original data) to estimate
the possible error introduced by smoothing.

r.to.vect extracts only area edges from the named raster input file.
If the raster map contains other data (i.e., line edges, or point data)
the output may be wrong.

By default, area centroids are often located close to boundaries and not
in the middle of an area. Centroids can be more centrally located with
the -c flag.

---

## See Also

Related tools:
- [`g.region`](https://grass.osgeo.org/grass-devel/manuals/g.region.html)
- [`r.thin`](https://grass.osgeo.org/grass-devel/manuals/r.thin.html)
- [`v.clean`](https://grass.osgeo.org/grass-devel/manuals/v.clean.html)

---

## Authors

Point support Bill Brown
Line support Mike Baba DBA Systems, Inc. 10560 Arrowhead Drive Fairfax, Virginia 22030
Area support Original version of r.poly : Jean Ezell and Andrew Heekin, U.S. Army Construction Engineering Research Laboratory
Modified program for smoothed lines: David Satnik, Central Washington University Updated 2001 by Andrea Aime, Modena, Italy
Update Original r.to.sites, r.line and r.poly merged and updated to 5.7 by
Radim Blazek

---

## Resources

- [Official r.to.vect manual](https://grass.osgeo.org/grass-devel/manuals/r.to.vect.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.to.vect.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
