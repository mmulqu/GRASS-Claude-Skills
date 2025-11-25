# Usage Guide - Vector & Imagery Tools

Quick start guide for using GRASS GIS Vector and Imagery tools with the `grass.tools` API.

## Setup

### Initialize GRASS Session

```python
from grass.script import setup as gsetup
from grass.tools import Tools

# Point to your GRASS database
gsetup.init('/path/to/grassdata', 'location_name', 'mapset_name')

# Create tools object
tools = Tools()
```

## Vector Tools (v.*)

### Vector Import/Export

```python
# Import from shapefile
tools.v_in_ogr(input='/path/to/data.shp', output='imported_vector')

# Import with SQL filter
tools.v_in_ogr(input='/path/to/data.shp',
               output='filtered',
               where='POPULATION > 10000')

# Export to shapefile
tools.v_out_ogr(input='vector_map',
                output='/path/to/output.shp',
                format='ESRI_Shapefile')

# Export to GeoJSON
tools.v_out_ogr(input='vector_map',
                output='/path/to/output.geojson',
                format='GeoJSON')
```

### Topology & Geometry

```python
# Build topology
tools.v_build(map='roads')

# Clean topology errors
tools.v_clean(input='roads',
              output='roads_clean',
              tool='break,rmdupl,rmdangle',
              threshold='0.001')

# Generalize features
tools.v_generalize(input='roads',
                   output='roads_simplified',
                   method='douglas',
                   threshold=10)

# Simplify geometry
tools.v_simplify(input='boundary',
                 output='boundary_simple',
                 threshold=50)
```

### Spatial Operations

```python
# Create buffer
tools.v_buffer(input='roads',
               output='road_buffer',
               distance=100)

# Overlay analysis
tools.v_overlay(ainput='parcels',
                binput='flood_zones',
                output='affected_parcels',
                operator='and')  # Options: and, or, not, xor

# Clip by region
tools.v_clip(input='roads',
             clip='study_area',
             output='roads_clipped')

# Dissolve boundaries
tools.v_dissolve(input='parcels',
                 output='dissolved',
                 column='owner')

# Patch multiple vectors
tools.v_patch(input='tile1,tile2,tile3',
              output='merged')
```

### Spatial Analysis

```python
# Calculate distances
tools.v_distance(from_='points',
                 to='lines',
                 upload='dist',
                 column='distance')

# Voronoi diagrams
tools.v_voronoi(input='points',
                output='voronoi_polygons')

# Delaunay triangulation
tools.v_delaunay(input='points',
                 output='triangulation')

# Convex hull
tools.v_hull(input='points',
             output='hull')

# Kernel density
tools.v_kernel(input='crime_points',
               output='density',
               radius=1000)
```

### Network Analysis

```python
# Prepare network
tools.v_net(input='roads',
            output='road_network',
            operation='connect',
            threshold=10)

# Find shortest path
tools.v_net_path(input='road_network',
                 output='route',
                 start_coordinates='x1,y1',
                 end_coordinates='x2,y2')

# Network distances
tools.v_net_distance(input='road_network',
                     output='distances',
                     from_layer=1,
                     to_layer=1)

# Isochrones
tools.v_net_iso(input='road_network',
                output='service_areas',
                center_cats='1',
                costs='300,600,900')

# Traveling salesman
tools.v_net_salesman(input='road_network',
                     output='tour',
                     center_cats='1',
                     arc_layer=1)
```

### Attribute Operations

```python
# Query attributes
result = tools.v_db_select(map='roads')

# Query specific columns
result = tools.v_db_select(map='roads',
                           columns='name,length,speed')

# Query with WHERE
result = tools.v_db_select(map='roads',
                           where='speed > 50')

# Update attributes
tools.v_db_update(map='roads',
                  column='paved',
                  value='1',
                  where='type="highway"')

# Add column
tools.v_db_addcolumn(map='roads',
                     columns='width double precision')

# Join tables
tools.v_db_join(map='parcels',
                column='parcel_id',
                other_table='owners',
                other_column='id')

# Sample raster at vector points
tools.v_what_rast(map='sample_points',
                  raster='elevation',
                  column='elev_value')

# Calculate raster stats per vector
tools.v_rast_stats(map='watersheds',
                   raster='precipitation',
                   column_prefix='precip',
                   method='average,sum')
```

### Vector Selection & Extraction

```python
# Extract features by category
tools.v_extract(input='parcels',
                output='selected',
                cats='1-100,500,600-700')

# Extract by attributes
tools.v_extract(input='parcels',
                output='large_parcels',
                where='area > 5000')

# Select by location
tools.v_select(ainput='points',
               binput='polygons',
               output='points_in_polygons',
               operator='within')
```

## Imagery Tools (i.*)

### Image Groups

```python
# Create imagery group
tools.i_group(group='landsat',
              subgroup='visible',
              input='band1,band2,band3')

# Create full multispectral group
tools.i_group(group='landsat',
              subgroup='all_bands',
              input='band1,band2,band3,band4,band5,band6,band7')
```

### Image Classification

```python
# Unsupervised classification (clustering)
tools.i_cluster(group='landsat',
                subgroup='all_bands',
                signaturefile='cluster_sig',
                classes=10,
                iterations=30)

# Maximum likelihood classification
tools.i_maxlik(group='landsat',
               subgroup='all_bands',
               signaturefile='cluster_sig',
               output='classified')

# SMAP classification
tools.i_smap(group='landsat',
             subgroup='all_bands',
             signaturefile='training_sig',
             output='classified_smap')

# Image segmentation
tools.i_segment(group='landsat',
                output='segments',
                threshold=0.5,
                minsize=10)
```

### Vegetation Indices

```python
# Calculate NDVI
tools.i_vi(red='band3',
           nir='band4',
           output='ndvi',
           viname='ndvi')

# Calculate EVI
tools.i_vi(red='band3',
           nir='band4',
           blue='band1',
           output='evi',
           viname='evi')

# Multiple indices at once
for index in ['ndvi', 'evi', 'savi']:
    tools.i_vi(red='band3',
               nir='band4',
               blue='band1',
               output=index,
               viname=index)
```

### Atmospheric Correction

```python
# Landsat top-of-atmosphere reflectance
tools.i_landsat_toar(input='lsat_',
                     output='lsat_toar_',
                     sensor='oli8',
                     metfile='LC08_metadata.txt')

# Atmospheric correction
tools.i_atcorr(input='band4',
               output='band4_corrected',
               parameters='atcorr_params.txt',
               elevation='dem')

# Topographic correction
tools.i_topo_corr(input='band4',
                  output='band4_topcorr',
                  basemap='dem',
                  zenith=30)
```

### Image Enhancement

```python
# Principal Component Analysis
tools.i_pca(input='band1,band2,band3,band4',
            output='pca')

# Color enhancement
tools.i_colors_enhance(red='band3',
                       green='band2',
                       blue='band1')

# Pan-sharpening (Brovey)
tools.i_fusion_brovey(ms1='band2',
                      ms2='band3',
                      ms3='band4',
                      pan='band8',
                      output_prefix='pansharp_')
```

### Image Transformation

```python
# FFT
tools.i_fft(input_image='aerial',
            real='fft_real',
            imaginary='fft_imag')

# Inverse FFT
tools.i_ifft(real='fft_real',
             imaginary='fft_imag',
             output='reconstructed')

# Georectification
tools.i_rectify(group='unrectified',
                output='rectified',
                extension='_rect')
```

### Image Analysis

```python
# Albedo calculation
tools.i_albedo(input='band1,band2,band3,band4,band5,band7',
               output='albedo')

# Emissivity
tools.i_emissivity(input='ndvi',
                   output='emissivity')

# Zero-crossing edge detection
tools.i_zc(input='elevation',
           output='edges',
           threshold=10)
```

## Error Handling

```python
from grass.tools import ToolError

try:
    tools.v_buffer(input='nonexistent', output='buffer', distance=100)
except ToolError as e:
    print(f"Tool error: {e}")

try:
    tools.i_vi(red='band3', nir='band4', output='ndvi', viname='ndvi')
except ToolError as e:
    print(f"Imagery error: {e}")
```

## Example Workflows

### Vector Analysis Workflow

```python
from grass.script import setup as gsetup
from grass.tools import Tools

gsetup.init('/path/to/grassdata', 'location', 'mapset')
tools = Tools()

# Import data
tools.v_in_ogr(input='roads.shp', output='roads')
tools.v_in_ogr(input='parcels.shp', output='parcels')

# Clean topology
tools.v_clean(input='roads', output='roads_clean', tool='break,rmdupl')

# Create buffer around roads
tools.v_buffer(input='roads_clean', output='road_buffer', distance=50)

# Find parcels within buffer
tools.v_overlay(ainput='parcels',
                binput='road_buffer',
                output='parcels_near_roads',
                operator='and')

# Calculate areas
tools.v_to_db(map='parcels_near_roads',
              option='area',
              columns='area')
```

### Satellite Image Classification Workflow

```python
# Create image group
tools.i_group(group='landsat_scene',
              subgroup='all',
              input='B1,B2,B3,B4,B5,B6,B7')

# Atmospheric correction
tools.i_landsat_toar(input='B',
                     output='TOAR_',
                     sensor='oli8',
                     metfile='metadata.txt')

# Calculate NDVI for training
tools.i_vi(red='TOAR_4',
           nir='TOAR_5',
           output='ndvi',
           viname='ndvi')

# Unsupervised classification
tools.i_cluster(group='landsat_scene',
                subgroup='all',
                signaturefile='clusters',
                classes=15)

tools.i_maxlik(group='landsat_scene',
               subgroup='all',
               signaturefile='clusters',
               output='landcover')

# Calculate class areas
tools.r_report(map='landcover', units='h', flags='n')
```

## Tips

1. **Topology**: Always build topology with `v.build` after creating/modifying vectors
2. **Clean data**: Use `v.clean` to fix topology errors before analysis
3. **Network analysis**: Must use `v.net` to prepare network before network tools
4. **Image groups**: Create groups before classification
5. **Signatures**: Generate good training signatures for supervised classification
6. **Indices**: Calculate vegetation indices for land cover analysis

---

For complete parameter details, see individual tool documentation in the `tools/` directory.

