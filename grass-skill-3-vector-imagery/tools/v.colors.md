# v.colors

**Category**: vector

## Description

Creates/modifies the color table associated with a vector map.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.v_colors(map,layer="1",use="cat",column=None,range=None,color=None,raster=None,raster_3d=None,rules=None,rgb_column=None,flags=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`map : str, required`**
   - Name of vector map
   - Or data source for direct OGR access
   - Used as: input, vector, name

2. **`layer : str, optional`**
   - Layer number or name
   - Vector features can have category values in different layers. This number determines which layer to use. When used with direct OGR access this is the layer name.
   - Used as: input, layer

3. **`use : str, required`**
   - Source values
   - Allowed values: attr, cat, z
   - attr: read values from attribute table (requires <column> option)
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/v.colors.html#__tabbed_2_3) for all details)*

4. **`column : str, optional`**
   - Name of column containing numeric data
   - Required for use=attr
   - Used as: input, dbcolumn, name

5. **`range : tuple[float, float] | list[float] | str, optional`**
   - Manually set range (refers to 'column' option)
   - Ignored when 'rules' given
   - Used as: min,max

6. **`color : str, optional`**
   - Name of color table
   - Used as: input, colortable, style
   - Allowed values: aspect, aspectcolr, bcyr, bgyr, blues, byg, byr, celsius, corine, curvature, differences, elevation, etopo2, evi, fahrenheit, forest_cover, gdd, grass, greens, grey, grey.eq, grey.log, grey1.0, grey255, gyr, haxby, inferno, kelvin, magma, ndvi, ndwi, nlcd, oranges, plasma, population, population_dens, precipitation, precipitation_daily, precipitation_monthly, rainbow, ramp, random, reds, roygbiv, rstcurv, ryb, ryg, sepia, slope, soilmoisture, srtm, srtm_percent, srtm_plus, terrain, viridis, water, wave
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/v.colors.html#__tabbed_2_3) for all details)*

7. **`raster : str | np.ndarray, optional`**
   - Raster map from which to copy color table
   - Used as: input, raster, name

8. **`raster_3d : str, optional`**
   - 3D raster map from which to copy color table
   - Used as: input, raster_3d, name

9. **`rules : str | io.StringIO, optional`**
   - Path to rules file
   - Used as: input, file, name

10. **`rgb_column : str, optional`**
   - Name of color column to populate RGB values
   - If not given writes color table
   - Used as: input, dbcolumn, name

11. **`flags : str, optional`**
   - Allowed values: r, w, l, d, n, g, a, c
   - r
   - Remove existing color table
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/v.colors.html#__tabbed_2_3) for all details)*

12. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

13. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

14. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 14 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/v.colors.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

v.colors allows creating or modifying color table associated with a
vector map similarly to r.colors for raster maps.

Color rules are built from features category values ( use=cat ) or
numeric data column ( use=attr ) defined by column option. For 3D
vector maps is allowed to define color rules based on points or
centroids z-coordinate ( use=z ). 3D vector lines are not supported.

The raster option allows user to specify a raster map from which to
copy the color table, similarly raster_3d option for 3D raster map.
Without use=attr and column options, raster values will be
matched with categories. Use these two options to transfer raster colors
to vector attributes.

The rules color table type will cause v.colors to read color table
specifications from given file and will build the color table
accordingly. See r.colors manual page for details.

If the user specifies the -w flag, the current color table file for
the input map will not be overwritten. This means that the color table
is created only if the vector map does not already have a color table.
If this option is not specified, the color table will be created if one
does not exist, or modified if it does.

Alternatively the color rules can be stored in a string column
( rgb_column ) by saving the RRR:GGG:BBB values suitable for use with d.vect .

---

## See Also

Related tools:
- [`d.vect`](https://grass.osgeo.org/grass-devel/manuals/d.vect.html)
- [`r.colors`](https://grass.osgeo.org/grass-devel/manuals/r.colors.html)
- [`r.colors.out`](https://grass.osgeo.org/grass-devel/manuals/r.colors.out.html)
- [`r3.colors`](https://grass.osgeo.org/grass-devel/manuals/r3.colors.html)
- [`r3.colors.out`](https://grass.osgeo.org/grass-devel/manuals/r3.colors.out.html)
- [`v.colors.out`](https://grass.osgeo.org/grass-devel/manuals/v.colors.out.html)

---

## Authors

Martin Landa, OSGeoREL, Czech Technical University in Prague, Czech
Republic Huidae Cho

---

## Resources

- [Official v.colors manual](https://grass.osgeo.org/grass-devel/manuals/v.colors.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/v.colors.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
