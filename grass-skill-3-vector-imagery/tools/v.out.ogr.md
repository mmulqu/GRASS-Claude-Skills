# v.out.ogr

**Category**: vector

## Description

Exports a vector map layer to any of the supported OGR vector formats. By default a vector map layer is exported to OGC GeoPackage format.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.v_out_ogr(input,layer="1",type="auto",output,format="GPKG",output_layer=None,output_type="",dsco="",lco="",method="fast",flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

---

---

## Detailed Description

v.out.ogr converts GRASS vector map layer to any of the supported OGR vector formats (including OGC GeoPackage, ESRI
Shapefile, SpatiaLite or GML).

OGR (Simple Features Library) is part of the GDAL library, so you need to install this library to use v.out.ogr .

The OGR library supports many various formats including:

The list of supported formats is printed with the -l flag.

For further available formats view the GDAL vector drivers documentation .

---

## See Also

Related tools:
- [`v.out.postgis`](https://grass.osgeo.org/grass-devel/manuals/v.out.postgis.html)
- [`db.out.ogr`](https://grass.osgeo.org/grass-devel/manuals/db.out.ogr.html)
- [`v.external`](https://grass.osgeo.org/grass-devel/manuals/v.external.html)
- [`v.external.out`](https://grass.osgeo.org/grass-devel/manuals/v.external.out.html)
- [`v.in.ogr`](https://grass.osgeo.org/grass-devel/manuals/v.in.ogr.html)
- [`v.pack`](https://grass.osgeo.org/grass-devel/manuals/v.pack.html)

---

## Authors

Radim Blazek, ITC-Irst, Trento, Italy Some contributions: Markus Neteler Multi-feature support by Martin Landa, Czech Technical University in
Prague, 2013

---

## Resources

- [Official v.out.ogr manual](https://grass.osgeo.org/grass-devel/manuals/v.out.ogr.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/v.out.ogr.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
