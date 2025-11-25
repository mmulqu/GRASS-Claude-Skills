# r.null

**Category**: raster

## Description

Manages NULL-values of given raster map.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_null(map,setnull=None,null=None,flags=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`map : str | np.ndarray, required`**
   - Name of raster map for which to edit null values
   - Used as: input, raster, name

2. **`setnull : str | list[str], optional`**
   - List of cell values to be set to NULL
   - Used as: val[-val]

3. **`null : float, optional`**
   - The value to replace the null value by

4. **`flags : str, optional`**
   - Allowed values: f, i, n, c, r, z
   - f
   - Only do the work if the map is floating-point
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/r.null.html#__tabbed_2_3) for all details)*

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

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

The function of r.null is to explicitly create the NULL-value bitmap
file. The intended usage is to update maps that do not have a NULL-value
bitmap file (i.e. to indicate for each pixel if zero is a valid value or
is to be considered as NULL, i.e. no data value). The module does not
work with reclassified or external maps.

The design is flexible. Ranges of values can be set to NULL and/or the
NULL value can be eliminated and replace with a specified value.

The setnull parameter is used to specify values in the ranges to be
set to NULL. A range is either a single value (e.g., 5.3), or a pair of
values (e.g., 4.76-34.56). Existing NULL-values are left NULL, unless
the null argument is requested.

The null parameter eliminates the NULL value and replaces it with
value. This argument is applied only to existing NULL values, and not to
the NULLs created by the setnull argument.

---

## See Also

Related tools:
- [`r.compress`](https://grass.osgeo.org/grass-devel/manuals/r.compress.html)
- [`r.support`](https://grass.osgeo.org/grass-devel/manuals/r.support.html)
- [`r.quant`](https://grass.osgeo.org/grass-devel/manuals/r.quant.html)

---

## Resources

- [Official r.null manual](https://grass.osgeo.org/grass-devel/manuals/r.null.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.null.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
