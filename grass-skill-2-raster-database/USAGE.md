# Usage Guide - Raster & Database Tools

Quick start guide for using GRASS GIS Raster and Database tools with the `grass.tools` API.

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

## Raster Tools (r.*)

### Terrain Analysis

```python
# Calculate slope and aspect
tools.r_slope_aspect(elevation='dem',
                     slope='slope',
                     aspect='aspect',
                     format='degrees')

# Generate contours
tools.r_contour(input='dem', output='contours', step=10)

# Create shaded relief
tools.r_relief(input='dem', output='hillshade', altitude=45, azimuth=315)

# Detect landforms
tools.r_geomorphon(elevation='dem', forms='landforms')

# Calculate watersheds
tools.r_watershed(elevation='dem',
                  threshold=1000,
                  basin='basins',
                  stream='streams',
                  accumulation='flow_acc')
```

### Raster Algebra & Analysis

```python
# Raster calculator (simple)
tools.r_mapcalc(expression='ndvi = float(nir - red) / (nir + red)')

# Neighborhood analysis
tools.r_neighbors(input='elevation',
                  output='smoothed',
                  method='average',
                  size=5)

# Statistical analysis
tools.r_univar(map='elevation', flags='g')

# Zonal statistics
tools.r_statistics(base='zones',
                   cover='values',
                   method='average',
                   output='zone_means')

# Correlation
tools.r_covar(map='band1,band2,band3,band4')
```

### Interpolation

```python
# IDW interpolation
tools.r_surf_idw(input='points', output='surface', column='value')

# Interpolate from contours
tools.r_surf_contour(input='contours', output='dem')

# Resample with interpolation
tools.r_resamp_interp(input='dem_10m',
                      output='dem_30m',
                      method='bilinear')

# Resample with statistics
tools.r_resamp_stats(input='dem_10m',
                     output='dem_100m',
                     method='average')
```

### Raster Processing

```python
# Reclassify
tools.r_reclass(input='elevation',
                output='elev_classes',
                rules='reclass_rules.txt')

# Recode values
tools.r_recode(input='landuse',
               output='landuse_new',
               rules='recode_rules.txt')

# Manage NULL values
tools.r_null(map='dem', setnull='0')

# Cross-tabulate rasters
tools.r_cross(input='soil,landuse',
              output='soil_landuse')

# Patch rasters
tools.r_patch(input='tile1,tile2,tile3', output='mosaic')
```

### Raster Conversion

```python
# Convert to vector
tools.r_to_vect(input='landuse',
                output='landuse_poly',
                type='area')

# Convert to points
tools.r_to_vect(input='elevation',
                output='elev_points',
                type='point')
```

### Spatial Analysis

```python
# Create buffers
tools.r_buffer(input='lakes',
               output='lake_buffer',
               distances='100,200,300')

# Cost surface analysis
tools.r_cost(input='friction',
             output='cost',
             start_coordinates='x,y')

# Drainage path
tools.r_drain(input='dem',
              output='path',
              start_coordinates='x,y')

# Distance calculations
tools.r_grow_distance(input='features',
                      distance='dist_map')

# Clump cells
tools.r_clump(input='landuse',
              output='clumps')
```

### Raster Statistics

```python
# Basic statistics
result = tools.r_univar(map='elevation', flags='g')

# Extended statistics
result = tools.r_univar(map='elevation', flags='e')

# Statistics by zones
tools.r_univar(map='values',
               zones='regions',
               output='stats.txt')

# Quantiles
result = tools.r_quantile(input='elevation', percentiles='25,50,75')
```

## Database Tools (db.*)

### Querying Data

```python
# Simple query
result = tools.db_select(sql='SELECT * FROM roads')

# Query with WHERE clause
result = tools.db_select(sql='SELECT name, length FROM roads WHERE length > 1000')

# Query specific table
result = tools.db_select(table='parcels')

# Query with conditions
result = tools.db_select(table='parcels',
                         columns='owner,area',
                         where='area > 5000')
```

### Database Operations

```python
# Execute SQL statement
tools.db_execute(sql='UPDATE roads SET paved=1 WHERE type="highway"')

# Multiple statements
tools.db_execute(sql_file='updates.sql')

# Create table
tools.db_execute(sql='CREATE TABLE new_table (id INTEGER, name VARCHAR(50))')

# Insert data
tools.db_execute(sql='INSERT INTO new_table VALUES (1, "Test")')
```

### Database Management

```python
# List tables
result = tools.db_tables(flags='p')

# List columns
result = tools.db_columns(table='roads')

# Describe table structure
result = tools.db_describe(table='roads', flags='c')

# Copy table
tools.db_copy(from_table='roads',
              to_table='roads_backup')

# Drop table
tools.db_execute(sql='DROP TABLE temp_table')
```

### Database Connection

```python
# Show connection settings
result = tools.db_connect(flags='p')

# Set database connection
tools.db_connect(driver='sqlite',
                 database='$GISDBASE/$LOCATION_NAME/$MAPSET/sqlite.db')

# Login (for remote databases)
tools.db_login(driver='pg',
               database='grassdb',
               user='username',
               password='password')
```

## Error Handling

```python
from grass.tools import ToolError

try:
    tools.r_mapcalc(expression='result = nonexistent_map * 2')
except ToolError as e:
    print(f"Tool error: {e}")

try:
    tools.db_select(sql='SELECT * FROM nonexistent_table')
except ToolError as e:
    print(f"Database error: {e}")
```

## Example Workflows

### Terrain Analysis Workflow

```python
from grass.script import setup as gsetup
from grass.tools import Tools

gsetup.init('/path/to/grassdata', 'location', 'mapset')
tools = Tools()

# Set region
tools.g_region(raster='dem')

# Calculate terrain parameters
tools.r_slope_aspect(elevation='dem', slope='slope', aspect='aspect')
tools.r_relief(input='dem', output='hillshade')

# Calculate watersheds
tools.r_watershed(elevation='dem',
                  threshold=1000,
                  basin='basins',
                  stream='streams')

# Smooth DEM
tools.r_neighbors(input='dem', output='dem_smooth', method='average', size=5)

# Get statistics
result = tools.r_univar(map='slope', flags='g')
print(result.stdout)
```

### Raster Classification Workflow

```python
# Calculate vegetation index
tools.r_mapcalc(expression='ndvi = float(nir - red) / (nir + red)')

# Classify NDVI
reclass_rules = '''0:0.2:1:bare soil
0.2:0.4:2:sparse vegetation
0.4:0.6:3:moderate vegetation  
0.6:1.0:4:dense vegetation'''

with open('ndvi_reclass.txt', 'w') as f:
    f.write(reclass_rules)

tools.r_reclass(input='ndvi',
                output='veg_classes',
                rules='ndvi_reclass.txt')

# Calculate statistics by class
tools.r_statistics(base='veg_classes',
                   cover='biomass',
                   method='average',
                   output='biomass_by_class')
```

## Tips

1. **Set region**: Always use `g.region` before raster operations
2. **Check NULL values**: Use `r.null` to handle missing data
3. **Use r.mapcalc**: For complex raster algebra
4. **Memory**: Large rasters may need more memory; adjust with `--mem`
5. **Temporary maps**: Use meaningful names or clean up with `g.remove`
6. **Database**: Check connection with `db.connect -p` first

---

For complete parameter details, see individual tool documentation in the `tools/` directory.

