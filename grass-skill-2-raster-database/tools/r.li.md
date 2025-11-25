# r.li

**Category**: raster

## Description

Landscape structure analysis package overview

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

*(Not yet available in grass.tools)*

---

---

## Detailed Description

The r.li suite is a toolset for multiscale analysis of landscape
structure. It aims at implementing metrics as found in external software
for quantitative measures of landscape structure like FRAGSTATS
(McGarigal and Marks 1995).

The r.li suite offers a set of patch and diversity indices. It
supports analysis of landscapes composed of a mosaic of patches, but,
more generally, the modules work with any two-dimensional raster map
whose cell values are integer (e.g., 1, 2) or floating point (e.g., 1.1,
3.2) values. The g.gui.rlisetup module has options for controlling the
shape, size, number, and distribution of sampling areas used to collect
information about the landscape structure. Sampling area shapes can be
the entire map or a moving window of square, rectangular or circular
shape. The size of sampling areas can be changed, so that the landscape
can be analyzed at a variety of spatial scales simultaneously. Sampling
areas may be distributed across the landscape in a random, systematic,
or stratified-random manner, or as a moving window.

The r.li modules can calculate a number of measures that produce
single values as output (e.g. mean patch size in the sampling area), as
well as measures that produce a distribution of values as output (e.g.
frequency distribution of patch sizes in the sampling area). The results
are stored as raster maps.

All modules require configuration file which can be created by the g.gui.rlisetup module which is a GUI tool providing a convenient way
to set all necessary parameters. This file can be used repetitively
saving user from the need to specify all parameters over and over again.

---

## Authors

Claudio Porta and Lucio Davide Spano, students of Computer Science,
University of Pisa (Italy). Commission from Faunalia Pontedera (PI)
Partially rewritten by Markus Metz

---

## Resources

- [Official r.li manual](https://grass.osgeo.org/grass-devel/manuals/r.li.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.li.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
