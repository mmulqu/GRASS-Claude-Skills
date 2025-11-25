# v.overlay

**Category**: vector

## Description

Overlays two vector maps offering clip, intersection, difference, symmetrical difference, union operators.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.v_overlay(ainput,alayer="1",atype="auto",binput,blayer="1",btype="area",operator,output,olayer="1,0,0",snap=1e-8,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`ainput : str, required`**
   - Name of input vector map (A)
   - Or data source for direct OGR access
   - Used as: input, vector, name

2. **`alayer : str, optional`**
   - Layer number or name (vector map A)
   - Vector features can have category values in different layers. This number determines which layer to use. When used with direct OGR access this is the layer name.
   - Used as: input, layer

3. **`atype : str | list[str], optional`**
   - Feature type (vector map A)
   - Input feature type
   - Allowed values: line, area, auto

4. **`binput : str, required`**
   - Name of input vector map (B)
   - Or data source for direct OGR access
   - Used as: input, vector, name

5. **`blayer : str, optional`**
   - Layer number or name (vector map B)
   - Vector features can have category values in different layers. This number determines which layer to use. When used with direct OGR access this is the layer name.
   - Used as: input, layer

6. **`btype : str | list[str], optional`**
   - Feature type (vector map B)
   - Input feature type
   - Allowed values: area

7. **`operator : str, required`**
   - Operator defines features written to output vector map
   - Feature is written to output if the result of operation 'ainput operator binput' is true. Input feature is considered to be true, if category of given layer is defined.
   - Allowed values: and, or, not, xor
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/v.overlay.html#__tabbed_2_3) for all details)*

8. **`output : str, required`**
   - Name for output vector map
   - Used as: output, vector, name

9. **`olayer : str | list[str], optional`**
   - Output layer for new category, ainput and binput
   - If 0 or not given, the category is not written
   - Used as: input, layer

10. **`snap : float, optional`**
   - Snapping threshold for boundaries
   - Disable snapping with snap <= 0
   - Default: 1e-8

11. **`flags : str, optional`**
   - Allowed values: t
   - t
   - Do not create attribute table

12. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

13. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

14. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

15. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 15 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/v.overlay.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

v.overlay allows the user to overlay two vector maps. Features in ainput can be lines or areas and are cut with areas in binput .
Simple clipping can be performed with the and operator.

If areas in ainput are overlaid with areas in binput , it is
sometimes necessary to snap areas of binput to those of ainput ,
otherwise areas can go missing or many sliver areas can be created.
Snapping is enabled by default and can be disabled by setting the snap option to a negative value. Recommended values are between
0.00000001 and 0.0001. Using larger values for snapping can have
undesired side-effects, but may sometimes be necessary to get a clean
output (see example below). In general, it is recommended to start with
a small snapping threshold, gradually increasing the threshold until the
result is reasonably clean. Snapping modifies only boundaries in binput,
which are snapped to boundaries in ainput. Boundaries in ainput are
not modified.

---

## See Also

Related tools:
- [`v.clip`](https://grass.osgeo.org/grass-devel/manuals/v.clip.html)
- [`v.db.connect`](https://grass.osgeo.org/grass-devel/manuals/v.db.connect.html)
- [`v.select`](https://grass.osgeo.org/grass-devel/manuals/v.select.html)
- [`g.copy`](https://grass.osgeo.org/grass-devel/manuals/g.copy.html)

---

## Authors

Radim Blazek, ITC-Irst, Trento, Italy Markus Metz Speedup for large, complex input areas sponsored by mundialis

---

## Resources

- [Official v.overlay manual](https://grass.osgeo.org/grass-devel/manuals/v.overlay.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/v.overlay.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
