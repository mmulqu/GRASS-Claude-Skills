# r.region

**Category**: raster

## Description

Sets the boundary definitions for a raster map.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_region(map,region=None,raster=None,vector=None,n=None,s=None,e=None,w=None,align=None,flags=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`map : str | np.ndarray, required`**
   - Name of raster map to change
   - Used as: input, raster, name

2. **`region : str, optional`**
   - Set region from named region
   - Used as: input, region, name

3. **`raster : str | np.ndarray, optional`**
   - Set region to match this raster map
   - Used as: input, raster, name

4. **`vector : str, optional`**
   - Name of vector map
   - Set region to match this vector map
   - Used as: input, vector, name

5. **`n : str, optional`**
   - Value for the northern edge
   - Used as: value

6. **`s : str, optional`**
   - Value for the southern edge
   - Used as: value

7. **`e : str, optional`**
   - Value for the eastern edge
   - Used as: value

8. **`w : str, optional`**
   - Value for the western edge
   - Used as: value

9. **`align : str | np.ndarray, optional`**
   - Raster map to align to
   - Used as: input, raster, name

10. **`flags : str, optional`**
   - Allowed values: c, d, a
   - c
   - Set from current region
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/r.region.html#__tabbed_2_3) for all details)*

11. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

12. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

13. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 13 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/r.region.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

The r.region program allows the user to manage the boundaries of a
raster map. These boundaries can be set by the user directly and/or set
from a region definition file (stored under the windows directory in
the user's current mapset), a raster or vector map, or a 3dview file.

The align parameter sets the current resolution equal to that of the
named raster map, and align the boundaries to a row and column edge in
the named map. Alignment only moves the existing boundaries outward to
the edges of the next nearest cell in the named raster map -- not to the
named map's edges. To perform the latter function, use the raster = name option.

---

## See Also

Related tools:
- [`r.support`](https://grass.osgeo.org/grass-devel/manuals/r.support.html)
- [`g.region`](https://grass.osgeo.org/grass-devel/manuals/g.region.html)
- [`v.transform`](https://grass.osgeo.org/grass-devel/manuals/v.transform.html)

---

## Resources

- [Official r.region manual](https://grass.osgeo.org/grass-devel/manuals/r.region.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.region.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
