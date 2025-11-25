# v.sample

**Category**: vector

## Description

Samples a raster map at vector point locations.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.v_sample(input,layer="1",column,output,raster,method="nearest",zscale=1.0,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str, required`**
   - Name of input vector point map
   - Or data source for direct OGR access
   - Used as: input, vector, name

2. **`layer : str, optional`**
   - Layer number or name
   - Vector features can have category values in different layers. This number determines which layer to use. When used with direct OGR access this is the layer name.
   - Used as: input, layer

3. **`column : str, required`**
   - Name of attribute column to use for comparison
   - Used as: input, dbcolumn, name

4. **`output : str, required`**
   - Name for output vector map to store differences
   - Used as: output, vector, name

5. **`raster : str | np.ndarray, required`**
   - Name of raster map to be sampled
   - Used as: input, raster, name

6. **`method : str, optional`**
   - Sampling interpolation method
   - Allowed values: nearest, bilinear, bicubic
   - nearest: Nearest-neighbor interpolation
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/v.sample.html#__tabbed_2_3) for all details)*

7. **`zscale : float, optional`**
   - Scaling factor for values read from raster map
   - Sampled values will be multiplied by this factor
   - Default: 1.0

8. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

9. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

10. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

11. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 11 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/v.sample.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

v.sample samples a GRASS raster map at the point locations in the
input file by either cubic convolution interpolation, bilinear
interpolation, or nearest neighbor sampling (default).

This program may be especially useful when sampling for cross validation
of interpolations whose output is a raster map.

---

## See Also

Related tools:
- [`g.region`](https://grass.osgeo.org/grass-devel/manuals/g.region.html)
- [`v.random`](https://grass.osgeo.org/grass-devel/manuals/v.random.html)
- [`v.what.rast`](https://grass.osgeo.org/grass-devel/manuals/v.what.rast.html)
- [`s.sample`](https://grass.osgeo.org/grass-devel/manuals/s.sample.html)

---

## Authors

James Darrell McCauley when he was at: Agricultural
Engineering Purdue
University
Updated for GRASS 5.0 by Eric G. Miller Updated for GRASS 5.7 by Radim Blazek

---

## Resources

- [Official v.sample manual](https://grass.osgeo.org/grass-devel/manuals/v.sample.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/v.sample.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
