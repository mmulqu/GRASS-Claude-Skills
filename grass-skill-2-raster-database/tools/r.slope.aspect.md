# r.slope.aspect

**Category**: raster

## Description

Generates raster maps of slope, aspect, curvatures and partial derivatives from an elevation raster map. Aspect is calculated counterclockwise from east.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_slope_aspect(elevation,slope=None,aspect=None,format="degrees",precision="FCELL",pcurvature=None,tcurvature=None,dx=None,dy=None,dxx=None,dyy=None,dxy=None,zscale=1.0,min_slope=0.0,nprocs=0,memory=300,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`elevation : str | np.ndarray, required`**
   - Name of input elevation raster map
   - Used as: input, raster, name

2. **`slope : str | type(np.ndarray) | type(np.array) | type(gs.array.array), optional`**
   - Name for output slope raster map
   - Used as: output, raster, name

3. **`aspect : str | type(np.ndarray) | type(np.array) | type(gs.array.array), optional`**
   - Name for output aspect raster map
   - Used as: output, raster, name

4. **`format : str, optional`**
   - Format for reporting the slope
   - Allowed values: degrees, percent
   - Default: degrees

5. **`precision : str, optional`**
   - Type of output aspect and slope maps
   - Storage type for resultant raster map
   - Allowed values: CELL, FCELL, DCELL
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/r.slope.aspect.html#__tabbed_2_3) for all details)*

6. **`pcurvature : str | type(np.ndarray) | type(np.array) | type(gs.array.array), optional`**
   - Name for output profile curvature raster map
   - Used as: output, raster, name

7. **`tcurvature : str | type(np.ndarray) | type(np.array) | type(gs.array.array), optional`**
   - Name for output tangential curvature raster map
   - Used as: output, raster, name

8. **`dx : str | type(np.ndarray) | type(np.array) | type(gs.array.array), optional`**
   - Name for output first order partial derivative dx (E-W slope) raster map
   - Used as: output, raster, name

9. **`dy : str | type(np.ndarray) | type(np.array) | type(gs.array.array), optional`**
   - Name for output first order partial derivative dy (N-S slope) raster map
   - Used as: output, raster, name

10. **`dxx : str | type(np.ndarray) | type(np.array) | type(gs.array.array), optional`**
   - Name for output second order partial derivative dxx raster map
   - Used as: output, raster, name

11. **`dyy : str | type(np.ndarray) | type(np.array) | type(gs.array.array), optional`**
   - Name for output second order partial derivative dyy raster map
   - Used as: output, raster, name

12. **`dxy : str | type(np.ndarray) | type(np.array) | type(gs.array.array), optional`**
   - Name for output second order partial derivative dxy raster map
   - Used as: output, raster, name

13. **`zscale : float, optional`**
   - Multiplicative factor to convert elevation units to horizontal units
   - Default: 1.0

14. **`min_slope : float, optional`**
   - Minimum slope value (in percent) for which aspect is computed
   - Default: 0.0

15. **`nprocs : int, optional`**
   - Number of threads for parallel computing
   - 0: use OpenMP default; >0: use nprocs; <0: use MAX-nprocs
   - Default: 0

16. **`memory : int, optional`**
   - Maximum memory to be used (in MB)
   - Cache size for raster rows
   - Used as: memory in MB

17. **`flags : str, optional`**
   - Allowed values: a, e, n
   - a
   - Do not align the current region to the raster elevation map
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/r.slope.aspect.html#__tabbed_2_3) for all details)*

18. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

19. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

20. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

21. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 21 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/r.slope.aspect.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | np.ndarray | tuple[np.ndarray] | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned. If an array type (e.g., np.ndarray) is used for one of the raster outputs, the result will be an array and will have the shape corresponding to the computational region. If an array type is used for more than one raster output, the result will be a tuple of arrays.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

r.slope.aspect generates raster maps of slope, aspect, curvatures and
first and second order partial derivatives from a raster map of true
elevation values. The user must specify the input elevation raster
map and at least one output raster maps. The user can also specify the format for slope (degrees, percent; default=degrees), and the zscale : multiplicative factor to convert elevation units to
horizontal units; (default 1.0).

The elevation input raster map specified by the user must contain
true elevation values, not rescaled or categorized data. If the
elevation values are in other units than in the horizontal units, they
must be converted to horizontal units using the parameter zscale . In GRASS, vertical units are not assumed to be meters any more.
For example, if both your vertical and horizontal units are feet,
parameter zscale must not be used .

The aspect output raster map indicates the direction that slopes are
facing counterclockwise from East: 90 degrees is North, 180 is West, 270
is South, 360 is East. Zero aspect indicates flat areas with zero slope.
Category and color table files are also generated for the aspect raster
map. Note: These values can be transformed to azimuth values (90 is East, 180
is South, 270 is West, 360 is North) using r.mapcalc :

Alternatively, the -n flag can be used to produce aspect as degrees
CW from North. Aspect for flat areas is then set to -9999 (default: 0).
Note: The reason for using -9999 is to be compliant with gdaldem which uses -9999 by default as the nodata value.

The aspect for slope equal to zero (flat areas) is set to zero (-9999
with -n flag). Thus, most cells with a very small slope end up
having category 0, 45, ..., 360 in aspect output. It is possible to
reduce the bias in these directions by filtering out the aspect in areas
where the terrain is almost flat. A option min_slope can be used to
specify the minimum slope for which aspect is computed. For all cells
with slope \< min_slope , both slope and aspect are set to zero.



The slope output raster map contains slope values, stated in degrees
of inclination from the horizontal if format =degrees option (the
default) is chosen, and in percent rise if format =percent option is
chosen. Category and color table files are generated.

Profile and tangential curvatures are the curvatures in the direction of
steepest slope and in the direction of the contour tangent respectively.
The curvatures are expressed as 1/metres, e.g. a curvature of 0.05
corresponds to a radius of curvature of 20m. Convex form values are
positive and concave form values are negative.

Example DEM

Slope (degree) from example DEM

Aspect (degree) from example DEM

Tangential curvature (1/m) from example DEM

Profile curvature (1/m) from example DEM

For some applications, the user will wish to use a reclassified raster
map of slope that groups slope values into ranges of slope. This can be
done using r.reclass . An example of a useful
reclassification is given below:

The following color table works well with the above reclassification.

---

## See Also

Related tools:
- [`r.mapcalc`](https://grass.osgeo.org/grass-devel/manuals/r.mapcalc.html)
- [`r.neighbors`](https://grass.osgeo.org/grass-devel/manuals/r.neighbors.html)
- [`r.reclass`](https://grass.osgeo.org/grass-devel/manuals/r.reclass.html)
- [`r.rescale`](https://grass.osgeo.org/grass-devel/manuals/r.rescale.html)

---

## Authors

Michael Shapiro, U.S.Army Construction Engineering Research Laboratory Olga Waupotitsch, U.S.Army Construction Engineering Research Laboratory

---

## Resources

- [Official r.slope.aspect manual](https://grass.osgeo.org/grass-devel/manuals/r.slope.aspect.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.slope.aspect.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
