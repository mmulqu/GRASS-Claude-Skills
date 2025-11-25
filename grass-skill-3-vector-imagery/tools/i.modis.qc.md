# i.modis.qc

**Category**: imagery

## Description

Extracts quality control parameters from MODIS QC layers.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.i_modis_qc(input,output,productname,qcname,band=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str | np.ndarray, required`**
   - Name of input surface reflectance QC layer [bit array]
   - Used as: input, raster, name

2. **`output : str | type(np.ndarray) | type(np.array) | type(gs.array.array), required`**
   - Name for output QC type classification layer
   - Used as: output, raster, name

3. **`productname : str, required`**
   - Name of MODIS product type
   - Allowed values: mod09Q1, mod09A1, mod09A1s, mod09GA, mod09GAs, mod09CMG, mod09CMGs, mod09CMGi, mod11A1, mod11A2, mod13A2, mcd43B2, mcd43B2q, mod13Q1
   - mod09Q1: surf. refl. 250m 8-days
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/i.modis.qc.html#__tabbed_2_3) for all details)*

4. **`qcname : str, required`**
   - Name of QC type to extract
   - Allowed values: adjcorr, atcorr, cloud, data_quality, diff_orbit_from_500m, modland_qa, mandatory_qa_11A1, data_quality_flag_11A1, emis_error_11A1, lst_error_11A1, data_quality_flag_11A2, emis_error_11A2, mandatory_qa_11A2, lst_error_11A2, aerosol_quantity, brdf_correction_performed, cirrus_detected, cloud_shadow, cloud_state, internal_cloud_algorithm, internal_fire_algorithm, internal_snow_mask, land_water, mod35_snow_ice, pixel_adjacent_to_cloud, salt_pan, icm_cloudy, icm_clear, icm_high_clouds, icm_low_clouds, icm_snow, icm_fire, icm_sun_glint, icm_dust, icm_cloud_shadow, icm_pixel_is_adjacent_to_cloud, icm_cirrus, icm_pan_flag, icm_criteria_for_aerosol_retrieval, icm_aot_has_clim_val, modland_qa, vi_usefulness, aerosol_quantity, pixel_adjacent_to_cloud, brdf_correction_performed, mixed_clouds, land_water, possible_snow_ice, possible_shadow, platform, land_water, sun_z_angle_at_local_noon, brdf_correction_performed, modland_qa, vi_usefulness, aerosol_quantity, pixel_adjacent_to_cloud, brdf_correction_performed, mixed_clouds, land_water, possible_snow_ice, possible_shadow
   - adjcorr: mod09: Adjacency Correction
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/i.modis.qc.html#__tabbed_2_3) for all details)*

5. **`band : str, optional`**
   - Band number of MODIS product (mod09Q1=[1,2],mod09A1=[1-7],m[o/y]d09GA=[1-7],m[o/y]d09CMG=[1-7], mcd43B2q=[1-7])
   - Allowed values: 1, 2, 3, 4, 5, 6, 7
   - 1: Band 1: Red
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/i.modis.qc.html#__tabbed_2_3) for all details)*

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

i.modis.qc extracts Requested Quality Assessment flags from the
following MODIS products: MOD09A1, MOD09Q1, MOD11A1, MOD11A2, MOD13A2,
MOD13Q1, MCD43B2. This does include MOD09A1 QA_state_500m layer (see
Notes). Added MOD09GA support in 2016, it follows MOD09A1 and its StateQA, but
does not have BRDF State QA, instead has Salt Pan State QA.

bits[0-3][4-7][8-11][12-15][16-19][20-23][24-27]

---

## See Also

Related tools:
- [`i.vi`](https://grass.osgeo.org/grass-devel/manuals/i.vi.html)

---

## Resources

- [Official i.modis.qc manual](https://grass.osgeo.org/grass-devel/manuals/i.modis.qc.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/i.modis.qc.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
