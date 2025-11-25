---
name: grass-gis--raster-and-database-tools
description: Documentation for 190 GRASS GIS tools covering raster processing (r.*) and database operations (db.*) with complete API signatures and parameters for spatial data analysis.
---

# GRASS GIS - Raster & Database Tools

This skill provides comprehensive documentation for GRASS GIS tools focused on **raster data processing** and **database operations**. Part of a 3-skill series covering all GRASS GIS functionality.

## What This Skill Provides

- **172 Raster Tools (r.*)**: Raster analysis, terrain modeling, spatial statistics, interpolation, and raster processing
- **18 Database Tools (db.*)**: Attribute management, SQL queries, table operations, and database connections

## Tool Categories

### Raster Tools (r.*)
Comprehensive raster data analysis and processing:

**Terrain Analysis:**
- `r.slope.aspect` - Calculate slope and aspect
- `r.contour` - Generate contour lines
- `r.relief` - Create shaded relief
- `r.geomorphon` - Detect landforms
- `r.watershed` - Calculate watershed basins and streams
- `r.terraflow` - Flow routing for massive grids

**Raster Algebra & Statistics:**
- `r.mapcalc` - Raster map calculator
- `r.neighbors` - Neighborhood analysis
- `r.statistics` - Zonal statistics
- `r.univar` - Univariate statistics
- `r.covar` - Covariance/correlation
- `r.regression.line` - Linear regression

**Interpolation & Sampling:**
- `r.surf.idw` - Inverse distance weighted interpolation
- `r.surf.contour` - Interpolate from contours
- `r.resamp.interp` - Resample using interpolation
- `r.resamp.stats` - Resample using statistics
- `r.random` - Random sampling

**Raster Conversion & Processing:**
- `r.to.vect` - Convert raster to vector
- `r.null` - Manage NULL values
- `r.recode` - Recode raster values
- `r.reclass` - Reclassify raster
- `r.cross` - Cross-tabulate rasters
- `r.patch` - Patch raster maps

**Spatial Analysis:**
- `r.buffer` - Create buffer zones
- `r.cost` - Calculate cost surfaces
- `r.drain` - Trace flow paths
- `r.grow.distance` - Generate distance maps
- `r.clump` - Find clumps of cells
- `r.thin` - Thin linear features

And 140+ more raster tools...

### Database Tools (db.*)
Attribute management and database operations:
- `db.select` - Query attribute tables
- `db.execute` - Execute SQL statements
- `db.connect` - Database connection settings
- `db.login` - Set database login credentials
- `db.tables` - List database tables
- `db.columns` - List table columns
- `db.describe` - Describe table structure
- `db.copy` - Copy tables
- And 10 more database tools...

## When to Use This Skill

Use this skill when you need to:
- **Analyze terrain** - Calculate slope, aspect, curvature, watersheds
- **Process raster data** - Interpolate, resample, reclassify, patch rasters
- **Perform spatial analysis** - Cost surfaces, buffers, flow routing, viewsheds
- **Calculate statistics** - Zonal stats, univariate stats, correlations
- **Manage attributes** - Query databases, execute SQL, manage table connections
- **Transform data** - Convert rasters, manage NULL values, cross-tabulate

## How to Access Documentation

All tool documentation is in the `tools/` directory. Read `tools/{tool_name}.md` for specific tool details.

**Examples:**
- `tools/r.slope.aspect.md` - Terrain analysis
- `tools/r.mapcalc.md` - Raster algebra
- `tools/r.neighbors.md` - Neighborhood analysis
- `tools/db.select.md` - Query attributes

## Tool Documentation Structure

Each tool's markdown file contains:

1. **Function Signature**: Exact Python `grass.tools` function call
2. **Parameters**: Complete list with types, descriptions, allowed values, defaults
3. **Returns**: Return type (`ToolResult` or `None`)
4. **Raises**: Exceptions (`ToolError`)
5. **Detailed Description**: What the tool does
6. **Note**: Important usage notes
7. **See Also**: Related tools
8. **Authors**: Original contributors

## grass.tools API Status

- **Experimental** in GRASS 8.5
- **Will be stable** in GRASS 8.6
- Object-oriented interface with Python type hints
- Returns `ToolResult` objects for consistent handling

## Quick Start

### Initialize GRASS Session
```python
from grass.script import setup as gsetup
from grass.tools import Tools

# Initialize session
gsetup.init('/path/to/grassdata', 'location', 'mapset')
tools = Tools()
```

### Terrain Analysis Example
```python
# Set computational region
tools.g_region(raster='elevation')

# Calculate slope and aspect
tools.r_slope_aspect(elevation='elevation', 
                     slope='slope', 
                     aspect='aspect',
                     format='degrees')

# Create shaded relief
tools.r_relief(input='elevation', output='hillshade')

# Generate contours
tools.r_contour(input='elevation', output='contours', step=10)
```

### Raster Processing Example
```python
# Smooth raster with neighborhood average
tools.r_neighbors(input='elevation', 
                  output='smoothed',
                  method='average',
                  size=5)

# Reclassify values
tools.r_recode(input='landuse',
               output='landuse_reclass',
               rules='reclass_rules.txt')

# Calculate statistics
tools.r_univar(map='elevation', flags='g')
```

### Database Operations Example
```python
# Query attributes
result = tools.db_select(sql='SELECT * FROM roads WHERE speed > 50')

# Execute SQL
tools.db_execute(sql='UPDATE roads SET paved=1 WHERE type=\'highway\'')

# Get table info
tools.db_columns(table='parcels')
```

## Related Skills

This is part of a 3-skill series:
- **grass-skill-1-display-general** - Display, General & Temporal tools
- **grass-skill-2-raster-database** (this skill) - Raster & Database tools
- **grass-skill-3-vector-imagery** - Vector operations & Imagery tools

## Resources

- **Official GRASS Documentation**: https://grass.osgeo.org/grass-devel/manuals/
- **GRASS GIS Website**: https://grass.osgeo.org/
- Each tool links to its official documentation page

---

*Generated from GRASS GIS 8.5 development documentation*

