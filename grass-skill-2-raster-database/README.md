# GRASS GIS - Raster & Database Tools

Complete documentation for 190 GRASS GIS tools covering raster processing and database operations.

## Tools by Category

### Raster Tools (172 tools)

- [r.basins.fill](tools/r.basins.fill.md)
- [r.blend](tools/r.blend.md)
- [r.buffer](tools/r.buffer.md)
- [r.buffer.lowmem](tools/r.buffer.lowmem.md)
- [r.buildvrt](tools/r.buildvrt.md)
- [r.carve](tools/r.carve.md)
- [r.category](tools/r.category.md)
- [r.circle](tools/r.circle.md)
- [r.clump](tools/r.clump.md)
- [r.coin](tools/r.coin.md)
- [r.colors](tools/r.colors.md)
- [r.colors.out](tools/r.colors.out.md)
- [r.colors.stddev](tools/r.colors.stddev.md)
- [r.composite](tools/r.composite.md)
- [r.compress](tools/r.compress.md)
- *...and 157 more raster tools*

### Database Tools (18 tools)

- [db.columns](tools/db.columns.md)
- [db.connect](tools/db.connect.md)
- [db.copy](tools/db.copy.md)
- [db.createdb](tools/db.createdb.md)
- [db.databases](tools/db.databases.md)
- [db.describe](tools/db.describe.md)
- [db.drivers](tools/db.drivers.md)
- [db.dropcolumn](tools/db.dropcolumn.md)
- [db.dropdb](tools/db.dropdb.md)
- [db.droptable](tools/db.droptable.md)
- [db.execute](tools/db.execute.md)
- [db.in.ogr](tools/db.in.ogr.md)
- [db.login](tools/db.login.md)
- [db.out.ogr](tools/db.out.ogr.md)
- [db.select](tools/db.select.md)
- *...and 3 more database tools*

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
tools.r_slope_aspect(elevation='dem', slope='slope')
`

---

*Part of a 3-skill series for complete GRASS GIS coverage*
