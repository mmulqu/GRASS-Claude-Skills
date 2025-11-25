# r.uslek

**Category**: raster

## Description

Computes USLE Soil Erodibility Factor (K).

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_uslek(psand,pclay,psilt,pomat,output,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`psand : str | np.ndarray, required`**
   - Name of soil sand fraction raster map [0.0-1.0]
   - Used as: input, raster, name

2. **`pclay : str | np.ndarray, required`**
   - Name of soil clay fraction raster map [0.0-1.0]
   - Used as: input, raster, name

3. **`psilt : str | np.ndarray, required`**
   - Name of soil silt fraction raster map [0.0-1.0]
   - Used as: input, raster, name

4. **`pomat : str | np.ndarray, required`**
   - Name of soil organic matter raster map [0.0-1.0]
   - Used as: input, raster, name

5. **`output : str | type(np.ndarray) | type(np.array) | type(gs.array.array), required`**
   - Name for output USLE K factor raster map [t.ha.hr/ha.MJ.mm]
   - Used as: output, raster, name

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

r.uslek calculates the USLE K factor, that is the Soil Erodibility
Factor. It takes input of soil texture classes (sand, clay, silt) and
organic matter, all in range of [0.0-1.0]. The FAO World Soil CD
documentation was used to produce the conversion system between soil
textures and soil classes. The soil classes are in number of 12 and
apparently come from a USDA publication of 1951 (p.209). Once the soil
classes have been identified (by vector cross-products tests), a general
conversion table was applied for transforming soil classes into K
factor.

---

## See Also

Related tools:
- [`r.usler`](https://grass.osgeo.org/grass-devel/manuals/r.usler.html)
- [`r.watershed`](https://grass.osgeo.org/grass-devel/manuals/r.watershed.html)

---

## Resources

- [Official r.uslek manual](https://grass.osgeo.org/grass-devel/manuals/r.uslek.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.uslek.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
