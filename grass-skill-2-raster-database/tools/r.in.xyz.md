# r.in.xyz

**Category**: raster

## Description

Creates a raster map from an assemblage of many coordinates using univariate statistics.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_in_xyz(input,output,method="mean",separator="pipe",x=1,y=2,z=3,skip=0,zrange=None,zscale=1.0,value_column=0,vrange=None,vscale=1.0,type="FCELL",percent=100,pth=None,trim=None,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str, required`**
   - ASCII file containing input data (or "-" to read from stdin)
   - Used as: input, file, name

2. **`output : str | type(np.ndarray) | type(np.array) | type(gs.array.array), required`**
   - Name for output raster map
   - Used as: output, raster, name

3. **`method : str, optional`**
   - Statistic to use for raster values
   - Allowed values: n, min, max, range, sum, mean, stddev, variance, coeff_var, median, percentile, skewness, trimmean
   - n: Number of points in cell
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/r.in.xyz.html#__tabbed_2_3) for all details)*

4. **`separator : str, optional`**
   - Field separator
   - Special characters: pipe, comma, space, tab, newline
   - Used as: input, separator, character

5. **`x : int, optional`**
   - Column number of x coordinates in input file (first column is 1)
   - Default: 1

6. **`y : int, optional`**
   - Column number of y coordinates in input file
   - Default: 2

7. **`z : int, optional`**
   - Column number of data values in input file
   - If a separate value column is given, this option refers to the z-coordinate column to be filtered by the zrange option
   - Default: 3

8. **`skip : int, optional`**
   - Number of header lines to skip at top of input file
   - Default: 0

9. **`zrange : tuple[float, float] | list[float] | str, optional`**
   - Filter range for z data (min,max)
   - Used as: min,max

10. **`zscale : float, optional`**
   - Scale to apply to z data
   - Default: 1.0

11. **`value_column : int, optional`**
   - Alternate column number of data values in input file
   - If not given (or set to 0) the z-column data is used
   - Default: 0

12. **`vrange : tuple[float, float] | list[float] | str, optional`**
   - Filter range for alternate value column data (min,max)
   - Used as: min,max

13. **`vscale : float, optional`**
   - Scale to apply to alternate value column data
   - Default: 1.0

14. **`type : str, optional`**
   - Type of raster map to be created
   - Storage type for resultant raster map
   - Allowed values: CELL, FCELL, DCELL
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/r.in.xyz.html#__tabbed_2_3) for all details)*

15. **`percent : int, optional`**
   - Percent of map to keep in memory
   - Allowed values: 1-100
   - Default: 100

16. **`pth : int, optional`**
   - Pth percentile of the values
   - Allowed values: 1-100

17. **`trim : float, optional`**
   - Discard <trim> percent of the smallest and <trim> percent of the largest observations
   - Allowed values: 0-50

18. **`flags : str, optional`**
   - Allowed values: s, g, i
   - s
   - Scan data file for extent then exit
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/r.in.xyz.html#__tabbed_2_3) for all details)*

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


*Showing 10 of 22 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/r.in.xyz.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | np.ndarray | tuple[np.ndarray] | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned. If an array type (e.g., np.ndarray) is used for one of the raster outputs, the result will be an array and will have the shape corresponding to the computational region. If an array type is used for more than one raster output, the result will be a tuple of arrays.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

The r.in.xyz module will load and bin ungridded x,y,z ASCII data into
a new raster map. The user may choose from a variety of statistical
methods in creating the new raster. Gridded data provided as a stream of
x,y,z points may also be imported.

Please note that the current region extents and resolution are used for
the import. It is therefore recommended to first use the -s flag to
get the extents of the input points to be imported, then adjust the
current region accordingly, and only then proceed with the actual
import.

r.in.xyz is designed for processing massive point cloud datasets, for
example raw LIDAR or sidescan sonar swath data. It has been tested with
datasets as large as tens of billion of points (705GB in a single file).

Available statistics for populating the raster are ( method ):

It is also possible to bin and store another data column (e.g.
backscatter) while simultaneously filtering and scaling both the data
column values and the z range.

---

## See Also

Related tools:
- [`g.region`](https://grass.osgeo.org/grass-devel/manuals/g.region.html)
- [`m.proj`](https://grass.osgeo.org/grass-devel/manuals/m.proj.html)
- [`r.fillnulls`](https://grass.osgeo.org/grass-devel/manuals/r.fillnulls.html)
- [`r.in.ascii`](https://grass.osgeo.org/grass-devel/manuals/r.in.ascii.html)
- [`r.in.pdal`](https://grass.osgeo.org/grass-devel/manuals/r.in.pdal.html)
- [`r3.in.xyz`](https://grass.osgeo.org/grass-devel/manuals/r3.in.xyz.html)
- [`r.mapcalc`](https://grass.osgeo.org/grass-devel/manuals/r.mapcalc.html)
- [`r.neighbors`](https://grass.osgeo.org/grass-devel/manuals/r.neighbors.html)
- [`r.out.xyz`](https://grass.osgeo.org/grass-devel/manuals/r.out.xyz.html)
- [`r.to.rast3`](https://grass.osgeo.org/grass-devel/manuals/r.to.rast3.html)
- [`r.to.vect`](https://grass.osgeo.org/grass-devel/manuals/r.to.vect.html)
- [`r.univar`](https://grass.osgeo.org/grass-devel/manuals/r.univar.html)
- [`v.in.ascii`](https://grass.osgeo.org/grass-devel/manuals/v.in.ascii.html)
- [`v.surf.rst`](https://grass.osgeo.org/grass-devel/manuals/v.surf.rst.html)

---

## Authors

Hamish Bowman, Department of Marine Science, University of Otagom New
Zealand Extended by Volker Wichmann to support the aggregate functions median,
percentile, skewness and trimmed mean .

---

## Resources

- [Official r.in.xyz manual](https://grass.osgeo.org/grass-devel/manuals/r.in.xyz.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.in.xyz.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
