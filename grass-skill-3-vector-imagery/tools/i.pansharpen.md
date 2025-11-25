# i.pansharpen

**Category**: imagery

## Description

Image fusion algorithms to sharpen multispectral with high-res panchromatic channels

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.i_pansharpen(red,green,blue,pan,output,method="ihs",bitdepth=8,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`red : str | np.ndarray, required`**
   - Name of raster map to be used for <red>
   - Used as: input, raster, name

2. **`green : str | np.ndarray, required`**
   - Name of raster map to be used for <green>
   - Used as: input, raster, name

3. **`blue : str | np.ndarray, required`**
   - Name of raster map to be used for <blue>
   - Used as: input, raster, name

4. **`pan : str | np.ndarray, required`**
   - Name of raster map to be used for high resolution panchromatic channel
   - Used as: input, raster, name

5. **`output : str | type(np.ndarray) | type(np.array) | type(gs.array.array), required`**
   - Name for output basename raster map(s)
   - Used as: output, raster, basename

6. **`method : str, required`**
   - Method for pan sharpening
   - Allowed values: brovey, ihs, pca
   - Default: ihs

7. **`bitdepth : int, required`**
   - Bit depth of image (must be in range of 2-30)
   - Allowed values: 2-32
   - Default: 8

8. **`flags : str, optional`**
   - Allowed values: s, l, r
   - s
   - Serial processing rather than parallel processing
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/i.pansharpen.html#__tabbed_2_3) for all details)*

9. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

10. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

11. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

12. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 12 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/i.pansharpen.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | np.ndarray | tuple[np.ndarray] | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned. If an array type (e.g., np.ndarray) is used for one of the raster outputs, the result will be an array and will have the shape corresponding to the computational region. If an array type is used for more than one raster output, the result will be a tuple of arrays.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

i.pansharpen uses a high resolution panchromatic band from a
multispectral image to sharpen 3 lower resolution bands. The 3 lower
resolution bands can then be combined into an RGB color image at a
higher (more detailed) resolution than is possible using the original 3
bands. For example, Landsat ETM has low resolution spectral bands 1
(blue), 2 (green), 3 (red), 4 (near IR), 5 (mid-IR), and 7 (mid-IR) at
30m resolution, and a high resolution panchromatic band 8 at 15m
resolution. Pan sharpening allows bands 3-2-1 (or other combinations of
30m resolution bands like 4-3-2 or 5-4-2) to be combined into a 15m
resolution color image.

i.pansharpen offers a choice of three different 'pan sharpening'
algorithms: IHS, Brovey, and PCA.

For IHS pan sharpening , the original 3 lower resolution bands,
selected as red, green and blue channels for creating an RGB composite
image, are transformed into IHS (intensity, hue, and saturation) color
space. The panchromatic band is then substituted for the intensity
channel (I), combined with the original hue (H) and saturation (S)
channels, and transformed back to RGB color space at the higher
resolution of the panchromatic band. The algorithm for this can be
represented as: RGB -> IHS -> [pan]HS -> RGB.

With a Brovey pan sharpening , each of the 3 lower resolution bands and
panchromatic band are combined using the following algorithm to
calculate 3 new bands at the higher resolution (example for band 1):

In PCA pan sharpening , a principal component analysis is performed on
the original 3 lower resolution bands to create 3 principal component
images (PC1, PC2, and PC3) and their associated eigenvectors (EV), such
that:

and

An inverse PCA is then performed, substituting the panchromatic band for
PC1. To do this, the eigenvectors matrix is inverted (in this case
transposed), the PC images are multiplied by the eigenvectors with the
panchromatic band substituted for PC1, and mean of each band is added to
each transformed image band using the following algorithm (example for
band 1):

The assignment of the channels depends on the satellite. Examples of
satellite imagery with high resolution panchromatic bands, and lower
resolution spectral bands include Landsat 7 ETM, QuickBird, and SPOT.

---

## See Also

Related tools:
- [`i.his.rgb`](https://grass.osgeo.org/grass-devel/manuals/i.his.rgb.html)
- [`i.rgb.his`](https://grass.osgeo.org/grass-devel/manuals/i.rgb.his.html)
- [`i.pca`](https://grass.osgeo.org/grass-devel/manuals/i.pca.html)
- [`d.rgb`](https://grass.osgeo.org/grass-devel/manuals/d.rgb.html)
- [`r.composite`](https://grass.osgeo.org/grass-devel/manuals/r.composite.html)

---

## Authors

Michael Barton (Arizona State University, USA) with contributions from Markus Neteler (ITC-irst, Italy); Glynn
Clements; Luca Delucchi (Fondazione E. Mach, Italy); Markus Metz; and
Hamish Bowman.

---

## Resources

- [Official i.pansharpen manual](https://grass.osgeo.org/grass-devel/manuals/i.pansharpen.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/i.pansharpen.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
