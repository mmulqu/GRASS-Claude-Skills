# r.li.daemon

**Category**: raster

## Description

Support module for r.li landscape index calculations.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

*(Not yet available in grass.tools)*

---

---

## Detailed Description

This documentation is focused on scientists and developers who wants to
implement a new landscape index computation. Refer to the r.li modules overview and g.gui.rlisetup module for user-focused documentation.

r.li.daemon provides support for landscape index calculations on
raster maps. It hides the management of areas, defined using g.gui.rlisetup command. It is not used like a
standalone program, but its functions are a library used by all r.li.[index] commands. This description is a tutorial for new index definition.

The developer has only to focus on a unique area, like in mathematical
definitions, and has to write a C implementation of it. The areas are defined using a struct called area_des and it
members are explained in the source code (doxygen) documentation.

To write a new index only two steps are needed:

Compile it using a changed Makefile based on the file for r.li.patchdensity .

Refer to the r.li library documentation in the source code and
implementation of r.li modules for details and examples.

---

## See Also

Related tools:
- [`r.le`](https://grass.osgeo.org/grass-devel/manuals/r.le.html)
- [`r.li`](https://grass.osgeo.org/grass-devel/manuals/r.li.html)
- [`g.gui.rlisetup`](https://grass.osgeo.org/grass-devel/manuals/g.gui.rlisetup.html)

---

## Authors

Claudio Porta and Lucio Davide Spano, students of Computer Science
University of Pisa (Italy). Commission from Faunalia Pontedera (PI) Rewritten from "r.le.setup" by William L. Baker Various bug fixes by Markus Metz

---

## Resources

- [Official r.li.daemon manual](https://grass.osgeo.org/grass-devel/manuals/r.li.daemon.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.li.daemon.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
