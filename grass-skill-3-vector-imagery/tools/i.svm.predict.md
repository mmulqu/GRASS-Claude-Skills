# i.svm.predict

**Category**: imagery

## Description

Predict with a SVM Predict with a Support Vector Machine

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

*(Not yet available in grass.tools)*

---

---

## Detailed Description

i.svm.predict predicts values with a Support Vector Machine (SVM) and
stores them in a raster file. Predictions are based on a signature file
generated with i.svm.train .

Internally the module performs input value rescaling of each of imagery
group rasters by minimum and maximum range determined during training.

---

## See Also

Related tools:
- [`i.svm.train`](https://grass.osgeo.org/grass-devel/manuals/i.svm.train.html)
- [`r.support`](https://grass.osgeo.org/grass-devel/manuals/r.support.html)
- [`i.maxlik`](https://grass.osgeo.org/grass-devel/manuals/i.maxlik.html)
- [`i.smap`](https://grass.osgeo.org/grass-devel/manuals/i.smap.html)

---

## Resources

- [Official i.svm.predict manual](https://grass.osgeo.org/grass-devel/manuals/i.svm.predict.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/i.svm.predict.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
