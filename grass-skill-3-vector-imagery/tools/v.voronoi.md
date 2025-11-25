# v.voronoi

**Category**: vector

## Description

Creates a Voronoi diagram constrained to the extents of the current region from an input vector map containing points or centroids.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.v_voronoi(input,layer="-1",output,smoothness=0.25,thin=-1,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
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

4. **`smoothness : float, optional`**
   - Factor for output smoothness
   - Applies to input areas only. Smaller values produce smoother output but can cause numerical instability.
   - Default: 0.25

5. **`thin : float, optional`**
   - Maximum dangle length of skeletons
   - Applies only to skeleton extraction. Default = -1 will extract the center line.
   - Default: -1

6. **`flags : str, optional`**
   - Allowed values: a, s, l, t
   - a
   - Create Voronoi diagram for input areas
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/v.voronoi.html#__tabbed_2_3) for all details)*

7. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

8. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

9. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

10. **`superquiet : bool, optional`**
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

v.voronoi creates a Voronoi diagram (Thiessen polygons) from points or
centroids.

The bounds of the output map are limited by the current region (see g.region ).

The -a flag can be used to create a Voronoi diagram for areas.

The -s flag can be used to extract the center line of areas or
skeletons of areas with thin >= 0. Smaller values for the thin option will preserve more detail, while negative values will extract
only the center line.

---

## See Also

Related tools:
- [`g.region`](https://grass.osgeo.org/grass-devel/manuals/g.region.html)
- [`v.delaunay`](https://grass.osgeo.org/grass-devel/manuals/v.delaunay.html)
- [`v.hull`](https://grass.osgeo.org/grass-devel/manuals/v.hull.html)

---

## Authors

James Darrell McCauley, Purdue University GRASS 5 update, improvements: Andrea Aime ,
Modena, Italy GRASS 5.7 update: Radim Blazek Markus Metz

---

## Resources

- [Official v.voronoi manual](https://grass.osgeo.org/grass-devel/manuals/v.voronoi.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/v.voronoi.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
