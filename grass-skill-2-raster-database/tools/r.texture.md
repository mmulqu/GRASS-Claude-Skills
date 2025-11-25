# r.texture

**Category**: raster

## Description

Generate images with textural features from a raster map.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_texture(input,output,nprocs=0,size=3,distance=1,method=None,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str | np.ndarray, required`**
   - Name of input raster map
   - Used as: input, raster, name

2. **`output : str | type(np.ndarray) | type(np.array) | type(gs.array.array), required`**
   - Name for output basename raster map(s)
   - Used as: output, raster, basename

3. **`nprocs : int, optional`**
   - Number of threads for parallel computing
   - 0: use OpenMP default; >0: use nprocs; <0: use MAX-nprocs
   - Default: 0

4. **`size : int, optional`**
   - The size of moving window (odd and >= 3)
   - Used as: value
   - Default: 3

5. **`distance : int, optional`**
   - The distance between two samples (>= 1)
   - The distance must be smaller than the size of the moving window
   - Used as: value

6. **`method : str | list[str], optional`**
   - Textural measurement method
   - Allowed values: asm, contrast, corr, var, idm, sa, sv, se, entr, dv, de, moc1, moc2

7. **`flags : str, optional`**
   - Allowed values: s, a, n
   - s
   - Separate output for each angle (0, 45, 90, 135)
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/r.texture.html#__tabbed_2_3) for all details)*

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


*Showing 10 of 11 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/r.texture.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | np.ndarray | tuple[np.ndarray] | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned. If an array type (e.g., np.ndarray) is used for one of the raster outputs, the result will be an array and will have the shape corresponding to the computational region. If an array type is used for more than one raster output, the result will be a tuple of arrays.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

r.texture creates raster maps with textural features from a
user-specified raster map layer. The module calculates textural features
based on spatial dependence matrices at 0, 45, 90, and 135 degrees.

In order to take into account the scale of the texture to be measured, r.texture allows the user to define the size of the moving window
and the distance at which to compare pixel grey values. By default the
module averages the results over the 4 orientations, but the user can
also request output of the texture variables in 4 different orientations
(flag -s ). Please note that angles are defined in degrees of east and
they increase counterclockwise, so 0 is East - West, 45 is North-East -
South-West, 90 is North - South, 135 is North-West - South-East.

The user can either chose one or several texture measures (see below for
their description) using the method parameter, or can request the
creating of maps for all available methods with the -a .

r.texture assumes grey levels ranging from 0 to 255 as input. The
input is automatically rescaled to 0 to 255 if the input map range is
outside of this range. In order to reduce noise in the input data (thus
generally reinforcing the textural features), and to speed up
processing, it is recommended that the user recode the data using
equal-probability quantization. Quantization rules for r.recode can be
generated with r.quantile -r using e.g 16 or 32 quantiles (see example
below).

---

## See Also

Related tools:
- [`i.maxlik`](https://grass.osgeo.org/grass-devel/manuals/i.maxlik.html)
- [`i.gensig`](https://grass.osgeo.org/grass-devel/manuals/i.gensig.html)
- [`i.smap`](https://grass.osgeo.org/grass-devel/manuals/i.smap.html)
- [`i.gensigset`](https://grass.osgeo.org/grass-devel/manuals/i.gensigset.html)
- [`i.segment.stats`](https://grass.osgeo.org/grass-devel/manuals/i.segment.stats.html)
- [`i.pca`](https://grass.osgeo.org/grass-devel/manuals/i.pca.html)
- [`r.neighbors`](https://grass.osgeo.org/grass-devel/manuals/r.neighbors.html)
- [`r.rescale`](https://grass.osgeo.org/grass-devel/manuals/r.rescale.html)

---

## Authors

G. Antoniol - RCOST (Research Centre on
Software Technology - Viale Traiano - 82100 Benevento) C. Basco - RCOST (Research Centre on Software Technology - Viale
Traiano - 82100 Benevento) M. Ceccarelli - Facolta di Scienze, Universita del Sannio, Benevento Markus Metz (correction and optimization of the initial version) Moritz Lennert (documentation)

---

## Resources

- [Official r.texture manual](https://grass.osgeo.org/grass-devel/manuals/r.texture.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.texture.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
