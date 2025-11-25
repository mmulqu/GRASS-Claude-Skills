# r.circle

**Category**: raster

## Description

Creates a raster map containing concentric rings around a given point.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_circle(output,coordinates,min=None,max=None,multiplier=None,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`output : str | type(np.ndarray) | type(np.array) | type(gs.array.array), required`**
   - Name for output raster map
   - Used as: output, raster, name

2. **`coordinates : tuple[float, float] | list[float] | str, required`**
   - The coordinate of the center (east,north)
   - Used as: input, coords, east,north

3. **`min : float, optional`**
   - Minimum radius for ring/circle map (in meters)

4. **`max : float, optional`**
   - Maximum radius for ring/circle map (in meters)

5. **`multiplier : float, optional`**
   - Data value multiplier

6. **`flags : str, optional`**
   - Allowed values: b
   - b
   - Generate binary raster map

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

result : grass.tools.support.ToolResult | np.ndarray | tuple[np.ndarray] | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned. If an array type (e.g., np.ndarray) is used for one of the raster outputs, the result will be an array and will have the shape corresponding to the computational region. If an array type is used for more than one raster output, the result will be a tuple of arrays.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

r.circle creates an output raster map centered on the x,y values
specified with the coordinate parameter, out to the edge of the
current region. The output cell values increase linearly from the
specified center. The min and max parameters control the inner and
outer output raster map radii, respectively.

The mult parameter can be used to multiply the output raster cells by
a common factor. Note that this parameter does not affect the output
raster position or size; only the z-values are changed with this
parameter.

Binary-output raster maps (solid circles of one value) can be created
with the -b flag. Raster maps so created can be used to create
binary filters for use in i.ifft (inverse Fourier transformations;
apply filter with r.mask ).

---

## See Also

Related tools:
- [`g.region`](https://grass.osgeo.org/grass-devel/manuals/g.region.html)
- [`g.remove`](https://grass.osgeo.org/grass-devel/manuals/g.remove.html)
- [`g.rename`](https://grass.osgeo.org/grass-devel/manuals/g.rename.html)
- [`i.fft`](https://grass.osgeo.org/grass-devel/manuals/i.fft.html)
- [`i.ifft`](https://grass.osgeo.org/grass-devel/manuals/i.ifft.html)
- [`r.mask`](https://grass.osgeo.org/grass-devel/manuals/r.mask.html)

---

## Authors

Bill Brown, U.S. Army Construction Engineering Research Laboratory Additional flag/min/max parameter by Markus Neteler, University of
Hannover

---

## Resources

- [Official r.circle manual](https://grass.osgeo.org/grass-devel/manuals/r.circle.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.circle.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
