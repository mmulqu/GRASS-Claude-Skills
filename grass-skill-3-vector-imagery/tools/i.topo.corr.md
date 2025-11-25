# i.topo.corr

**Category**: imagery

## Description

Computes topographic correction of reflectance.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.i_topo_corr(input=None,output,basemap,zenith,azimuth=None,method="c-factor",flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str | list[str], optional`**
   - Name of reflectance raster maps to be corrected topographically
   - Used as: input, raster, name

2. **`output : str | type(np.ndarray) | type(np.array) | type(gs.array.array), required`**
   - Name (flag -i) or prefix for output raster maps
   - Used as: output, raster, name

3. **`basemap : str | np.ndarray, required`**
   - Name of input base raster map (elevation or illumination)
   - Used as: input, raster, name

4. **`zenith : float, required`**
   - Solar zenith in degrees

5. **`azimuth : float, optional`**
   - Solar azimuth in degrees (only if flag -i)

6. **`method : str, optional`**
   - Topographic correction method
   - Allowed values: cosine, minnaert, c-factor, percent
   - Default: c-factor

7. **`flags : str, optional`**
   - Allowed values: i, s
   - i
   - Output sun illumination terrain model
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/i.topo.corr.html#__tabbed_2_3) for all details)*

8. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

9. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

10. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

11. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 11 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/i.topo.corr.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | np.ndarray | tuple[np.ndarray] | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned. If an array type (e.g., np.ndarray) is used for one of the raster outputs, the result will be an array and will have the shape corresponding to the computational region. If an array type is used for more than one raster output, the result will be a tuple of arrays.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

i.topo.corr is used to topographically correct reflectance from
imagery files, e.g. obtained with i.landsat.toar , using a sun
illumination terrain model. This illumination model represents the
cosine of the incident angle i , i.e. the angle between the normal to
the ground and the sun rays.

Note: If needed, the sun position can be calculated for a given date and
time with r.sunmask .

Figure showing terrain and solar angles

Using the -i flag and given an elevation basemap (metric), i.topo.corr creates a simple illumination model using the formula:

where,

For each band file, the corrected reflectance (ref_c) is calculate from
the original reflectance (ref_o) using one of the four offered methods
(one lambertian and two non-lambertian).

where, k is obtained by linear regression of ln(ref_o) = ln(ref_c) - k ln(cos_i/cos_z)

where, c is a/m from ref_o = a + m * cos_i

We can use cos_i to estimate the percent of solar incidence on the
surface, then the transformation (cos_i + 1)/2 varied from 0 (surface in
the side in opposition to the sun: infinite correction) to 1 (direct
exhibition to the sun: no correction) and the corrected reflectance can
be calculated as

---

## See Also

Related tools:
- [`i.landsat.toar`](https://grass.osgeo.org/grass-devel/manuals/i.landsat.toar.html)
- [`r.mapcalc`](https://grass.osgeo.org/grass-devel/manuals/r.mapcalc.html)
- [`r.sun`](https://grass.osgeo.org/grass-devel/manuals/r.sun.html)
- [`r.sunmask`](https://grass.osgeo.org/grass-devel/manuals/r.sunmask.html)

---

## Resources

- [Official i.topo.corr manual](https://grass.osgeo.org/grass-devel/manuals/i.topo.corr.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/i.topo.corr.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
