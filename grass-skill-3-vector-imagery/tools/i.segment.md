# i.segment

**Category**: imagery

## Description

Identifies segments (objects) from imagery data.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.i_segment(group,output,band_suffix=None,threshold,radius=1.5,hr=None,method="region_growing",similarity="euclidean",minsize=1,memory=300,iterations=None,seeds=None,bounds=None,goodness=None,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`group : str | list[str], required`**
   - Name of input imagery group or raster maps
   - Used as: input, raster, name

2. **`output : str | type(np.ndarray) | type(np.array) | type(gs.array.array), required`**
   - Name for output raster map
   - Used as: output, raster, name

3. **`band_suffix : str | type(np.ndarray) | type(np.array) | type(gs.array.array), optional`**
   - Suffix for output bands with modified band values
   - Name for output raster map
   - Used as: output, raster, name

4. **`threshold : float, required`**
   - Difference threshold between 0 and 1
   - Threshold = 0 merges only identical segments; threshold = 1 merges all

5. **`radius : float, optional`**
   - Spatial radius in number of cells
   - Must be >= 1, only cells within spatial bandwidth are considered for mean shift
   - Default: 1.5

6. **`hr : float, optional`**
   - Range (spectral) bandwidth [0, 1]
   - Only cells within range (spectral) bandwidth are considered for mean shift. Range bandwidth is used as conductance parameter for adaptive bandwidth

7. **`method : str, optional`**
   - Segmentation method
   - Allowed values: region_growing, mean_shift
   - Default: region_growing

8. **`similarity : str, optional`**
   - Similarity calculation method
   - Allowed values: euclidean, manhattan
   - Default: euclidean

9. **`minsize : int, optional`**
   - Minimum number of cells in a segment
   - The final step will merge small segments with their best neighbor
   - Allowed values: 1-100000

10. **`memory : int, optional`**
   - Maximum memory to be used (in MB)
   - Cache size for raster rows
   - Used as: memory in MB

11. **`iterations : int, optional`**
   - Maximum number of iterations

12. **`seeds : str | np.ndarray, optional`**
   - Name for input raster map with starting seeds
   - Used as: input, raster, name

13. **`bounds : str | np.ndarray, optional`**
   - Name of input bounding/constraining raster map
   - Must be integer values, each area will be segmented independent of the others
   - Used as: input, raster, name

14. **`goodness : str | type(np.ndarray) | type(np.array) | type(gs.array.array), optional`**
   - Name for output goodness of fit estimate map
   - Used as: output, raster, name

15. **`flags : str, optional`**
   - Allowed values: d, w, a, p
   - d
   - Use 8 neighbors (3x3 neighborhood) instead of the default 4 neighbors for each pixel
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/i.segment.html#__tabbed_2_3) for all details)*

16. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

17. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

18. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

19. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 19 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/i.segment.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | np.ndarray | tuple[np.ndarray] | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned. If an array type (e.g., np.ndarray) is used for one of the raster outputs, the result will be an array and will have the shape corresponding to the computational region. If an array type is used for more than one raster output, the result will be a tuple of arrays.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

i.segment identifies segments (objects) from imagery data.

Image segmentation or object recognition is the process of grouping
similar pixels into unique segments, also referred to as objects.
Boundary and region based algorithms are described in the literature,
currently a region growing and merging algorithm is implemented. Each
object found during the segmentation process is given a unique ID and is
a collection of contiguous pixels meeting some criteria. Note the
contrast with image classification where all pixels similar to each
other are assigned to the same class and do not need to be contiguous.
The image segmentation results can be useful on their own, or used as a
preprocessing step for image classification. The segmentation
preprocessing step can reduce noise and speed up the classification.

---

## See Also

Related tools:
- [`i.segment.stats`](https://grass.osgeo.org/grass-devel/manuals/i.segment.stats.html)
- [`i.segment.uspo`](https://grass.osgeo.org/grass-devel/manuals/i.segment.uspo.html)
- [`i.segment.hierarchical`](https://grass.osgeo.org/grass-devel/manuals/i.segment.hierarchical.html)
- [`g.gui.iclass`](https://grass.osgeo.org/grass-devel/manuals/g.gui.iclass.html)
- [`i.group`](https://grass.osgeo.org/grass-devel/manuals/i.group.html)
- [`i.maxlik`](https://grass.osgeo.org/grass-devel/manuals/i.maxlik.html)
- [`i.smap`](https://grass.osgeo.org/grass-devel/manuals/i.smap.html)
- [`r.kappa`](https://grass.osgeo.org/grass-devel/manuals/r.kappa.html)

---

## Authors

Eric Momsen - North Dakota State University Markus Metz (GSoC Mentor)

---

## Resources

- [Official i.segment manual](https://grass.osgeo.org/grass-devel/manuals/i.segment.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/i.segment.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
