# r.thin

**Category**: raster

## Description

Thins non-null cells that denote linear features in a raster map layer.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_thin(input,output,iterations=200,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str | np.ndarray, required`**
   - Name of input raster map
   - Used as: input, raster, name

2. **`output : str | type(np.ndarray) | type(np.array) | type(gs.array.array), required`**
   - Name for output raster map
   - Used as: output, raster, name

3. **`iterations : int, optional`**
   - Maximal number of iterations
   - Default: 200

4. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

5. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

6. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

7. **`superquiet : bool, optional`**
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

r.thin scans the named input raster map layer and thins non-NULL
cells that denote linear features into linear features having a single
cell width. Raster lines often need to be thinned (skeletonizing raster
features) to a single pixel width before they can be transformed to
vector data.

r.thin will thin only the non-NULL (no data) raster cells of the named input raster map layer within the current geographic region settings.
The cell width of the thinned output raster map layer will be equal to
the cell resolution of the currently set geographic region. All of the
thinned linear features will have the width of a single cell.

r.thin will create a new output raster data file containing the
thinned linear features. r.thin assumes that linear features are
encoded with positive values on a background of NULL's in the input raster data file, hence it creates a NULL/1 output map.

---

## See Also

Related tools:
- [`g.region`](https://grass.osgeo.org/grass-devel/manuals/g.region.html)
- [`r.to.vect`](https://grass.osgeo.org/grass-devel/manuals/r.to.vect.html)
- [`v.clean`](https://grass.osgeo.org/grass-devel/manuals/v.clean.html)
- [`v.build`](https://grass.osgeo.org/grass-devel/manuals/v.build.html)

---

## Authors

Olga Waupotitsch, U.S.Army Construction Engineering Research Laboratory
The code for finding the bounding box as well as input/output code was
written by Mike Baba (DBA Systems, 1990) and Jean Ezell (USACERL, 1988).

---

## Resources

- [Official r.thin manual](https://grass.osgeo.org/grass-devel/manuals/r.thin.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.thin.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
