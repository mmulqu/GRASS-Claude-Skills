# i.aster.toar

**Category**: imagery

## Description

Calculates Top of Atmosphere Radiance/Reflectance/Brightness Temperature from ASTER DN.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.i_aster_toar(input,dayofyear,sun_elevation,output,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str | list[str], required`**
   - Names of ASTER DN layers (15 layers)
   - Used as: input, raster, name

2. **`dayofyear : float, required`**
   - Day of Year of satellite overpass [0-366]

3. **`sun_elevation : float, required`**
   - Sun elevation angle (degrees, < 90.0)

4. **`output : str | type(np.ndarray) | type(np.array) | type(gs.array.array), required`**
   - Base name of the output layers (will add .x)
   - Used as: output, raster, name

5. **`flags : str, optional`**
   - Allowed values: r, a, b, c, d, e
   - r
   - Output is radiance (W/m2)
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/i.aster.toar.html#__tabbed_2_3) for all details)*

6. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

7. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

8. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

9. **`superquiet : bool, optional`**
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

i.aster.toar calculates the Top Of Atmosphere (TOA) reflectance for
Terra-ASTER L1B in the visible, NIR and SWIR bands (9+1 bands) and
brightness temperature for the TIR bands (5 bands), all from L1B DN
values. It is useful to apply after import of original ASTER imagery
that is generally in standard DN values range.

The order of input bands is

in one comma-separated list.

---

## See Also

Related tools:
- [`i.landsat.toar`](https://grass.osgeo.org/grass-devel/manuals/i.landsat.toar.html)
- [`r.in.aster`](https://grass.osgeo.org/grass-devel/manuals/r.in.aster.html)

---

## Resources

- [Official i.aster.toar manual](https://grass.osgeo.org/grass-devel/manuals/i.aster.toar.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/i.aster.toar.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
