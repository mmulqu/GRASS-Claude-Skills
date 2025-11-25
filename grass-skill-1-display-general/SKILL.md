---
name: grass-gis-display-general-temporal-tools
description: Documentation for 138 GRASS GIS tools covering display/visualization (d.*), general utilities (g.*), and temporal data processing (t.*) with complete API signatures and parameters.
---

# GRASS GIS - Display, General & Temporal Tools

This skill provides comprehensive documentation for GRASS GIS tools focused on **display/visualization**, **general utilities**, and **temporal data processing**. Part of a 3-skill series covering all GRASS GIS functionality.

## What This Skill Provides

- **43 Display Tools (d.*)**: Map rendering, legends, scale bars, annotations, and visualization
- **44 General Tools (g.*)**: Region management, projections, file operations, and system utilities
- **51 Temporal Tools (t.*)**: Time-series data processing, spatio-temporal analysis, and temporal data management

## Tool Categories

### Display Tools (d.*)
Create maps, add overlays, legends, scale bars, and annotations:
- `d.rast` - Display raster maps
- `d.vect` - Display vector maps
- `d.legend` - Add map legends
- `d.barscale` - Add scale bars
- `d.northarrow` - Add north arrows
- `d.text` - Add text annotations
- `d.histogram` - Display histograms
- And 36 more display tools...

### General Tools (g.*)
System configuration, region management, and file operations:
- `g.region` - Manage computational region
- `g.proj` - Coordinate reference system information
- `g.list` - List available maps
- `g.copy` - Copy maps
- `g.remove` - Remove maps
- `g.rename` - Rename maps
- `g.mapset` - Manage mapsets
- And 37 more general tools...

### Temporal Tools (t.*)
Process and analyze time-series geospatial data:
- `t.rast.series` - Temporal raster series processing
- `t.rast.aggregate` - Aggregate raster time series
- `t.rast.extract` - Extract raster time series
- `t.vect.observe.strds` - Sample raster time series at vector points
- `t.info` - Get temporal dataset information
- `t.list` - List temporal datasets
- `t.create` - Create temporal datasets
- And 44 more temporal tools...

## When to Use This Skill

Use this skill when you need to:
- **Visualize geospatial data** - Create maps, add legends, scale bars, annotations
- **Manage GRASS environment** - Set regions, handle projections, list/copy/rename maps
- **Process time-series data** - Analyze temporal patterns, aggregate over time, extract temporal subsets
- **Configure display settings** - Set colors, fonts, backgrounds, and visual properties
- **Work with coordinate systems** - Transform projections, manage CRS information

## How to Access Documentation

All tool documentation is in the `tools/` directory. Read `tools/{tool_name}.md` for specific tool details.

**Examples:**
- `tools/d.rast.md` - Display raster maps
- `tools/g.region.md` - Manage computational region  
- `tools/t.rast.series.md` - Process raster time series

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

### Display Workflow Example
```python
# Set computational region
tools.g_region(raster='elevation')

# Display raster
tools.d_rast(map='elevation')

# Add vector overlay
tools.d_vect(map='roads', color='red', width=2)

# Add legend
tools.d_legend(raster='elevation', at='5,50,7,10')

# Add scale bar
tools.d_barscale(at='5,10', length=1000)
```

### Temporal Analysis Example
```python
# Create temporal raster dataset
tools.t_create(output='temperature_series', type='strds', 
               title='Monthly Temperature', description='2020-2023 data')

# Register raster maps
tools.t_register(input='temperature_series', maps='temp_2020_01,temp_2020_02,...')

# Aggregate monthly to annual averages
tools.t_rast_aggregate(input='temperature_series', output='annual_temp',
                       basename='temp_year', granularity='1 years', 
                       method='average')
```

## Related Skills

This is part of a 3-skill series:
- **grass-skill-1-display-general** (this skill) - Display, General & Temporal tools
- **grass-skill-2-raster-database** - Raster processing & Database tools
- **grass-skill-3-vector-imagery** - Vector operations & Imagery tools

## Resources

- **Official GRASS Documentation**: https://grass.osgeo.org/grass-devel/manuals/
- **GRASS GIS Website**: https://grass.osgeo.org/
- Each tool links to its official documentation page

---

*Generated from GRASS GIS 8.5 development documentation*

