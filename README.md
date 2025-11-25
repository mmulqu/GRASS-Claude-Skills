# GRASS GIS Claude Code Skills

Complete Claude Code skills providing documentation for all 509 GRASS GIS tools using the new `grass.tools` API (GRASS 8.5+).

## Overview

This repository contains three Claude Code skills that give Claude comprehensive knowledge of GRASS GIS functionality. Each skill includes complete API documentation, parameter references, and usage examples for geospatial analysis workflows.

**Total Coverage**: 509 GRASS GIS tools across 3 skills

## Skills Included

### 🗺️ Skill 1: Display, General & Temporal Tools
**138 tools** | `grass-skill-1-display-general/`

Covers visualization, system utilities, and time-series analysis:
- **Display (d.\*)**: Map rendering, legends, scale bars, annotations
- **General (g.\*)**: Region management, projections, file operations
- **Temporal (t.\*)**: Spatio-temporal data processing and analysis

**Common Tools**: `d.rast`, `d.vect`, `d.legend`, `g.region`, `g.proj`, `g.list`, `t.rast.series`, `t.rast.aggregate`

### 🏔️ Skill 2: Raster & Database Tools
**190 tools** | `grass-skill-2-raster-database/`

Covers raster analysis and database operations:
- **Raster (r.\*)**: Terrain analysis, raster algebra, interpolation, spatial analysis
- **Database (db.\*)**: SQL queries, attribute management

**Common Tools**: `r.slope.aspect`, `r.watershed`, `r.mapcalc`, `r.buffer`, `r.neighbors`, `r.univar`, `db.select`, `db.execute`

### 🛰️ Skill 3: Vector & Imagery Tools
**181 tools** | `grass-skill-3-vector-imagery/`

Covers vector operations and remote sensing:
- **Vector (v.\*)**: Vector processing, topology, network analysis, spatial queries
- **Imagery (i.\*)**: Classification, vegetation indices, atmospheric correction

**Common Tools**: `v.buffer`, `v.overlay`, `v.clean`, `v.net.path`, `i.vi`, `i.cluster`, `i.maxlik`, `i.segment`

## Quick Start

### Installation in Claude Desktop

1. Open **Claude Desktop** → **Settings** → **Skills**
2. Click **Add Skill** and select each folder:
   - `grass-skill-1-display-general`
   - `grass-skill-2-raster-database`
   - `grass-skill-3-vector-imagery`
3. Enable all three skills
4. Verify with `/skills` command

See [`claude.md`](claude.md) for detailed installation instructions.

### Using in Claude Code

Once installed, ask Claude about GRASS GIS operations:

```
"How do I calculate slope from a DEM?"
"Show me vector buffer creation"
"What are the parameters for r.watershed?"
"Help me classify satellite imagery"
```

Claude will provide accurate code examples using the `grass.tools` API.

## grass.tools API

All tools use the modern `grass.tools` API (experimental in 8.5, stable in 8.6):

```python
from grass.script import setup as gsetup
from grass.tools import Tools

# Initialize GRASS session
gsetup.init('/path/to/grassdata', 'location_name', 'mapset_name')
tools = Tools()

# Example: Terrain analysis workflow
tools.g_region(raster='dem')
tools.r_slope_aspect(elevation='dem', slope='slope', aspect='aspect')
tools.r_watershed(elevation='dem', threshold=1000, basin='basins', stream='streams')

# Example: Vector operations
tools.v_buffer(input='roads', output='road_buffer', distance=50)
tools.v_overlay(ainput='parcels', binput='road_buffer',
                output='parcels_near_roads', operator='and')

# Example: Display and visualization
tools.d_rast(map='elevation')
tools.d_vect(map='streams', color='blue', width=2)
tools.d_legend(raster='elevation', at='5,50,7,10')
```

## Repository Structure

```
GRASS-Claude-Skills/
├── claude.md                                    # Installation guide
├── README.md                                    # This file
├── grass-skill-1-display-general/
│   ├── SKILL.md                                 # Skill overview
│   ├── USAGE.md                                 # Quick start examples
│   ├── README.md                                # Tool listing
│   └── tools/                                   # 138 tool docs
│       ├── d.rast.md
│       ├── g.region.md
│       ├── t.rast.series.md
│       └── ...
├── grass-skill-2-raster-database/
│   ├── SKILL.md
│   ├── USAGE.md
│   ├── README.md
│   └── tools/                                   # 190 tool docs
│       ├── r.slope.aspect.md
│       ├── r.watershed.md
│       ├── db.select.md
│       └── ...
└── grass-skill-3-vector-imagery/
    ├── SKILL.md
    ├── USAGE.md
    ├── README.md
    └── tools/                                   # 181 tool docs
        ├── v.buffer.md
        ├── v.overlay.md
        ├── i.vi.md
        └── ...
```

## Documentation Structure

Each tool has complete documentation with:

- **Function Signature**: `tools.tool_name(param1, param2, ...)`
- **Parameters**: Full parameter list with types, descriptions, defaults, and allowed values
- **Returns**: Return type (`ToolResult` or `None`)
- **Raises**: Exception handling (`ToolError`)
- **Description**: Detailed functionality explanation
- **Related Tools**: Cross-references to similar tools
- **Official Docs**: Links to GRASS documentation

## Example Workflows

### Terrain Analysis
```python
from grass.script import setup as gsetup
from grass.tools import Tools

gsetup.init('/path/to/grassdata', 'location', 'mapset')
tools = Tools()

# Set working region
tools.g_region(raster='dem')

# Calculate terrain parameters
tools.r_slope_aspect(elevation='dem', slope='slope', aspect='aspect')
tools.r_relief(input='dem', output='hillshade')

# Watershed analysis
tools.r_watershed(elevation='dem', threshold=1000,
                  basin='basins', stream='streams', accumulation='flow_acc')

# Statistics
result = tools.r_univar(map='slope', flags='g')
print(result.stdout)
```

### Vector Analysis
```python
# Import data
tools.v_in_ogr(input='roads.shp', output='roads')
tools.v_in_ogr(input='parcels.shp', output='parcels')

# Clean topology
tools.v_clean(input='roads', output='roads_clean', tool='break,rmdupl')

# Buffer and overlay
tools.v_buffer(input='roads_clean', output='road_buffer', distance=50)
tools.v_overlay(ainput='parcels', binput='road_buffer',
                output='parcels_near_roads', operator='and')
```

### Satellite Image Classification
```python
# Create image group
tools.i_group(group='landsat', subgroup='all',
              input='B1,B2,B3,B4,B5,B6,B7')

# Calculate NDVI
tools.i_vi(red='B4', nir='B5', output='ndvi', viname='ndvi')

# Classify
tools.i_cluster(group='landsat', subgroup='all',
                signaturefile='clusters', classes=15)
tools.i_maxlik(group='landsat', subgroup='all',
               signaturefile='clusters', output='landcover')
```

### Temporal Analysis
```python
# Create temporal dataset
tools.t_create(output='temperature_series', type='strds',
               title='Monthly Temperature', description='2020-2023 data')

# Register rasters
tools.t_register(input='temperature_series',
                 maps='temp_2020_01,temp_2020_02,temp_2020_03,...',
                 start='2020-01-01', increment='1 months')

# Aggregate to annual averages
tools.t_rast_aggregate(input='temperature_series', output='annual_temp',
                       basename='temp_year', granularity='1 years',
                       method='average')
```

## Requirements

- **GRASS GIS 8.5+**: Required for `grass.tools` API
- **Python 3.8+**: For GRASS Python scripting
- **Claude Desktop**: For Claude Code skills integration

## Features

✅ **509 tools documented** across all GRASS modules
✅ **Complete API signatures** with Python type hints
✅ **All parameters documented** with types and defaults
✅ **Usage examples** for common workflows
✅ **Error handling** with `ToolError` exceptions
✅ **Cross-references** between related tools
✅ **Quick-start guides** in each skill's `USAGE.md`

## Resources

- **GRASS GIS**: https://grass.osgeo.org/
- **GRASS Documentation**: https://grass.osgeo.org/grass-devel/manuals/
- **grass.tools API**: https://grass.osgeo.org/grass85/manuals/libpython/grass.tools.html
- **Claude Desktop**: https://claude.ai/download

## About grass.tools API

The `grass.tools` API is the new object-oriented interface for GRASS GIS:

- **Status**: Experimental in GRASS 8.5 → Stable in GRASS 8.6
- **Benefits**:
  - Clean object-oriented design
  - Python type hints for IDE support
  - Consistent return types
  - Better error handling
  - Automatic parameter validation

## Contributing

These skills were generated from GRASS GIS 8.5 development documentation. To update or improve:

1. Check individual tool documentation in `tools/` directories
2. Refer to official GRASS documentation for authoritative information
3. Test with GRASS GIS 8.5+ for API compatibility

## License

Documentation derived from GRASS GIS project (GPL v2+).

## Support

For GRASS GIS questions:
- Community: https://grass.osgeo.org/support/
- Mailing lists: https://lists.osgeo.org/mailman/listinfo/grass-user
- Issue tracker: https://github.com/OSGeo/grass

---

**Total Tools**: 509 | **Skills**: 3 | **GRASS Version**: 8.5+
