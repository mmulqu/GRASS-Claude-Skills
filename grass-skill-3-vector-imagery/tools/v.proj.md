# v.proj

**Category**: vector

## Description

Re-projects a vector map from one project to the current project.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.v_proj(project,mapset=None,input=None,dbase=None,smax=10000,output=None,pipeline=None,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`project : str, required`**
   - Project (location) containing input vector map
   - Project name (not path to project)
   - Used as: input, location, name

2. **`mapset : str, optional`**
   - Mapset containing input vector map
   - Default: name of current mapset
   - Used as: input, mapset, name

3. **`input : str, optional`**
   - Name of input vector map to re-project
   - Used as: input, vector, name

4. **`dbase : str, optional`**
   - Path to GRASS database of input project
   - Default: path to the current GRASS database
   - Used as: input, dbase, path

5. **`smax : float, optional`**
   - Maximum segment length in meters in output vector map
   - Increases accuracy of reprojected shapes, disable with smax=0
   - Default: 10000

6. **`output : str, optional`**
   - Name for output vector map (default: input)
   - Used as: output, vector, name

7. **`pipeline : str, optional`**
   - PROJ pipeline for coordinate transformation

8. **`flags : str, optional`**
   - Allowed values: l, z, w, b
   - l
   - List vector maps in input mapset and exit
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/v.proj.html#__tabbed_2_3) for all details)*

9. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

10. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

11. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

12. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 12 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/v.proj.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

v.proj allows a user to convert a vector map in a specified mapset of
a specified project (different from current) with coordinate reference
system (CRS) of source project to the vector map in a current mapset of
current project with CRS of current project (both CRSs are defined in
their corresponding projects). The CRS information can be viewed and
managed with g.proj .

For an introduction to map CRSs (and the PROJ library), see the manual
page of r.proj .

---

## See Also

Related tools:
- [`g.proj`](https://grass.osgeo.org/grass-devel/manuals/g.proj.html)
- [`m.proj`](https://grass.osgeo.org/grass-devel/manuals/m.proj.html)
- [`r.proj`](https://grass.osgeo.org/grass-devel/manuals/r.proj.html)
- [`i.rectify`](https://grass.osgeo.org/grass-devel/manuals/i.rectify.html)
- [`r.stats`](https://grass.osgeo.org/grass-devel/manuals/r.stats.html)
- [`v.sample`](https://grass.osgeo.org/grass-devel/manuals/v.sample.html)
- [`v.split`](https://grass.osgeo.org/grass-devel/manuals/v.split.html)
- [`v.surf.idw`](https://grass.osgeo.org/grass-devel/manuals/v.surf.idw.html)
- [`v.surf.rst`](https://grass.osgeo.org/grass-devel/manuals/v.surf.rst.html)

---

## Authors

Irina Kosinovsky, US ARMY CERL M.L. Holko, USDA, SCS, NHQ-CGIS R.L. Glenn, USDA, SCS, NHQ-CGIS

---

## Resources

- [Official v.proj manual](https://grass.osgeo.org/grass-devel/manuals/v.proj.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/v.proj.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
