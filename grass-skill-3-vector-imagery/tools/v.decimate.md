# v.decimate

**Category**: vector

## Description

Decimates a point cloud Copies points from one vector to another while applying different decimations

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.v_decimate(input,layer="-1",output,zrange=None,cats=None,skip=None,preserve=None,offset=None,limit=None,zdiff=None,cell_limit=None,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
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

3. **`output : str, required`**
   - Name for output vector map
   - Used as: output, vector, name

4. **`zrange : tuple[float, float] | list[float] | str, optional`**
   - Filter range for z data (min,max)
   - Used as: min,max

5. **`cats : str, optional`**
   - Category values
   - Example: 1,3,7-9,13
   - Used as: input, cats, range

6. **`skip : int, optional`**
   - Throw away every n-th point
   - For example, 5 will import 80 percent of points. If not specified, all points are copied

7. **`preserve : int, optional`**
   - Preserve only every n-th point
   - For example, 4 will import 25 percent of points. If not specified, all points are copied

8. **`offset : int, optional`**
   - Skip first n points
   - Skips the given number of points at the beginning.

9. **`limit : int, optional`**
   - Copy only n points
   - Copies only the given number of points

10. **`zdiff : float, optional`**
   - Minimal difference of z values
   - Minimal difference between z values in grid-based decimation

11. **`cell_limit : int, optional`**
   - Preserve only n points per grid cell
   - Preserves only the given number of points per grid cell in grid-based decimation

12. **`flags : str, optional`**
   - Allowed values: g, f, c, z, x, b, t
   - g
   - Apply grid-based decimation
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/v.decimate.html#__tabbed_2_3) for all details)*

13. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

14. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

15. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

16. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 16 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/v.decimate.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

v.decimate reduces number of points in the input vector map and copies
them over to the output vector map. Different point decimation
techniques can be applied to reduce the number of points.

Two main decimation techniques are:

The grid-based decimation will remove points based on:

The grid-based decimation is currently using a 2D grid, so the points
are placed and compared within this 2D grid. The comparison can happen
using z coordinates or categories. Note that although the grid is only
2D, the module works with 3D points.

The grid-based decimation extent and resolution depend on the current
computational region as set by g.region . As a
consequence, the output is limited only to computational region in this
case.

TODO: Currently, any output is limited by the region.

The count-based decimation result highly depends on how the data are
ordered in the input. This applies especially to offset and limit options where the resulting shape and densities can be
surprising. The options skip and preserve are influenced by
order of points in a similar way but they usually keep relative density
of points (which may or may not be desired). On the other hand, the
grid-based decimation will generally result in more even density of
output points (see Figure 1).

Besides decimation, point count can be reduced by applying different
selections or filters, these are:

---

## See Also

Related tools:
- [`v.extract`](https://grass.osgeo.org/grass-devel/manuals/v.extract.html)
- [`v.outlier`](https://grass.osgeo.org/grass-devel/manuals/v.outlier.html)
- [`v.select`](https://grass.osgeo.org/grass-devel/manuals/v.select.html)
- [`v.category`](https://grass.osgeo.org/grass-devel/manuals/v.category.html)
- [`v.build`](https://grass.osgeo.org/grass-devel/manuals/v.build.html)
- [`v.in.pdal`](https://grass.osgeo.org/grass-devel/manuals/v.in.pdal.html)
- [`g.region`](https://grass.osgeo.org/grass-devel/manuals/g.region.html)

---

## Resources

- [Official v.decimate manual](https://grass.osgeo.org/grass-devel/manuals/v.decimate.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/v.decimate.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
