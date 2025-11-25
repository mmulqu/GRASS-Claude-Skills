# Usage Guide - Display, General & Temporal Tools

Quick start guide for using GRASS GIS Display, General, and Temporal tools with the `grass.tools` API.

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

## Display Tools (d.*)

### Basic Map Display

```python
# Display raster map
tools.d_rast(map='elevation')

# Display vector map with styling
tools.d_vect(map='roads', color='red', width=2, icon='basic/circle')

# Display specific categories
tools.d_vect(map='landuse', where='cat=5', fill_color='green')
```

### Adding Map Elements

```python
# Add legend
tools.d_legend(raster='elevation', at='5,50,7,10', title='Elevation (m)')

# Add scale bar
tools.d_barscale(at='5,10', length=1000, units='kilometers')

# Add north arrow
tools.d_northarrow(at='85,90', fill_color='black')

# Add text annotation
tools.d_text(text='Study Area', at='50,95', color='black', size=5)
```

### Display Analysis Results

```python
# Display histogram
tools.d_histogram(map='elevation')

# Display color table
tools.d_colortable(map='elevation', at='10,90,5,8')

# Display grid
tools.d_grid(size='1000', color='gray')
```

## General Tools (g.*)

### Region Management

```python
# Set region from raster
tools.g_region(raster='elevation')

# Set region with specific bounds
tools.g_region(n=228500, s=215000, e=645000, w=630000, res=10)

# Save current region
tools.g_region(save='my_region')

# Load saved region
tools.g_region(region='my_region')

# Print region info
result = tools.g_region(flags='p')
```

### Map Management

```python
# List all raster maps
tools.g_list(type='raster')

# List maps matching pattern
tools.g_list(type='raster', pattern='elev*')

# Copy map
tools.g_copy(raster='elevation,elevation_backup')

# Rename map
tools.g_rename(raster='old_name,new_name')

# Remove map
tools.g_remove(type='raster', name='temp_map', flags='f')
```

### Projection Information

```python
# Get projection info
result = tools.g_proj(flags='p')

# Get projection in WKT format
result = tools.g_proj(flags='w')

# Get EPSG code
result = tools.g_proj(flags='g')
```

## Temporal Tools (t.*)

### Creating Temporal Datasets

```python
# Create space-time raster dataset
tools.t_create(output='temperature_series',
               type='strds',
               temporaltype='absolute',
               title='Monthly Temperature',
               description='2020-2023 temperature data')

# Create space-time vector dataset
tools.t_create(output='gps_tracks',
               type='stvds',
               temporaltype='absolute',
               title='GPS Tracking Data')
```

### Registering Maps

```python
# Register raster maps with timestamps
tools.t_register(input='temperature_series',
                 maps='temp_2020_01,temp_2020_02,temp_2020_03',
                 start='2020-01-01',
                 increment='1 months')

# Register from file
tools.t_register(input='temperature_series',
                 file='timestamps.txt')
```

### Temporal Analysis

```python
# Aggregate to annual averages
tools.t_rast_aggregate(input='temperature_series',
                       output='annual_temp',
                       basename='temp_year',
                       granularity='1 years',
                       method='average')

# Extract temporal subset
tools.t_rast_extract(input='temperature_series',
                     output='summer_temps',
                     where='start_time >= "2020-06-01" AND start_time < "2020-09-01"')

# Calculate series statistics
tools.t_rast_series(input='temperature_series',
                    output='temp_mean',
                    method='average')
```

### Temporal Queries

```python
# List temporal datasets
tools.t_list(type='strds')

# Get dataset info
tools.t_info(input='temperature_series')

# Sample at vector points
tools.t_vect_observe_strds(input='weather_stations',
                            strds='temperature_series',
                            output='station_temps',
                            column='temperature')
```

## Error Handling

```python
from grass.tools import ToolError

try:
    tools.d_rast(map='nonexistent_map')
except ToolError as e:
    print(f"Tool error: {e}")
```

## Working with Results

```python
# Some tools return ToolResult objects
result = tools.g_region(flags='p')
if result:
    print(result.stdout)  # Access output

# Most display tools return None
result = tools.d_rast(map='elevation')
# result is None
```

## Tips

1. **Set region first**: Always use `g.region` before processing
2. **Check display**: Use `d.mon` to start display monitor if needed
3. **Temporal data**: Register maps in chronological order
4. **Error handling**: Wrap tools in try/except for ToolError
5. **Documentation**: Read individual tool .md files for all parameters

## Example Workflow

```python
from grass.script import setup as gsetup
from grass.tools import Tools

# Initialize
gsetup.init('/path/to/grassdata', 'location', 'mapset')
tools = Tools()

# Set working region
tools.g_region(raster='elevation')

# Create visualization
tools.d_rast(map='elevation')
tools.d_vect(map='streams', color='blue', width=2)
tools.d_vect(map='roads', color='red', width=1)
tools.d_legend(raster='elevation', at='5,40,2,5')
tools.d_barscale(at='5,10')
tools.d_text(text='Watershed Study Area', at='50,95', size=4)

# Process temporal data
tools.t_create(output='precip_monthly', type='strds')
tools.t_register(input='precip_monthly', maps='precip_jan,precip_feb,...')
tools.t_rast_aggregate(input='precip_monthly', output='precip_annual',
                       granularity='1 years', method='sum')
```

---

For complete parameter details, see individual tool documentation in the `tools/` directory.

