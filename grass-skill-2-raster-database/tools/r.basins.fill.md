# r.basins.fill

**Category**: raster

## Description

Generates watershed subbasins raster map.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_basins_fill(cnetwork,tnetwork,output,number,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`cnetwork : str | np.ndarray, required`**
   - Name of input coded stream network raster map
   - Used as: input, raster, name

2. **`tnetwork : str | np.ndarray, required`**
   - Name of input thinned ridge network raster map
   - Used as: input, raster, name

3. **`output : str | type(np.ndarray) | type(np.array) | type(gs.array.array), required`**
   - Name for output raster map
   - Used as: output, raster, name

4. **`number : int, required`**
   - Number of passes through the dataset

5. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

6. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

7. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

8. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None

### Returns

result : grass.tools.support.ToolResult | np.ndarray | tuple[np.ndarray] | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned. If an array type (e.g., np.ndarray) is used for one of the raster outputs, the result will be an array and will have the shape corresponding to the computational region. If an array type is used for more than one raster output, the result will be a tuple of arrays.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

r.basins.fill generates a raster map layer depicting subbasins, based
on input raster map layers for the coded stream network (where each
channel segment has been "coded" with a unique category value) and for
the ridges within a given watershed. The raster map layer depicting
ridges should include the ridge which defines the perimeter of the
watershed. The coded stream network can be generated as part of the r.watershed program, but the map layer of ridges
will need to be created by hand (for example, through digitizing done in wxGUI vector digitizer ).

The resulting output raster map layer will code the subbasins with
category values matching those of the channel segments passing through
them. A user-supplied number of passes through the data is made in an
attempt to fill in these subbasins. If the resulting map layer from this
program appears to have holes within a subbasin, the program should be
rerun with a higher number of passes.

---

## See Also

Related tools:
- [`r.basins.fill`](https://grass.osgeo.org/grass-devel/manuals/r.basins.fill.html)
- [`r.watershed`](https://grass.osgeo.org/grass-devel/manuals/r.watershed.html)

---

## Authors

Dale White, Dept. of Geography, Pennsylvania State University Larry Band, Dept. of Geography, University of Toronto, Canada

---

## Resources

- [Official r.basins.fill manual](https://grass.osgeo.org/grass-devel/manuals/r.basins.fill.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.basins.fill.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
