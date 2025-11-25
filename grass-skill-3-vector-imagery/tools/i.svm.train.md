# i.svm.train

**Category**: imagery

## Description

Train a SVM Train a Support Vector Machine

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

*(Not yet available in grass.tools)*

---

---

## Detailed Description

i.svm.train finds parameters for a Support Vector Machine and stores
them in a signature file for later usage by i.svm.predict .

Internally the module performs input value rescaling of each of imagery
group rasters by mean normalisation based on minimum and maximum value
present in the raster metadata. Rescaling parameters are written into
the signature file for use during prediction.

---

## See Also

Related tools:
- [`i.svm.predict`](https://grass.osgeo.org/grass-devel/manuals/i.svm.predict.html)
- [`r.support`](https://grass.osgeo.org/grass-devel/manuals/r.support.html)
- [`i.maxlik`](https://grass.osgeo.org/grass-devel/manuals/i.maxlik.html)
- [`i.smap`](https://grass.osgeo.org/grass-devel/manuals/i.smap.html)

---

## Resources

- [Official i.svm.train manual](https://grass.osgeo.org/grass-devel/manuals/i.svm.train.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/i.svm.train.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
