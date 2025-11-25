# r.transect

**Category**: raster

## Description

Outputs raster map layer values lying along user defined transect line(s).

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_transect(map,line,null_value="*",flags=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`map : str | np.ndarray, required`**
   - Raster map to be queried
   - Used as: input, raster, name

2. **`line : list[tuple[str, str, str, str]] | tuple[str, str, str, str] | list[str] | str, required`**
   - Transect definition
   - Used as: east,north,azimuth,distance

3. **`null_value : str, optional`**
   - String representing NULL value
   - Used as: string
   - Default: *

4. **`flags : str, optional`**
   - Allowed values: g
   - g
   - Output easting and northing in first two columns of four column output

5. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

6. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

7. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

r.transect outputs, in ASCII, the values in a raster map which lie
along one or more user-defined transect lines. The transects are
described by their starting coordinates, azimuth, and distance.

The line parameter is a definition of (each) transect line,
specified by the geographic coordinates of its starting point ( easting,
northing ), the angle and direction of its travel ( azimuth ), and its
distance ( distance ).

The azimuth is an angle, in degrees, measured to the east of north.
The distance is in map units (meters for a metered database, like
UTM).

The null parameter can optionally be set to change the character
string representing null values.

---

## See Also

Related tools:
- [`r.profile`](https://grass.osgeo.org/grass-devel/manuals/r.profile.html)

---

## Resources

- [Official r.transect manual](https://grass.osgeo.org/grass-devel/manuals/r.transect.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.transect.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
