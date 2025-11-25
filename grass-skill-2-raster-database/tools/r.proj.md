# r.proj

**Category**: raster

## Description

Re-projects a raster map from given project to the current project.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_proj(project,mapset=None,input=None,dbase=None,output=None,method="nearest",memory=300,resolution=None,format="plain",pipeline=None,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`project : str, required`**
   - Project (location) containing input raster map
   - Project name (not path to project)
   - Used as: input, location, name

2. **`mapset : str, optional`**
   - Mapset containing input raster map
   - Default: name of current mapset
   - Used as: input, mapset, name

3. **`input : str | np.ndarray, optional`**
   - Name of input raster map to re-project
   - Used as: input, raster, name

4. **`dbase : str, optional`**
   - Path to GRASS database of input project
   - Default: path to the current GRASS database
   - Used as: input, dbase, path

5. **`output : str | type(np.ndarray) | type(np.array) | type(gs.array.array), optional`**
   - Name for output raster map (default: same as 'input')
   - Used as: output, raster, name

6. **`method : str, optional`**
   - Interpolation method to use
   - Allowed values: nearest, bilinear, bicubic, lanczos, bilinear_f, bicubic_f, lanczos_f
   - nearest: nearest neighbor
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/r.proj.html#__tabbed_2_3) for all details)*

7. **`memory : int, optional`**
   - Maximum memory to be used (in MB)
   - Cache size for raster rows
   - Used as: memory in MB

8. **`resolution : float, optional`**
   - Resolution of output raster map

9. **`format : str, required`**
   - Output format
   - Used as: name
   - Allowed values: plain, shell, json
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/r.proj.html#__tabbed_2_3) for all details)*

10. **`pipeline : str, optional`**
   - PROJ pipeline for coordinate transformation

11. **`flags : str, optional`**
   - Allowed values: l, n, p, g
   - l
   - List raster maps in input mapset and exit
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/r.proj.html#__tabbed_2_3) for all details)*

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


*Showing 10 of 15 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/r.proj.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | np.ndarray | tuple[np.ndarray] | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned. If an array type (e.g., np.ndarray) is used for one of the raster outputs, the result will be an array and will have the shape corresponding to the computational region. If an array type is used for more than one raster output, the result will be a tuple of arrays.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

r.proj is used to reproject a raster map from the coordinate reference
system (CRS) of the input project into a CRS of a specified project
(previously called location). The CRS information is taken from the
current PROJ_INFO files, as set and viewed with g.proj .

Map projections are a method of representing information from a curved
surface (usually a spheroid) in two dimensions, typically to allow
indexing through cartesian coordinates. There are a wide variety of
projections, with common ones divided into a number of classes,
including cylindrical and pseudo-cylindrical, conic and pseudo-conic,
and azimuthal methods, each of which may be conformal, equal-area, or
neither.

The particular projection chosen depends on the purpose of the project,
and the size, shape and location of the area of interest. For example,
normal cylindrical projections are good for maps which are of greater
extent east-west than north-south and in equatorial regions, while conic
projections are better in mid-latitudes; transverse cylindrical
projections are used for maps which are of greater extent north-south
than east-west; azimuthal projections are used for polar regions.
Oblique versions of any of these may also be used. Conformal projections
preserve angular relationships, and better preserve arc-length, while
equal-area projections are more appropriate for statistical studies and
work in which the amount of material is important.

Projections are defined by precise mathematical relations, so the method
of projecting coordinates from a geographic reference frame
(latitude-longitude) into a projected cartesian reference frame (eg
metres) is governed by these equations. Inverse projections can also be
achieved. The public-domain Unix software package PROJ [1] has been
designed to perform these transformations, and the user's manual
contains a detailed description of over 100 useful projections. This
also includes a programmers library of the projection methods to support
other software development.

Thus, converting a vector map - in which objects are located with
arbitrary spatial precision - from one projection into another is
usually accomplished by a simple two-step process: first the location of
all the points in the map are converted from the source through an
inverse projection into latitude-longitude, and then through a forward
projection into the target. (Of course the procedure will be one-step if
either the source or target is in geographic coordinates.)

Converting a raster map, or image, between different projections,
however, involves additional considerations. A raster may be considered
to represent a sampling of a process at a regular, ordered set of
locations. The set of locations that lie at the intersections of a
cartesian grid in one projection will not, in general, coincide with the
sample points in another projection. Thus, the conversion of raster maps
involves an interpolation step in which the values of points at
intermediate locations relative to the source grid are estimated.

GIS data capture, import and transfer often requires a reprojection
step, since the source or client will frequently be in a different CRS
to the working CRS.

In some cases it is convenient to do the conversion outside the package,
prior to import or after export, using software such as PROJ 's cs2cs [1]. This is an easy
method for converting an ASCII file containing a list of coordinate
points, since there is no topology to be preserved and cs2cs can be
used to process simple lists using a one-line command. The m.proj module provides a handy front end to cs2cs .

Vector maps is generally more complex, as parts of the data stored in
the files will describe topology, and not just coordinates. In GRASS, the v.proj module is provided to reproject vector maps,
transferring topology and attributes as well as node coordinates. This
program uses the CRS definition and parameters which are stored in the
PROJ_INFO and PROJ_UNITS files in the PERMANENT mapset directory for
every GRASS project.

As discussed briefly above, the fundamental step in reprojecting a
raster is resampling the source grid at locations corresponding to the
intersections of a grid in the target CRS. The basic procedure for
accomplishing this, therefore, is as follows:

r.proj converts a map to a new CRS. It reads a map from a different
project, reprojects it and writes it out to the current project. The
reprojected data is resampled with one of four different methods:
nearest neighbor, bilinear, bicubic interpolation or lanczos.

The method=nearest method, which performs a nearest neighbor
assignment, is the fastest of the three resampling methods. It is
primarily used for categorical data such as a land use classification,
since it will not change the values of the data cells. The method=bilinear method determines the new value of the cell based on
a weighted distance average of the 4 surrounding cells in the input map.
The method=bicubic method determines the new value of the cell based
on a weighted distance average of the 16 surrounding cells in the input
map. The method=lanczos method determines the new value of the cell
based on a weighted distance average of the 25 surrounding cells in the
input map. Compared to bicubic, lanczos puts a higher weight on cells
close to the center and a lower weight on cells away from the center,
resulting in slightly better contrast.

The bilinear, bicubic and lanczos interpolation methods are most
appropriate for continuous data and cause some smoothing. The amount of
smoothing decreases from bilinear to bicubic to lanczos. These options
should not be used with categorical data, since the cell values will be
altered.

In the bilinear, bicubic and lanczos methods, if any of the surrounding
cells used to interpolate the new cell value are NULL, the resulting
cell will be NULL, even if the nearest cell is not NULL. This will cause
some thinning along NULL borders, such as the coasts of land areas in a
DEM. The bilinear_f , bicubic_f and lanczos_f interpolation
methods can be used if thinning along NULL edges is not desired. These
methods "fall back" to simpler interpolation methods along NULL borders.
That is, from lanczos to bicubic to bilinear to nearest.

If nearest neighbor assignment is used, the output map has the same
raster format as the input map. If any of the interpolations is used,
the output map is written as floating point.

Note that, following normal GRASS conventions, the coverage and
resolution of the resulting grid is set by the current region settings,
which may be adjusted using g.region . The target raster
will be relatively unbiased for all cases if its grid has a similar
resolution to the source, so that the resampling/interpolation step is
only a local operation. If the resolution is changed significantly, then
the behaviour of the generalisation or refinement will depend on the
model of the process being represented. This will be very different for
categorical versus numerical data. Note that three methods for the local
interpolation step are provided.

r.proj supports general datum transformations, making use of the PROJ co-ordinate system translation library.

---

## See Also

Related tools:
- [`g.region`](https://grass.osgeo.org/grass-devel/manuals/g.region.html)
- [`g.proj`](https://grass.osgeo.org/grass-devel/manuals/g.proj.html)
- [`i.rectify`](https://grass.osgeo.org/grass-devel/manuals/i.rectify.html)
- [`m.proj`](https://grass.osgeo.org/grass-devel/manuals/m.proj.html)
- [`r.support`](https://grass.osgeo.org/grass-devel/manuals/r.support.html)
- [`r.stats`](https://grass.osgeo.org/grass-devel/manuals/r.stats.html)
- [`v.proj`](https://grass.osgeo.org/grass-devel/manuals/v.proj.html)
- [`v.in.region`](https://grass.osgeo.org/grass-devel/manuals/v.in.region.html)

---

## Authors

Martin Schroeder, University of Heidelberg, Germany Man page text from S.J.D. Cox, AGCRC, CSIRO Exploration & Mining,
Nedlands, WA Updated by Morten Hulden Datum transformation support and cleanup by Paul Kelly Support of PROJ5+ by Markus Metz, mundialis

---

## Resources

- [Official r.proj manual](https://grass.osgeo.org/grass-devel/manuals/r.proj.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.proj.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
