# g.region

**Category**: general

## Description

Manages the boundary definitions for the geographic region.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.g_region(region=None,raster=None,raster_3d=None,vector=None,n=None,s=None,e=None,w=None,t=None,b=None,rows=None,cols=None,res=None,res3=None,nsres=None,ewres=None,nsres3=None,ewres3=None,tbres=None,zoom=None,align=None,grow=None,save=None,format="plain",flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`region : str, optional`**
   - Set current region from named region
   - Used as: input, region, name

2. **`raster : str | list[str], optional`**
   - Set region to match raster map(s)
   - Used as: input, raster, name

3. **`raster_3d : str, optional`**
   - Set region to match 3D raster map(s) (both 2D and 3D values)
   - Used as: input, raster_3d, name

4. **`vector : str | list[str], optional`**
   - Set region to match vector map(s)
   - Used as: input, vector, name

5. **`n : str, optional`**
   - Value for the northern edge
   - Used as: value

6. **`s : str, optional`**
   - Value for the southern edge
   - Used as: value

7. **`e : str, optional`**
   - Value for the eastern edge
   - Used as: value

8. **`w : str, optional`**
   - Value for the western edge
   - Used as: value

9. **`t : str, optional`**
   - Value for the top edge
   - Used as: value

10. **`b : str, optional`**
   - Value for the bottom edge
   - Used as: value

11. **`rows : int, optional`**
   - Number of rows in the new region
   - Used as: value

12. **`cols : int, optional`**
   - Number of columns in the new region
   - Used as: value

13. **`res : str, optional`**
   - 2D grid resolution (north-south and east-west)
   - Used as: value

14. **`res3 : str, optional`**
   - 3D grid resolution (north-south, east-west and top-bottom)
   - Used as: value

15. **`nsres : str, optional`**
   - North-south 2D grid resolution
   - Used as: value

16. **`ewres : str, optional`**
   - East-west 2D grid resolution
   - Used as: value

17. **`nsres3 : str, optional`**
   - North-south 3D grid resolution
   - Used as: value

18. **`ewres3 : str, optional`**
   - East-west 3D grid resolution
   - Used as: value

19. **`tbres : str, optional`**
   - Top-bottom 3D grid resolution
   - Used as: value

20. **`zoom : str | np.ndarray, optional`**
   - Shrink region until it meets non-NULL data from this raster map
   - Used as: input, raster, name

21. **`align : str | np.ndarray, optional`**
   - Adjust region cells to cleanly align with this raster map
   - Used as: input, raster, name

22. **`grow : int, optional`**
   - Number of cells to add to each side of the current region extent
   - A negative number shrinks the current region extent
   - Used as: value

23. **`save : str, optional`**
   - Save current region settings in named region file
   - Used as: output, region, name

24. **`format : str, required`**
   - Output format
   - Used as: name
   - Allowed values: plain, shell, json
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/g.region.html#__tabbed_2_3) for all details)*

25. **`flags : str, optional`**
   - Allowed values: d, s, p, l, e, c, t, w, m, n, 3, b, g, f, a, u, o
   - d
   - Set from default region
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/g.region.html#__tabbed_2_3) for all details)*

26. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

27. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

28. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

29. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 29 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/g.region.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

The g.region module allows the user to manage the settings of the
current geographic region. These regional boundaries can be set by the
user directly and/or set from a region definition file (stored under the windows directory in the user's current mapset). The user can create,
modify, and store as many geographic region definitions as desired for
any given mapset. However, only one of these geographic region
definitions will be current at any given moment, for a specified mapset;
i.e., GRASS programs that respect the geographic region settings will
use the current geographic region settings.

---

## See Also

Related tools:
- [`g.access`](https://grass.osgeo.org/grass-devel/manuals/g.access.html)
- [`g.mapsets`](https://grass.osgeo.org/grass-devel/manuals/g.mapsets.html)
- [`g.proj`](https://grass.osgeo.org/grass-devel/manuals/g.proj.html)

---

## Resources

- [Official g.region manual](https://grass.osgeo.org/grass-devel/manuals/g.region.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/g.region.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
