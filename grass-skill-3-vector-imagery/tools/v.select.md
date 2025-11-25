# v.select

**Category**: vector

## Description

Selects features from vector map (A) by features from other vector map (B).

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.v_select(ainput,alayer="1",atype="point,line,area",binput,blayer="1",btype="point,line,area",output,operator="overlap",relate=None,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`ainput : str, required`**
   - Name of input vector map
   - Input vector map from which to select features (A)
   - Used as: input, vector, name

2. **`alayer : str, optional`**
   - Layer number (vector map A)
   - Vector features can have category values in different layers. This number determines which layer to use. When used with direct OGR access this is the layer name.
   - Used as: input, layer

3. **`atype : str | list[str], optional`**
   - Feature type (vector map A)
   - Input feature type
   - Allowed values: point, line, boundary, centroid, area

4. **`binput : str, required`**
   - Name of input vector map
   - Query vector map (B)
   - Used as: input, vector, name

5. **`blayer : str, optional`**
   - Layer number (vector map B)
   - Vector features can have category values in different layers. This number determines which layer to use. When used with direct OGR access this is the layer name.
   - Used as: input, layer

6. **`btype : str | list[str], optional`**
   - Feature type (vector map B)
   - Input feature type
   - Allowed values: point, line, boundary, centroid, area

7. **`output : str, required`**
   - Name for output vector map
   - Used as: output, vector, name

8. **`operator : str, required`**
   - Operator defines required relation between features
   - A feature is written to output if the result of operation 'ainput operator binput' is true. An input feature is considered to be true, if category of given layer is defined.
   - Allowed values: overlap, equals, disjoint, intersects, touches, crosses, within, contains, overlaps, relate
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/v.select.html#__tabbed_2_3) for all details)*

9. **`relate : str, optional`**
   - Intersection Matrix Pattern used for 'relate' operator

10. **`flags : str, optional`**
   - Allowed values: t, c, r
   - t
   - Do not create attribute table
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/v.select.html#__tabbed_2_3) for all details)*

11. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

12. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

13. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

14. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 14 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/v.select.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

v.select allows the user to select features from a vector map by
features from another one.

Supported operators (without GEOS; using GRASS' own algorithm):

Supported operators (internally using GEOS - Geometry Engine, Open Source):

---

## See Also

Related tools:
- [`v.category`](https://grass.osgeo.org/grass-devel/manuals/v.category.html)
- [`v.clip`](https://grass.osgeo.org/grass-devel/manuals/v.clip.html)
- [`v.overlay`](https://grass.osgeo.org/grass-devel/manuals/v.overlay.html)
- [`v.extract`](https://grass.osgeo.org/grass-devel/manuals/v.extract.html)

---

## Authors

Radim Blazek GEOS support by Martin Landa, Czech Technical University in Prague,
Czech Republic ZIP code examples by Carol X. Garzon-Lopez, Trento, Italy

---

## Resources

- [Official v.select manual](https://grass.osgeo.org/grass-devel/manuals/v.select.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/v.select.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
