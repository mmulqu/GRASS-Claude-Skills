---
name: grass-gis--vector-and-imagery-tools
description: Documentation for 181 GRASS GIS tools covering vector operations (v.*) and imagery processing (i.*) with complete API signatures and parameters for spatial analysis and remote sensing.
---

# GRASS GIS - Vector & Imagery Tools

This skill provides comprehensive documentation for GRASS GIS tools focused on **vector data operations** and **imagery/remote sensing processing**. Part of a 3-skill series covering all GRASS GIS functionality.

## What This Skill Provides

- **128 Vector Tools (v.*)**: Vector analysis, topology, overlay operations, buffering, network analysis, and spatial queries
- **53 Imagery Tools (i.*)**: Satellite image processing, classification, pan-sharpening, atmospheric correction, and multispectral analysis

## Tool Categories

### Vector Tools (v.*)
Comprehensive vector data operations and analysis:

**Vector Creation & Conversion:**
- `v.in.ogr` - Import vector from OGR sources
- `v.out.ogr` - Export vector to OGR formats
- `v.to.rast` - Convert vector to raster
- `v.to.db` - Load vector values to database
- `v.extract` - Extract vector features
- `v.select` - Select features by attributes

**Topology & Geometry:**
- `v.build` - Build topology
- `v.clean` - Clean vector topology
- `v.generalize` - Generalize vector features
- `v.simplify` - Simplify vector geometry
- `v.split` - Split vector lines
- `v.segment` - Create segments

**Spatial Operations:**
- `v.buffer` - Create buffer zones
- `v.overlay` - Overlay vector maps (and, or, not, xor)
- `v.patch` - Patch vector maps
- `v.dissolve` - Dissolve boundaries
- `v.clip` - Clip vector by region
- `v.in.region` - Create vector from region

**Spatial Analysis:**
- `v.distance` - Calculate distances
- `v.neighbors` - Neighborhood analysis
- `v.voro noi` - Voronoi diagrams
- `v.delaunay` - Delaunay triangulation
- `v.hull` - Convex hull
- `v.kernel` - Kernel density estimation

**Network Analysis:**
- `v.net.path` - Find shortest path
- `v.net.distance` - Network distances
- `v.net.alloc` - Network allocation
- `v.net.iso` - Isochrones
- `v.net.salesman` - Traveling salesman
- `v.net.flow` - Network flow

**Attribute Operations:**
- `v.db.select` - Query vector attributes
- `v.db.update` - Update attributes
- `v.db.addcolumn` - Add columns
- `v.db.join` - Join tables
- `v.what.rast` - Sample raster at vector points
- `v.rast.stats` - Calculate raster statistics per vector

And 90+ more vector tools...

### Imagery Tools (i.*)
Satellite and aerial imagery processing:

**Image Classification:**
- `i.cluster` - Unsupervised classification (clustering)
- `i.maxlik` - Maximum likelihood classification
- `i.smap` - Sequential maximum a posteriori classification
- `i.segment` - Image segmentation
- `i.group` - Create imagery group
- `i.gensig` - Generate signature file

**Image Enhancement:**
- `i.pca` - Principal components analysis
- `i.colors.enhance` - Color enhancement
- `i.landsat.toar` - Landsat top-of-atmosphere reflectance
- `i.vi` - Vegetation indices (NDVI, EVI, etc.)
- `i.albedo` - Calculate albedo
- `i.emissivity` - Calculate emissivity

**Atmospheric Correction:**
- `i.atcorr` - Atmospheric correction
- `i.topo.corr` - Topographic correction
- `i.landsat.acca` - Landsat cloud detection

**Image Transformation:**
- `i.fft` - Fast Fourier Transform
- `i.ifft` - Inverse FFT
- `i.rectify` - Georectification
- `i.ortho.photo` - Orthorectification
- `i.fusion.brovey` - Brovey pan-sharpening

**Image Analysis:**
- `i.zc` - Zero-crossing edge detection
- `i.cca` - Canonical components analysis
- `i.biomass` - Biomass calculation
- `i.eb.* ` - Energy balance tools

And 30+ more imagery tools...

## When to Use This Skill

Use this skill when you need to:
- **Analyze vector data** - Buffering, overlay, topology, spatial queries
- **Perform network analysis** - Shortest paths, allocation, flow, isochrones
- **Process satellite imagery** - Classification, atmospheric correction, enhancement
- **Calculate indices** - NDVI, EVI, albedo, biomass
- **Geometric operations** - Generalize, simplify, dissolve, clip vectors
- **Manage attributes** - Join tables, update values, sample rasters

## How to Access Documentation

All tool documentation is in the `tools/` directory. Read `tools/{tool_name}.md` for specific tool details.

**Examples:**
- `tools/v.buffer.md` - Create buffer zones
- `tools/v.overlay.md` - Overlay analysis
- `tools/i.cluster.md` - Image classification
- `tools/i.vi.md` - Vegetation indices

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

### Vector Operations Example
```python
# Create 100m buffer around roads
tools.v_buffer(input='roads', output='road_buffer', distance=100)

# Overlay parcels with flood zones
tools.v_overlay(ainput='parcels', 
                binput='flood_zone',
                output='affected_parcels',
                operator='and')

# Find shortest path on road network
tools.v_net_path(input='roads',
                 output='route',
                 arc_layer=1,
                 start_coordinates='x1,y1',
                 end_coordinates='x2,y2')
```

### Imagery Processing Example
```python
# Create imagery group
tools.i_group(group='landsat',
              subgroup='all_bands',
              input='band1,band2,band3,band4,band5,band6,band7')

# Calculate NDVI
tools.i_vi(red='band3',
           nir='band4',
           output='ndvi',
           viname='ndvi')

# Unsupervised classification
tools.i_cluster(group='landsat',
                subgroup='all_bands',
                signaturefile='cluster_sig',
                classes=10)

tools.i_maxlik(group='landsat',
               subgroup='all_bands',
               signaturefile='cluster_sig',
               output='landcover')
```

## Related Skills

This is part of a 3-skill series:
- **grass-skill-1-display-general** - Display, General & Temporal tools
- **grass-skill-2-raster-database** - Raster processing & Database tools
- **grass-skill-3-vector-imagery** (this skill) - Vector & Imagery tools

## Resources

- **Official GRASS Documentation**: https://grass.osgeo.org/grass-devel/manuals/
- **GRASS GIS Website**: https://grass.osgeo.org/
- Each tool links to its official documentation page

---

*Generated from GRASS GIS 8.5 development documentation*

