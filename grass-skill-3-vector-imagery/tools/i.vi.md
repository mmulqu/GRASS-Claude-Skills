# i.vi

**Category**: imagery

## Description

Calculates different types of vegetation indices. Uses red and nir bands mostly, and some indices require additional bands.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.i_vi(output,viname="ndvi",red=None,nir=None,green=None,blue=None,band5=None,band7=None,soil_line_slope=None,soil_line_intercept=None,soil_noise_reduction=None,storage_bit=8,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`output : str | type(np.ndarray) | type(np.array) | type(gs.array.array), required`**
   - Name for output raster map
   - Used as: output, raster, name

2. **`viname : str, required`**
   - Type of vegetation index
   - Used as: type
   - Allowed values: arvi, ci, dvi, evi, evi2, gvi, gari, gemi, ipvi, msavi, msavi2, ndvi, ndwi, pvi, savi, sr, vari, wdvi
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/i.vi.html#__tabbed_2_3) for all details)*

3. **`red : str | np.ndarray, optional`**
   - Name of input red channel surface reflectance map
   - Range: [0.0;1.0]
   - Used as: input, raster, name

4. **`nir : str | np.ndarray, optional`**
   - Name of input nir channel surface reflectance map
   - Range: [0.0;1.0]
   - Used as: input, raster, name

5. **`green : str | np.ndarray, optional`**
   - Name of input green channel surface reflectance map
   - Range: [0.0;1.0]
   - Used as: input, raster, name

6. **`blue : str | np.ndarray, optional`**
   - Name of input blue channel surface reflectance map
   - Range: [0.0;1.0]
   - Used as: input, raster, name

7. **`band5 : str | np.ndarray, optional`**
   - Name of input 5th channel surface reflectance map
   - Range: [0.0;1.0]
   - Used as: input, raster, name

8. **`band7 : str | np.ndarray, optional`**
   - Name of input 7th channel surface reflectance map
   - Range: [0.0;1.0]
   - Used as: input, raster, name

9. **`soil_line_slope : float, optional`**
   - Value of the slope of the soil line (MSAVI and PVI only)

10. **`soil_line_intercept : float, optional`**
   - Value of the intercept of the soil line (MSAVI only)

11. **`soil_noise_reduction : float, optional`**
   - Value of the factor of reduction of soil noise (MSAVI only)

12. **`storage_bit : int, optional`**
   - Maximum bits for digital numbers
   - If data is in Digital Numbers (i.e. integer type), give the max bits (i.e. 8 for Landsat -> [0-255])
   - Allowed values: 7, 8, 10, 16

13. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

14. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

15. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

16. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 16 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/i.vi.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | np.ndarray | tuple[np.ndarray] | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned. If an array type (e.g., np.ndarray) is used for one of the raster outputs, the result will be an array and will have the shape corresponding to the computational region. If an array type is used for more than one raster output, the result will be a tuple of arrays.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

i.vi calculates vegetation indices based on biophysical parameters.

Vegetation Indices are often considered the entry point of remote
sensing for Earth land monitoring. They are suffering from their
success, in terms that often people tend to harvest satellite images
from online sources and use them directly in this module.

From Digital number to Radiance: Satellite imagery is commonly stored in Digital Number (DN) for storage
purposes; e.g., Landsat5 data is stored in 8bit values (ranging from 0
to 255), other satellites maybe stored in 10 or 16 bits. If the data is
provided in DN, this implies that this imagery is "uncorrected". What
this means is that the image is what the satellite sees at its position
and altitude in space (stored in DN). This is not the signal at ground
yet. We call this data at-satellite or at-sensor. Encoded in the 8bits
(or more) is the amount of energy sensed by the sensor inside the
satellite platform. This energy is called radiance-at-sensor. Generally,
satellites image providers encode the radiance-at-sensor into 8bit (or
more) through an affine transform equation (y=ax+b). In case of using
Landsat imagery, look at the i.landsat.toar for an easy way to
transform DN to radiance-at-sensor. If using Aster data, try the i.aster.toar module.

From Radiance to Reflectance: Finally, once having obtained the radiance at sensor values, still the
atmosphere is between sensor and Earth's surface. This fact needs to be
corrected to account for the atmospheric interaction with the sun energy
that the vegetation reflects back into space. This can be done in two
ways for Landsat. The simple way is through i.landsat.toar , use e.g.
the DOS correction. The more accurate way is by using i.atcorr (which
works for many satellite sensors). Once the atmospheric correction has
been applied to the satellite data, data vales are called surface
reflectance. Surface reflectance is ranging from 0.0 to 1.0
theoretically (and absolutely). This level of data correction is the
proper level of correction to use with i.vi .

ARVI is resistant to atmospheric effects (in comparison to the NDVI) and
is accomplished by a self correcting process for the atmospheric effect
in the red channel, using the difference in the radiance between the
blue and the red channels (Kaufman and Tanre 1996).

Advantage is taken of a unique spectral feature of soil biogenic crust
containing cyanobacteria. It has been shown that the special phycobilin
pigment in cyanobacteria contributes in producing a relatively higher
reflectance in the blue spectral region than the same type of substrate
without the biogenic crust. The spectral crust index (CI) is based on
the normalized difference between the RED and the BLUE spectral values
(Karnieli, 1997, DOI: 10.1080/014311697218368).

The enhanced vegetation index (EVI) is an optimized index designed to
enhance the vegetation signal with improved sensitivity in high biomass
regions and improved vegetation monitoring through a de-coupling of the
canopy background signal and a reduction in atmosphere influences (Huete
A.R., Liu H.Q., Batchily K., van Leeuwen W. (1997). A comparison of
vegetation indices global set of TM images for EOS-MODIS. Remote Sensing
of Environment, 59:440-451).

A 2-band EVI (EVI2), without a blue band, which has the best similarity
with the 3-band EVI, particularly when atmospheric effects are
insignificant and data quality is good (Zhangyan Jiang ; Alfredo R.
Huete ; Youngwook Kim and Kamel Didan 2-band enhanced vegetation index
without a blue band and its application to AVHRR data. Proc. SPIE 6679,
Remote Sensing and Modeling of Ecosystems for Sustainability IV, 667905
(october 09, 2007) doi:10.1117/12.734933 ).

The formula was actually defined: Gitelson, Anatoly A.; Kaufman, Yoram
J.; Merzlyak, Mark N. (1996) Use of a green channel in remote sensing of
global vegetation from EOS- MODIS, Remote Sensing of Environment 58 (3),
289-298. doi:10.1016/s0034-4257(96)00072-7

where a is the soil line intercept, s is the soil line slope, and X is
an adjustment factor which is set to minimize soil noise (0.08 in
original papers).

This index is suitable to detect water bodies.

The water content of leaves can be estimated with another NDWI (after
Gao, 1996):

This index is important for monitoring vegetation health (not
implemented).

VARI was designed to
introduce an atmospheric self-correction (Gitelson A.A., Kaufman Y.J.,
Stark R., Rundquist D., 2002. Novel algorithms for estimation of
vegetation fraction Remote Sensing of Environment (80), pp76-87.)

---

## See Also

Related tools:
- [`i.albedo`](https://grass.osgeo.org/grass-devel/manuals/i.albedo.html)
- [`i.aster.toar`](https://grass.osgeo.org/grass-devel/manuals/i.aster.toar.html)
- [`i.landsat.toar`](https://grass.osgeo.org/grass-devel/manuals/i.landsat.toar.html)
- [`i.atcorr`](https://grass.osgeo.org/grass-devel/manuals/i.atcorr.html)
- [`i.tasscap`](https://grass.osgeo.org/grass-devel/manuals/i.tasscap.html)

---

## Authors

Baburao Kamble, Asian Institute of Technology, Thailand Yann Chemin, Asian Institute of Technology, Thailand

---

## Resources

- [Official i.vi manual](https://grass.osgeo.org/grass-devel/manuals/i.vi.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/i.vi.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
