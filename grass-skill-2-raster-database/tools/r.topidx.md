# r.topidx

**Category**: raster

## Description

Creates a topographic index (wetness index) raster map from an elevation raster map.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_topidx(input,output,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str | np.ndarray, required`**
   - Name of input elevation raster map
   - Used as: input, raster, name

2. **`output : str | type(np.ndarray) | type(np.array) | type(gs.array.array), required`**
   - Name for output topographic index raster map
   - Used as: output, raster, name

3. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

4. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

5. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

6. **`superquiet : bool, optional`**
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

r.topidx creates topographic index (wetness index), ln(a/tan(beta)),
map from elevation map where

Input maps may have NULL values. For example, if you have a raster mask
set for a watershed (using basin map from r.water.outlet ), the
following command will create a masked elevation map (belev):

r.stats -Anc prints out averaged statistics for topographic index.

Lat/long projects are not supported. If data is not projected, please
create a new project with a projected coordinate reference system and
reproject the data there. Please run r.topidx from that project.

---

## See Also

Related tools:
- [`r.topmodel`](https://grass.osgeo.org/grass-devel/manuals/r.topmodel.html)
- [`r.water.outlet`](https://grass.osgeo.org/grass-devel/manuals/r.water.outlet.html)
- [`r.mapcalc`](https://grass.osgeo.org/grass-devel/manuals/r.mapcalc.html)

---

## Authors

Huidae Cho Hydro Laboratory, Kyungpook National University, South Korea
Based on GRIDATB.FOR by Keith Beven.

---

## Resources

- [Official r.topidx manual](https://grass.osgeo.org/grass-devel/manuals/r.topidx.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.topidx.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
