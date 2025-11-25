# i.emissivity

**Category**: imagery

## Description

Computes emissivity from NDVI, generic method for sparse land.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.i_emissivity(input,output,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str | np.ndarray, required`**
   - Name of the NDVI map [-]
   - Used as: input, raster, name

2. **`output : str | type(np.ndarray) | type(np.array) | type(gs.array.array), required`**
   - Name of the output emissivity layer
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

i.emissivity calculates the emissivity in the longwave radiation
spectrum, according to the semi-empirical equation related to NDVI by
Caselles et al. (1997), valid in the NDVI range of 0.16 to 0.74
(Bastiaanssen, 1995).

Caselles et al. (1997) give reference (in Table 3 and Figure 2) to both
the NDVI range used (0.15 - 0.71) and the corresponding emissivity range
used (0.97 - 0.99).

The emissivity is the efficiency of longwave energy returning to the
atmosphere from the skin surface. The skin surface receives heat from
the thermal infrared radiation of the Sun, through atmospheric
interaction. A part is returned to the atmosphere fastly, and another
part is kept in the surface skin to be returned later. In more
scientific terms, the grey body radiation is equal to the black body
radiation times the emissivity.

---

## See Also

Related tools:
- [`i.eb.netrad`](https://grass.osgeo.org/grass-devel/manuals/i.eb.netrad.html)

---

## Resources

- [Official i.emissivity manual](https://grass.osgeo.org/grass-devel/manuals/i.emissivity.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/i.emissivity.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
