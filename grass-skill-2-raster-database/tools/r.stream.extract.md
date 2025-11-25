# r.stream.extract

**Category**: raster

## Description

Performs stream network extraction.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_stream_extract(elevation,accumulation=None,depression=None,threshold,d8cut=None,mexp=0,stream_length=0,memory=300,stream_raster=None,stream_vector=None,direction=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`elevation : str | np.ndarray, required`**
   - Name of input elevation raster map
   - Used as: input, raster, name

2. **`accumulation : str | np.ndarray, optional`**
   - Name of input accumulation raster map
   - Stream extraction will use provided accumulation instead of calculating it anew
   - Used as: input, raster, name

3. **`depression : str | np.ndarray, optional`**
   - Name of input raster map with real depressions
   - Streams will not be routed out of real depressions
   - Used as: input, raster, name

4. **`threshold : float, required`**
   - Minimum flow accumulation for streams
   - Must be > 0

5. **`d8cut : float, optional`**
   - Use SFD above this threshold
   - If accumulation is larger than d8cut, SFD is used instead of MFD. Applies only if no accumulation map is given.

6. **`mexp : float, optional`**
   - Montgomery exponent for slope, disabled with 0
   - Montgomery: accumulation is multiplied with pow(slope,mexp) and then compared with threshold
   - Default: 0

7. **`stream_length : int, optional`**
   - Delete stream segments shorter than stream_length cells
   - Applies only to first-order stream segments (springs/stream heads)
   - Default: 0

8. **`memory : int, optional`**
   - Maximum memory to be used (in MB)
   - Cache size for raster rows
   - Used as: memory in MB

9. **`stream_raster : str | type(np.ndarray) | type(np.array) | type(gs.array.array), optional`**
   - Name for output raster map with unique stream ids
   - Used as: output, raster, name

10. **`stream_vector : str, optional`**
   - Name for output vector map with unique stream ids
   - Used as: output, vector, name

11. **`direction : str | type(np.ndarray) | type(np.array) | type(gs.array.array), optional`**
   - Name for output raster map with flow direction
   - Used as: output, raster, name

12. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

13. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

14. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

15. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 15 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/r.stream.extract.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | np.ndarray | tuple[np.ndarray] | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned. If an array type (e.g., np.ndarray) is used for one of the raster outputs, the result will be an array and will have the shape corresponding to the computational region. If an array type is used for more than one raster output, the result will be a tuple of arrays.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

r.stream.extract extracts streams in both raster and vector format
from a required input elevation map and optional input accumulation map.

---

## See Also

Related tools:
- [`r.mapcalc`](https://grass.osgeo.org/grass-devel/manuals/r.mapcalc.html)
- [`r.param.scale`](https://grass.osgeo.org/grass-devel/manuals/r.param.scale.html)
- [`r.stream.channel`](https://grass.osgeo.org/grass-devel/manuals/r.stream.channel.html)
- [`r.stream.distance`](https://grass.osgeo.org/grass-devel/manuals/r.stream.distance.html)
- [`r.stream.order`](https://grass.osgeo.org/grass-devel/manuals/r.stream.order.html)
- [`r.stream.segment`](https://grass.osgeo.org/grass-devel/manuals/r.stream.segment.html)
- [`r.stream.slope`](https://grass.osgeo.org/grass-devel/manuals/r.stream.slope.html)
- [`r.stream.snap`](https://grass.osgeo.org/grass-devel/manuals/r.stream.snap.html)
- [`r.stream.stats`](https://grass.osgeo.org/grass-devel/manuals/r.stream.stats.html)
- [`r.terraflow`](https://grass.osgeo.org/grass-devel/manuals/r.terraflow.html)
- [`r.thin`](https://grass.osgeo.org/grass-devel/manuals/r.thin.html)
- [`r.to.vect`](https://grass.osgeo.org/grass-devel/manuals/r.to.vect.html)
- [`r.watershed`](https://grass.osgeo.org/grass-devel/manuals/r.watershed.html)

---

## Resources

- [Official r.stream.extract manual](https://grass.osgeo.org/grass-devel/manuals/r.stream.extract.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.stream.extract.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
