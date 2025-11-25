# r.plane

**Category**: raster

## Description

Creates raster plane map given dip (inclination), aspect (azimuth) and one point.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_plane(output,dip=0.0,azimuth=0.0,easting,northing,elevation,type="FCELL",overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`output : str | type(np.ndarray) | type(np.array) | type(gs.array.array), required`**
   - Name for output raster map
   - Used as: output, raster, name

2. **`dip : float, required`**
   - Dip of plane in degrees
   - Allowed values: -90-90
   - Default: 0.0

3. **`azimuth : float, required`**
   - Azimuth of the plane in degrees
   - Allowed values: 0-360
   - Default: 0.0

4. **`easting : float, required`**
   - Easting coordinate of a point on the plane

5. **`northing : float, required`**
   - Northing coordinate of a point on the plane

6. **`elevation : float, required`**
   - Elevation coordinate of a point on the plane

7. **`type : str, optional`**
   - Type of raster map to be created
   - Storage type for resultant raster map
   - Allowed values: CELL, FCELL, DCELL
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/r.plane.html#__tabbed_2_3) for all details)*

8. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

9. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

10. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

11. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 11 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/r.plane.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | np.ndarray | tuple[np.ndarray] | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned. If an array type (e.g., np.ndarray) is used for one of the raster outputs, the result will be an array and will have the shape corresponding to the computational region. If an array type is used for more than one raster output, the result will be a tuple of arrays.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

r.plane creates a tilted plane raster map given user-specified
parameters for inclination, azimuth, and the geographic location of a
point on the plane. The angle orientations of the azimuth parameter increase
counter-clockwise, i.e., 0 degree = N, 45 degree = NW, 90 degree = W
etc.

Increasing values of the dip parameter progressively lower (or dip)
the northern half of the plane, and incline the southern half, assuming
the azimuth parameter is held constant at 0 degrees.

---

## Authors

Stefan Jäger (1994), University of Heidelberg during a stay at USGS Updated to GRASS 5.7 by Michael Barton, Arizona State University Full rewrite for GRASS 7 by Glynn Clements

---

## Resources

- [Official r.plane manual](https://grass.osgeo.org/grass-devel/manuals/r.plane.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.plane.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
