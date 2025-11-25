# r.geomorphon

**Category**: raster

## Description

Calculates geomorphons (terrain forms) and associated geometry using machine vision approach.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_geomorphon(elevation,forms=None,ternary=None,positive=None,negative=None,intensity=None,exposition=None,range=None,variance=None,elongation=None,azimuth=None,extend=None,width=None,search=3,skip=0,flat=1,dist=0,comparison="anglev1",coordinates=None,profiledata=None,profileformat=None,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`elevation : str | np.ndarray, required`**
   - Name of input elevation raster map
   - Used as: input, raster, name

2. **`forms : str | type(np.ndarray) | type(np.array) | type(gs.array.array), optional`**
   - Most common geomorphic forms
   - Used as: output, raster, name

3. **`ternary : str | type(np.ndarray) | type(np.array) | type(gs.array.array), optional`**
   - Code of ternary patterns
   - Used as: output, raster, name

4. **`positive : str | type(np.ndarray) | type(np.array) | type(gs.array.array), optional`**
   - Code of binary positive patterns
   - Used as: output, raster, name

5. **`negative : str | type(np.ndarray) | type(np.array) | type(gs.array.array), optional`**
   - Code of binary negative patterns
   - Used as: output, raster, name

6. **`intensity : str | type(np.ndarray) | type(np.array) | type(gs.array.array), optional`**
   - Rasters containing mean relative elevation of the form
   - Used as: output, raster, name

7. **`exposition : str | type(np.ndarray) | type(np.array) | type(gs.array.array), optional`**
   - Rasters containing maximum difference between extend and central cell
   - Used as: output, raster, name

8. **`range : str | type(np.ndarray) | type(np.array) | type(gs.array.array), optional`**
   - Rasters containing difference between max and min elevation of the form extend
   - Used as: output, raster, name

9. **`variance : str | type(np.ndarray) | type(np.array) | type(gs.array.array), optional`**
   - Rasters containing variance of form boundary
   - Used as: output, raster, name

10. **`elongation : str | type(np.ndarray) | type(np.array) | type(gs.array.array), optional`**
   - Rasters containing local elongation
   - Used as: output, raster, name

11. **`azimuth : str | type(np.ndarray) | type(np.array) | type(gs.array.array), optional`**
   - Rasters containing local azimuth of the elongation
   - Used as: output, raster, name

12. **`extend : str | type(np.ndarray) | type(np.array) | type(gs.array.array), optional`**
   - Rasters containing local extend (area) of the form
   - Used as: output, raster, name

13. **`width : str | type(np.ndarray) | type(np.array) | type(gs.array.array), optional`**
   - Rasters containing local width of the form
   - Used as: output, raster, name

14. **`search : int, required`**
   - Outer search radius
   - Default: 3

15. **`skip : int, required`**
   - Inner search radius
   - Default: 0

16. **`flat : float, required`**
   - Flatness threshold (degrees)
   - Default: 1

17. **`dist : float, required`**
   - Flatness distance, zero for none
   - Default: 0

18. **`comparison : str, optional`**
   - Comparison mode for zenith/nadir line-of-sight search
   - Allowed values: anglev1, anglev2, anglev2_distance
   - Default: anglev1

19. **`coordinates : tuple[float, float] | list[float] | str, optional`**
   - Coordinates to profile
   - Used as: input, coords, east,north

20. **`profiledata : str, optional`**
   - Profile output file name ("-" for stdout)
   - Used as: output, file, name

21. **`profileformat : str, optional`**
   - Profile output format
   - Allowed values: json, yaml, xml

22. **`flags : str, optional`**
   - Allowed values: m, e
   - m
   - Use meters to define search units (default is cells)
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/r.geomorphon.html#__tabbed_2_3) for all details)*

23. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

24. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

25. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

26. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 26 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/r.geomorphon.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | np.ndarray | tuple[np.ndarray] | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned. If an array type (e.g., np.ndarray) is used for one of the raster outputs, the result will be an array and will have the shape corresponding to the computational region. If an array type is used for more than one raster output, the result will be a tuple of arrays.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

r.geomorphon calculates terrain forms using machine-vison technique
called geomorphons.



Geomorphon is a new concept of presentation and analysis of terrain
forms. This concept utilises 8-tuple pattern of the visibility
neighbourhood and breaks well known limitation of standard calculus
approach where all terrain forms cannot be detected in a single window
size. The pattern arises from a comparison of a focus pixel with its
eight neighbors starting from the one located to the east and continuing
counterclockwise producing ternary operator. For example, a tuple
{+,-,-,-,0,+,+,+} describes one possible pattern of relative measures
{higher, lower, lower, lower, equal, higher, higher, higher} for pixels
surrounding the focus pixel. It is important to stress that the
visibility neighbors are not necessarily an immediate neighbors of
the focus pixel in the grid, but the pixels determined from the
line-of-sight principle along the eight principal directions. This
principle relates surface relief and horizontal distance by means of
so-called zenith and nadir angles along the eight principal compass
directions. The ternary operator converts the information contained in
all the pairs of zenith and nadir angles into the ternary pattern
(8-tuple). The result depends on the values of two parameters: search
radius (L) and relief threshold (d). The search radius is the maximum
allowable distance for calculation of zenith and nadir angles. The
relief threshold is a minimum value of difference between LOSs angle
(zenith and nadir) that is considered significantly different from the
horizon. Two lines-of-sight are necessary due to zenith LOS only, does
not detect positive forms correctly.

There are 3**8 = 6561 possible ternary patterns (8-tuples). By
removing all patterns that are the result of either rotation or
reflection of other patterns, a set of 498 patterns remains, referred to
as geomorphons. This is a comprehensive and exhaustive set of idealized
landforms that are independent of the size, relief, and orientation of
the actual landform.

Form recognition depends on two free parameters: Search radius and flatness threshold . Using larger values of L and is tantamount to
terrain classification from a higher and wider perspective, whereas
using smaller values of L and is tantamount to terrain classification
from a local point of view. A character of the map depends on the value
of L. Using small value of L results in the map that correctly
identifies landforms if their size is smaller than L; landforms having
larger sizes are broken down into components. Using larger values of L
allows simultaneous identification of landforms on variety of sizes in
expense of recognition smaller, second-order forms. There are two
additional parameters: skip radius used to eliminate impact of small
irregularities. On the contrary flatness distance eliminates the
impact of very high distance (in meters) of search radius which may not
detect elevation difference if this is at very far distance. Important
especially with low resolution DEMS.

---

## See Also

Related tools:
- [`r.param.scale`](https://grass.osgeo.org/grass-devel/manuals/r.param.scale.html)

---

## Authors

Jarek Jasiewicz, Tomek Stepinski (merit contribution)

---

## Resources

- [Official r.geomorphon manual](https://grass.osgeo.org/grass-devel/manuals/r.geomorphon.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.geomorphon.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
