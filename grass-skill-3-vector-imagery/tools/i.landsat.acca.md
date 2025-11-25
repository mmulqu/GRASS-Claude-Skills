# i.landsat.acca

**Category**: imagery

## Description

Performs Landsat TM/ETM+ Automatic Cloud Cover Assessment (ACCA).

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.i_landsat_acca(input,output,b56composite=225.,b45ratio=1.,histogram=100,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str | np.ndarray, required`**
   - Base name of input raster bands
   - Example: 'B.' for B.1, B.2, ...
   - Used as: input, raster, basename

2. **`output : str | type(np.ndarray) | type(np.array) | type(gs.array.array), required`**
   - Name for output raster map
   - Used as: output, raster, name

3. **`b56composite : float, optional`**
   - B56composite (step 6)
   - Default: 225.

4. **`b45ratio : float, optional`**
   - B45ratio: Desert detection (step 10)
   - Default: 1.

5. **`histogram : int, optional`**
   - Number of classes in the cloud temperature histogram
   - Default: 100

6. **`flags : str, optional`**
   - Allowed values: 5, f, x, 2, s
   - 5
   - Data is Landsat-5 TM
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/i.landsat.acca.html#__tabbed_2_3) for all details)*

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

i.landsat.acca implements the Automated Cloud-Cover Assessment (ACCA) Algorithm from Irish (2000) with the constant values for pass
filter one from Irish et al. (2006). To do this, it needs Landsat band
numbers 2, 3, 4, 5, and 6 (or band 61 for Landsat-7 ETM+) which have
already been processed from DN into reflectance and band-6 temperature
with i.landsat.toar ).

The ACCA algorithm gives good results over most of the planet with the
exception of ice sheets because ACCA operates on the premise that clouds
are colder than the land surface they cover. The algorithm was designed
for Landsat-7 ETM+ but because reflectance is used it is also useful for
Landsat-4/5 TM.

---

## See Also

Related tools:
- [`i.atcorr`](https://grass.osgeo.org/grass-devel/manuals/i.atcorr.html)
- [`i.landsat.toar`](https://grass.osgeo.org/grass-devel/manuals/i.landsat.toar.html)

---

## Resources

- [Official i.landsat.acca manual](https://grass.osgeo.org/grass-devel/manuals/i.landsat.acca.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/i.landsat.acca.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
