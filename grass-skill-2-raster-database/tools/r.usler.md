# r.usler

**Category**: raster

## Description

Computes USLE R factor, Rainfall erosivity index.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_usler(input,output,method="morgan",overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str | np.ndarray, required`**
   - Name of annual precipitation raster map [mm/year]
   - Used as: input, raster, name

2. **`output : str | type(np.ndarray) | type(np.array) | type(gs.array.array), required`**
   - Name for output USLE R raster map [MJ.mm/ha.hr.year]
   - Used as: output, raster, name

3. **`method : str, required`**
   - Name of USLE R equation
   - Allowed values: roose,  morgan,  foster,  elswaify
   - roose: Roosle (1975)
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/r.usler.html#__tabbed_2_3) for all details)*

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

r.usler calculates USLE R factor for Rainfall erosivity. It enables
several empirical equations: Roosle (1975), Morgan (1974), Foster(1981)
and El-Swaify (1985).

---

## See Also

Related tools:
- [`r.uslek`](https://grass.osgeo.org/grass-devel/manuals/r.uslek.html)
- [`r.watershed`](https://grass.osgeo.org/grass-devel/manuals/r.watershed.html)

---

## Authors

Natialia Medvedeva, SIC-ISDC, Ashgabat, Turkmenistan Yann Chemin, SIC-ISDC, Ashgabat, Turkmenistan

---

## Resources

- [Official r.usler manual](https://grass.osgeo.org/grass-devel/manuals/r.usler.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.usler.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
