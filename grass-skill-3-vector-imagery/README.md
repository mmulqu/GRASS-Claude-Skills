# GRASS GIS - Vector & Imagery Tools

Complete documentation for 181 GRASS GIS tools covering vector operations and imagery processing.

## Tools by Category

### Vector Tools (128 tools)

- [v.buffer](tools/v.buffer.md)
- [v.build](tools/v.build.md)
- [v.build.all](tools/v.build.all.md)
- [v.build.polylines](tools/v.build.polylines.md)
- [v.category](tools/v.category.md)
- [v.centroids](tools/v.centroids.md)
- [v.class](tools/v.class.md)
- [v.clean](tools/v.clean.md)
- [v.clip](tools/v.clip.md)
- [v.cluster](tools/v.cluster.md)
- [v.colors](tools/v.colors.md)
- [v.colors.out](tools/v.colors.out.md)
- [v.db.addcolumn](tools/v.db.addcolumn.md)
- [v.db.addtable](tools/v.db.addtable.md)
- [v.db.connect](tools/v.db.connect.md)
- *...and 113 more vector tools*

### Imagery Tools (53 tools)

- [i.albedo](tools/i.albedo.md)
- [i.aster.toar](tools/i.aster.toar.md)
- [i.atcorr](tools/i.atcorr.md)
- [i.band.library](tools/i.band.library.md)
- [i.biomass](tools/i.biomass.md)
- [i.cca](tools/i.cca.md)
- [i.cluster](tools/i.cluster.md)
- [i.colors.enhance](tools/i.colors.enhance.md)
- [i.eb.eta](tools/i.eb.eta.md)
- [i.eb.evapfr](tools/i.eb.evapfr.md)
- [i.eb.hsebal01](tools/i.eb.hsebal01.md)
- [i.eb.netrad](tools/i.eb.netrad.md)
- [i.eb.soilheatflux](tools/i.eb.soilheatflux.md)
- [i.emissivity](tools/i.emissivity.md)
- [i.evapo.mh](tools/i.evapo.mh.md)
- *...and 38 more imagery tools*

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
tools.v_buffer(input='roads', output='buffer', distance=100)
`

---

*Part of a 3-skill series for complete GRASS GIS coverage*
