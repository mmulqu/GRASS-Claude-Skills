# GRASS GIS Skills for Claude Code

This repository contains three comprehensive Claude Code skills that provide complete documentation for GRASS GIS 8.5+ tools using the new `grass.tools` API.

## Installation

### Prerequisites

- [Claude Desktop](https://claude.ai/download) installed on your system
- GRASS GIS 8.5 or later (for the `grass.tools` API)

### Installing Skills in Claude Desktop

1. **Navigate to Settings**
   - Open **Claude Desktop**
   - Go to **Settings** → **Capabilities**

2. **Enable Code Execution**
   - Ensure that **Code execution and file creation** is enabled
   - This is required for skills to function properly

3. **Upload Skills**
   - Scroll to the **Skills** section
   - Click **"Upload skill"** button
   - Upload each ZIP file from this repository:
     - `grass-skill-1-display-general.zip`
     - `grass-skill-2-raster-database.zip`
     - `grass-skill-3-vector-imagery.zip`

4. **Enable Skills**
   - Each uploaded skill will appear in your skills list
   - Toggle individual skills on or off as needed
   - Enable all three GRASS GIS skills

5. **Verify Installation**
   - Type `/skills` in Claude Code to see all installed skills
   - You should see all three GRASS GIS skills listed and enabled

## What's Included

### Skill 1: Display, General & Temporal Tools
**138 tools** covering:
- **Display Tools (d.\*)**: Map rendering, legends, scale bars, annotations, and visualization
  - `d.rast` - Display raster maps
  - `d.vect` - Display vector maps
  - `d.legend` - Add map legends
  - `d.barscale` - Add scale bars
  - `d.northarrow` - Add north arrows
  - And 133 more display tools

- **General Tools (g.\*)**: Region management, projections, file operations, and system utilities
  - `g.region` - Manage computational region
  - `g.proj` - Coordinate reference system information
  - `g.list` - List available maps
  - `g.copy`, `g.rename`, `g.remove` - Map management
  - And more general utilities

- **Temporal Tools (t.\*)**: Time-series data processing and spatio-temporal analysis
  - `t.rast.series` - Temporal raster series processing
  - `t.rast.aggregate` - Aggregate raster time series
  - `t.create`, `t.register` - Temporal dataset management
  - And more temporal analysis tools

### Skill 2: Raster & Database Tools
**190 tools** covering:
- **Raster Tools (r.\*)**: Terrain analysis, raster algebra, interpolation, and spatial analysis
  - `r.slope.aspect` - Calculate slope and aspect from DEM
  - `r.watershed` - Watershed analysis and stream extraction
  - `r.mapcalc` - Raster map calculator (algebra)
  - `r.neighbors` - Neighborhood analysis
  - `r.statistics` - Zonal statistics
  - `r.buffer`, `r.cost`, `r.drain` - Spatial analysis
  - And 184 more raster tools

- **Database Tools (db.\*)**: Attribute database operations and SQL queries
  - `db.select` - Query database
  - `db.execute` - Execute SQL statements
  - `db.tables`, `db.columns` - Database inspection
  - And more database utilities

### Skill 3: Vector & Imagery Tools
**181 tools** covering:
- **Vector Tools (v.\*)**: Vector operations, topology, network analysis, and spatial queries
  - `v.buffer` - Create buffers around features
  - `v.overlay` - Vector overlay operations
  - `v.clean` - Topology cleaning
  - `v.net` - Network analysis preparation
  - `v.net.path` - Shortest path routing
  - `v.dissolve`, `v.patch` - Vector processing
  - And 175 more vector tools

- **Imagery Tools (i.\*)**: Remote sensing, classification, and image processing
  - `i.vi` - Calculate vegetation indices (NDVI, EVI, etc.)
  - `i.cluster` - Unsupervised classification
  - `i.maxlik` - Maximum likelihood classification
  - `i.segment` - Image segmentation
  - `i.pca` - Principal component analysis
  - `i.landsat.toar` - Landsat atmospheric correction
  - And more imagery analysis tools

## Using the Skills

### In Claude Code

Once installed, Claude will have access to comprehensive documentation for all 509 GRASS GIS tools. Simply ask questions or request help with GRASS GIS operations:

**Examples:**
- "How do I calculate slope from a DEM using GRASS?"
- "Show me how to create a buffer around vector features"
- "What parameters does r.watershed accept?"
- "Help me classify a Landsat image using maximum likelihood"
- "How do I create and register temporal raster datasets?"

Claude will reference the appropriate skill documentation and provide accurate code examples using the `grass.tools` API.

### API Usage Pattern

All tools follow the `grass.tools` API pattern (experimental in GRASS 8.5, stable in 8.6):

```python
from grass.script import setup as gsetup
from grass.tools import Tools

# Initialize GRASS session
gsetup.init('/path/to/grassdata', 'location_name', 'mapset_name')
tools = Tools()

# Use any tool
tools.r_slope_aspect(elevation='dem', slope='slope', aspect='aspect')
tools.v_buffer(input='roads', output='road_buffer', distance=50)
tools.d_rast(map='elevation')
```

## Tool Documentation Structure

Each of the 509 tools has complete documentation including:
- **Function signature** with Python type hints
- **All parameters** with types, descriptions, and defaults
- **Return types** and error handling
- **Detailed descriptions** of functionality
- **Related tools** and cross-references
- **Links** to official GRASS documentation

## Quick Reference

### Accessing Tool Documentation

Each skill ZIP file contains a `tools/` directory with individual markdown files:
- `grass-skill-1-display-general.zip` → `tools/d.rast.md`, `tools/g.region.md`, etc.
- `grass-skill-2-raster-database.zip` → `tools/r.watershed.md`, `tools/r.slope.aspect.md`, etc.
- `grass-skill-3-vector-imagery.zip` → `tools/v.buffer.md`, `tools/i.vi.md`, etc.

### Usage Guides

Each skill ZIP includes a `USAGE.md` with quick-start examples:
- Skill 1: Display and temporal workflows
- Skill 2: Raster processing workflows
- Skill 3: Vector and imagery workflows

## Requirements

- **GRASS GIS 8.5+**: Required for `grass.tools` API
- **Python 3.8+**: For GRASS Python API
- **Claude Desktop**: For skill integration

## About the grass.tools API

The `grass.tools` API is the new object-oriented interface for GRASS GIS:
- **Status**: Experimental in GRASS 8.5, will be stable in GRASS 8.6
- **Benefits**:
  - Clean object-oriented design
  - Python type hints for better IDE support
  - Consistent return types (`ToolResult`)
  - Better error handling (`ToolError`)
  - Automatic parameter validation

## Resources

- **GRASS GIS Website**: https://grass.osgeo.org/
- **GRASS Documentation**: https://grass.osgeo.org/grass-devel/manuals/
- **grass.tools API**: https://grass.osgeo.org/grass85/manuals/libpython/grass.tools.html

## Support

For issues with these skills:
- Extract the ZIP files to view individual tool documentation in `tools/` directories
- Refer to `USAGE.md` files inside each ZIP for workflow examples
- Consult official GRASS documentation for detailed explanations

For GRASS GIS questions:
- Visit the [GRASS GIS community](https://grass.osgeo.org/support/)
- Check the [mailing lists](https://lists.osgeo.org/mailman/listinfo/grass-user)

---

*These skills were generated from GRASS GIS 8.5 development documentation to provide comprehensive Claude Code integration for geospatial workflows.*
