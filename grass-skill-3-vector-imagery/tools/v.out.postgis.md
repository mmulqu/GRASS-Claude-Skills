# v.out.postgis

**Category**: vector

## Description

Exports a vector map layer to PostGIS feature table.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.v_out_postgis(input,type="auto",layer="1",output,output_layer=None,output_link=None,options=None,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

---

---

## Detailed Description

v.out.postgis exports an existing GRASS vector map layer to PostGIS
feature table. Features without category are skipped.

By default GRASS topological features are converted into simple
features (see OGC Simple Feature
Access specification
for details). Flag -l allows to export vector features as
topological elements stored in PostGIS
Topology schema. Note that
topological export requires PostGIS version 2 or later.

Additional creation options can be defined by options parameter:

PostGIS Topology related options (relevant only for -l flag):

Creation options are comma-separated pairs ( key=value ), the
options are case-insensitive. Note that options defined by v.external.out are ignored by v.out.postgis .

v.out.postgis optionally also creates a new vector map in the current
mapset if output_link is defined.

---

## See Also

Related tools:
- [`v.out.ogr`](https://grass.osgeo.org/grass-devel/manuals/v.out.ogr.html)
- [`v.external`](https://grass.osgeo.org/grass-devel/manuals/v.external.html)
- [`v.external.out`](https://grass.osgeo.org/grass-devel/manuals/v.external.out.html)
- [`v.in.ogr`](https://grass.osgeo.org/grass-devel/manuals/v.in.ogr.html)

---

## Resources

- [Official v.out.postgis manual](https://grass.osgeo.org/grass-devel/manuals/v.out.postgis.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/v.out.postgis.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
