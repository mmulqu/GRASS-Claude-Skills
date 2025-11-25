# r.carve

**Category**: raster

## Description

Generates stream channels. Takes vector stream data, transforms it to raster and subtracts depth from the output DEM.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_carve(raster,vector,output,points=None,width=None,depth=None,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`raster : str | np.ndarray, required`**
   - Name of input raster elevation map
   - Used as: input, raster, name

2. **`vector : str, required`**
   - Name of input vector map containing stream(s)
   - Or data source for direct OGR access
   - Used as: input, vector, name

3. **`output : str | type(np.ndarray) | type(np.array) | type(gs.array.array), required`**
   - Name for output raster map
   - Used as: output, raster, name

4. **`points : str, optional`**
   - Name for output vector map for adjusted stream points
   - Used as: output, vector, name

5. **`width : float, optional`**
   - Stream width (in meters)
   - Default is raster cell width

6. **`depth : float, optional`**
   - Additional stream depth (in meters)

7. **`flags : str, optional`**
   - Allowed values: n
   - n
   - No flat areas allowed in flow direction

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


*Showing 10 of 11 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/r.carve.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | np.ndarray | tuple[np.ndarray] | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned. If an array type (e.g., np.ndarray) is used for one of the raster outputs, the result will be an array and will have the shape corresponding to the computational region. If an array type is used for more than one raster output, the result will be a tuple of arrays.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

r.carve accepts vector stream data as input, transforms them to
raster, and subtracts a default-depth + additional-depth from a DEM. If
the given width is more than 1 cell, it will carve the stream with the
given width. With the -n flag it should eliminate all flat cells
within the stream, so when and if the water gets into the stream it will
flow. The points option generates x,y,z for points which define the
stream with the z-value of the bottom of the carved-in stream. These
points can then be combined with contours to interpolate a new DEM with
better representation of valleys.

---

## See Also

Related tools:
- [`r.flow`](https://grass.osgeo.org/grass-devel/manuals/r.flow.html)
- [`r.fill.dir`](https://grass.osgeo.org/grass-devel/manuals/r.fill.dir.html)
- [`r.watershed`](https://grass.osgeo.org/grass-devel/manuals/r.watershed.html)

---

## Authors

Bill Brown (GMSL) GRASS 6 update: Brad Douglas

---

## Resources

- [Official r.carve manual](https://grass.osgeo.org/grass-devel/manuals/r.carve.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.carve.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
