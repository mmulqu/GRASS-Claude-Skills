# GRASS GIS - Display, General & Temporal Tools

Complete documentation for 138 GRASS GIS tools covering display, general utilities, and temporal processing.

## Tools by Category

### Display Tools (43 tools)

- [d.background](tools/d.background.md)
- [d.barscale](tools/d.barscale.md)
- [d.colorlist](tools/d.colorlist.md)
- [d.colortable](tools/d.colortable.md)
- [d.correlate](tools/d.correlate.md)
- [d.erase](tools/d.erase.md)
- [d.font](tools/d.font.md)
- [d.fontlist](tools/d.fontlist.md)
- [d.frame](tools/d.frame.md)
- [d.geodesic](tools/d.geodesic.md)
- *...and 33 more display tools*

### General Tools (44 tools)

- [g.access](tools/g.access.md)
- [g.cairocomp](tools/g.cairocomp.md)
- [g.copy](tools/g.copy.md)
- [g.dirseps](tools/g.dirseps.md)
- [g.download.location](tools/g.download.location.md)
- [g.download.project](tools/g.download.project.md)
- [g.extension](tools/g.extension.md)
- [g.extension.all](tools/g.extension.all.md)
- [g.filename](tools/g.filename.md)
- [g.findetc](tools/g.findetc.md)
- *...and 34 more general tools*

### Temporal Tools (51 tools)

- [t.connect](tools/t.connect.md)
- [t.copy](tools/t.copy.md)
- [t.create](tools/t.create.md)
- [t.info](tools/t.info.md)
- [t.list](tools/t.list.md)
- [t.merge](tools/t.merge.md)
- [t.rast.accdetect](tools/t.rast.accdetect.md)
- [t.rast.accumulate](tools/t.rast.accumulate.md)
- [t.rast.aggregate](tools/t.rast.aggregate.md)
- [t.rast.aggregate.ds](tools/t.rast.aggregate.ds.md)
- *...and 41 more temporal tools*

## Quick Links

- [SKILL.md](SKILL.md) - Skill overview and usage guide
- [USAGE.md](USAGE.md) - Quick start and examples

## grass.tools API

All tools use the experimental grass.tools API (stable in GRASS 8.6):

`python
from grass.script import setup as gsetup
from grass.tools import Tools

gsetup.init('/path/to/grassdata', 'location', 'mapset')
tools = Tools()

# Use any tool
tools.d_rast(map='elevation')
`

---

*Part of a 3-skill series for complete GRASS GIS coverage*
