# d.vect.chart

**Category**: display

## Description

Displays charts of vector data in the active frame on the graphics monitor.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.d_vect_chart(map,type="point,line,boundary,centroid",layer="1",chart_type="pie",columns,size_column=None,size=40,scale=1,outline_color="black",colors="black",max_ref=None,flags=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`map : str, required`**
   - Name of vector map
   - Or data source for direct OGR access
   - Used as: input, vector, name

2. **`type : str | list[str], optional`**
   - Input feature type
   - Allowed values: point, line, boundary, centroid, area
   - Default: point,line,boundary,centroid

3. **`layer : str, optional`**
   - Layer number or name
   - Vector features can have category values in different layers. This number determines which layer to use. When used with direct OGR access this is the layer name.
   - Used as: input, layer

4. **`chart_type : str, optional`**
   - Chart type
   - Allowed values: pie, bar
   - Default: pie

5. **`columns : str | list[str], required`**
   - Attribute columns containing data
   - Used as: input, dbcolumn, name

6. **`size_column : str, optional`**
   - Column used for pie chart size
   - Used as: input, dbcolumn, name

7. **`size : int, optional`**
   - Size of chart (diameter for pie, total width for bar)
   - Default: 40

8. **`scale : float, optional`**
   - Scale for size (to get size in pixels)
   - Default: 1

9. **`outline_color : str, optional`**
   - Outline color
   - Either a standard color name or R:G:B triplet
   - Used as: input, color, name

10. **`colors : str | list[str], optional`**
   - Colors used to fill charts
   - Either a standard color name or R:G:B triplet
   - Used as: input, color, name

11. **`max_ref : float | list[float] | str, optional`**
   - Maximum value used for bar plot reference

12. **`flags : str, optional`**
   - Allowed values: c, l, 3
   - c
   - Center the bar chart around a data point
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/d.vect.chart.html#__tabbed_2_3) for all details)*

13. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

14. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

15. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 15 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/d.vect.chart.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

d.vect.chart displays charts for GRASS vector data in the active frame
on the graphics monitor.

---

## See Also

Related tools:
- [`d.erase`](https://grass.osgeo.org/grass-devel/manuals/d.erase.html)
- [`d.vect`](https://grass.osgeo.org/grass-devel/manuals/d.vect.html)
- [`d.vect.thematic`](https://grass.osgeo.org/grass-devel/manuals/d.vect.thematic.html)
- [`d.what.vect`](https://grass.osgeo.org/grass-devel/manuals/d.what.vect.html)
- [`d.rast`](https://grass.osgeo.org/grass-devel/manuals/d.rast.html)

---

## Resources

- [Official d.vect.chart manual](https://grass.osgeo.org/grass-devel/manuals/d.vect.chart.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/d.vect.chart.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
