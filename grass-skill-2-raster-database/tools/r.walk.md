# r.walk

**Category**: raster

## Description

Creates a raster map showing the anisotropic cumulative cost of moving between different geographic locations on an input raster map whose cell category values represent cost.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_walk(elevation,friction,output,solver=None,nearest=None,outdir=None,start_points=None,stop_points=None,start_raster=None,start_coordinates=None,stop_coordinates=None,max_cost=0,null_cost=None,memory=300,walk_coeff="0.72,6.0,1.9998,-1.9998",lambda=1.0,slope_factor=-0.2125,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`elevation : str | np.ndarray, required`**
   - Name of input elevation raster map
   - Used as: input, raster, name

2. **`friction : str | np.ndarray, required`**
   - Name of input raster map containing friction costs
   - Used as: input, raster, name

3. **`output : str | type(np.ndarray) | type(np.array) | type(gs.array.array), required`**
   - Name for output raster map to contain walking costs
   - Used as: output, raster, name

4. **`solver : str | np.ndarray, optional`**
   - Name of input raster map solving equal costs
   - Helper variable to pick a direction if two directions have equal cumulative costs (smaller is better)
   - Used as: input, raster, name

5. **`nearest : str | type(np.ndarray) | type(np.array) | type(gs.array.array), optional`**
   - Name for output raster map with nearest start point
   - Used as: output, raster, name

6. **`outdir : str | type(np.ndarray) | type(np.array) | type(gs.array.array), optional`**
   - Name for output raster map to contain movement directions
   - Used as: output, raster, name

7. **`start_points : str, optional`**
   - Name of starting vector points map
   - Or data source for direct OGR access
   - Used as: input, vector, name

8. **`stop_points : str, optional`**
   - Name of stopping vector points map
   - Or data source for direct OGR access
   - Used as: input, vector, name

9. **`start_raster : str | np.ndarray, optional`**
   - Name of starting raster points map
   - Used as: input, raster, name

10. **`start_coordinates : list[tuple[float, float]] | tuple[float, float] | list[float] | str, optional`**
   - Coordinates of starting point(s) (E,N)
   - Used as: input, coords, east,north

11. **`stop_coordinates : list[tuple[float, float]] | tuple[float, float] | list[float] | str, optional`**
   - Coordinates of stopping point(s) (E,N)
   - Used as: input, coords, east,north

12. **`max_cost : int, optional`**
   - Maximum cumulative cost
   - Used as: value
   - Default: 0

13. **`null_cost : float, optional`**
   - Cost assigned to null cells. By default, null cells are excluded
   - Used as: value

14. **`memory : int, optional`**
   - Maximum memory to be used (in MB)
   - Cache size for raster rows
   - Used as: memory in MB

15. **`walk_coeff : tuple[str, str, str, str] | list[str] | str, optional`**
   - Coefficients for walking energy formula parameters a,b,c,d
   - Used as: a,b,c,d
   - Default: 0.72,6.0,1.9998,-1.9998

16. **`lambda : float, optional`**
   - Lambda coefficients for combining walking energy and friction cost
   - Default: 1.0

17. **`slope_factor : float, optional`**
   - Slope factor determines travel energy cost per height step
   - Default: -0.2125

18. **`flags : str, optional`**
   - Allowed values: k, n, r, i, b
   - k
   - Use the 'Knight's move'; slower, but more accurate
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/r.walk.html#__tabbed_2_3) for all details)*

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


*Showing 10 of 22 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/r.walk.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | np.ndarray | tuple[np.ndarray] | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned. If an array type (e.g., np.ndarray) is used for one of the raster outputs, the result will be an array and will have the shape corresponding to the computational region. If an array type is used for more than one raster output, the result will be a tuple of arrays.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

r.walk computes anisotropic cumulative cost of moving between
different geographic locations on an input elevation raster map whose
cell category values represent elevation combined with an input raster
map layer whose cell values represent friction cost.

r.walk outputs 1) a raster map showing the lowest cumulative cost
(time) of moving between each cell and the user-specified starting
points and 2) a second raster map showing the movement direction to the
next cell on the path back to the start point (see Movement
Direction ). It uses an input elevation raster map whose cell
category values represent elevation, combined with a second input raster
map whose cell values represent friction costs.

This function is similar to r.cost , but in addition to a
friction map, it considers an anisotropic travel time due to the
different walking speed associated with downhill and uphill movements.

---

## See Also

Related tools:
- [`r.cost`](https://grass.osgeo.org/grass-devel/manuals/r.cost.html)
- [`r.path`](https://grass.osgeo.org/grass-devel/manuals/r.path.html)
- [`r.in.ascii`](https://grass.osgeo.org/grass-devel/manuals/r.in.ascii.html)
- [`r.mapcalc`](https://grass.osgeo.org/grass-devel/manuals/r.mapcalc.html)
- [`r.recode`](https://grass.osgeo.org/grass-devel/manuals/r.recode.html)
- [`r.out.ascii`](https://grass.osgeo.org/grass-devel/manuals/r.out.ascii.html)

---

## Authors

Based on r.cost written by : Antony Awaida, Intelligent Engineering, Systems Laboratory, M.I.T. James Westervelt, U.S.Army Construction Engineering Research
Laboratory Updated for Grass 5 by Pierre de Mouveaux ( pmx@audiovu.com )
Initial version of r.walk: Steno Fontanari, 2002
Current version of r.walk: Franceschetti Simone, Sorrentino Diego, Mussi Fabiano and Pasolli
Mattia Correction by: Fontanari Steno, Napolitano Maurizio and Flor Roberto In collaboration with: Franchi Matteo, Vaglia Beatrice, Bartucca Luisa,
Fava Valentina and Tolotti Mathias, 2004
Updated for GRASS 6.1: Roberto Flor and Markus Neteler
Updated for GRASS GIS 7: Markus Metz Multiple path directions sponsored by mundialis

---

## Resources

- [Official r.walk manual](https://grass.osgeo.org/grass-devel/manuals/r.walk.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.walk.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
