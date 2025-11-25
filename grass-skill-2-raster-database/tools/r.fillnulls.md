# r.fillnulls

**Category**: raster

## Description

Fills no-data areas in raster maps using spline interpolation.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_fillnulls(input,output,method="rst",tension=40.,smooth=0.1,edge=3,npmin=600,segmax=300,lambda=0.01,memory=300,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str | np.ndarray, required`**
   - Name of input raster map
   - Used as: input, raster, name

2. **`output : str | type(np.ndarray) | type(np.array) | type(gs.array.array), required`**
   - Name for output raster map
   - Used as: output, raster, name

3. **`method : str, required`**
   - Interpolation method to use
   - Allowed values: bilinear, bicubic, rst
   - Default: rst

4. **`tension : float, optional`**
   - Spline tension parameter
   - Default: 40.

5. **`smooth : float, optional`**
   - Spline smoothing parameter
   - Default: 0.1

6. **`edge : int, optional`**
   - Width of hole edge used for interpolation (in cells)
   - Allowed values: 2-100
   - Default: 3

7. **`npmin : int, optional`**
   - Minimum number of points for approximation in a segment (>segmax)
   - Allowed values: 2-10000
   - Default: 600

8. **`segmax : int, optional`**
   - Maximum number of points in a segment
   - Allowed values: 2-10000
   - Default: 300

9. **`lambda : float, optional`**
   - Tykhonov regularization parameter (affects smoothing)
   - Used in bilinear and bicubic spline interpolation
   - Default: 0.01

10. **`memory : int, optional`**
   - Maximum memory to be used (in MB)
   - Cache size for raster rows
   - Used as: memory in MB

11. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

12. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

13. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

14. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 14 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/r.fillnulls.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | np.ndarray | tuple[np.ndarray] | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned. If an array type (e.g., np.ndarray) is used for one of the raster outputs, the result will be an array and will have the shape corresponding to the computational region. If an array type is used for more than one raster output, the result will be a tuple of arrays.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

r.fillnulls fills NULL pixels (no data areas) in input raster map and
stores filled data to a new output raster map. The fill areas are
interpolated from the no data area boundaries buffer using v.surf.rst regularized spline interpolation with
tension ( method=rst ) or r.resamp.bspline cubic or linear spline interpolation with Tykhonov regularization.

---

## See Also

Related tools:
- [`r.fill.dir`](https://grass.osgeo.org/grass-devel/manuals/r.fill.dir.html)
- [`r.mapcalc`](https://grass.osgeo.org/grass-devel/manuals/r.mapcalc.html)
- [`r.resamp.bspline`](https://grass.osgeo.org/grass-devel/manuals/r.resamp.bspline.html)
- [`v.surf.bspline`](https://grass.osgeo.org/grass-devel/manuals/v.surf.bspline.html)
- [`v.surf.rst`](https://grass.osgeo.org/grass-devel/manuals/v.surf.rst.html)
- [`v.fill.holes`](https://grass.osgeo.org/grass-devel/manuals/v.fill.holes.html)

---

## Authors

Markus Neteler, University of Hannover and Fondazione Edmund Mach Improvement by Hamish Bowman, NZ

---

## Resources

- [Official r.fillnulls manual](https://grass.osgeo.org/grass-devel/manuals/r.fillnulls.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.fillnulls.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
