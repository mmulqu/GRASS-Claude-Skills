# v.lrs.label

**Category**: vector

## Description

Creates stationing from input lines, and linear reference system.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.v_lrs_label(input,output,llayer="1",rsdriver="sqlite",rsdatabase="$GISDBASE/$LOCATION_NAME/$MAPSET/sqlite/sqlite.db",rstable,labels=None,offset="50,100,25,25",xoffset=25,yoffset=5,reference="center",font="standard",size=100,color="black",width=1,highlight_color="none",highlight_width=0,bgcolor="none",border="none",opaque="yes",overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str, required`**
   - Name of input vector map
   - Input vector map containing lines
   - Used as: input, vector, name

2. **`output : str, required`**
   - Output vector map where stationing will be written
   - Used as: output, vector, name

3. **`llayer : str, optional`**
   - Layer number or name
   - Line layer
   - Used as: input, layer

4. **`rsdriver : str, optional`**
   - Driver name for reference system table
   - Allowed values: dbf, odbc, ogr, pg, sqlite
   - Default: sqlite

5. **`rsdatabase : str, optional`**
   - Database name for reference system table
   - Default: $GISDBASE/$LOCATION_NAME/$MAPSET/sqlite/sqlite.db

6. **`rstable : str, required`**
   - Name of the reference system table

7. **`labels : str, optional`**
   - Label file
   - Used as: output, Labels

8. **`offset : str | list[str], optional`**
   - PM left, MP right, stationing left, stationing right offset
   - Default: 50,100,25,25

9. **`xoffset : float, optional`**
   - Offset label in label x-direction in map units
   - Default: 25

10. **`yoffset : float, optional`**
   - Offset label in label y-direction in map units
   - Default: 5

11. **`reference : str, optional`**
   - Reference position
   - Allowed values: center, left, right, upper, lower
   - Default: center

12. **`font : str, optional`**
   - Font
   - Default: standard

13. **`size : int, optional`**
   - Label size (in map-units)
   - Allowed values: 1-1000
   - Default: 100

14. **`color : str, optional`**
   - Text color
   - Either a standard color name or R:G:B triplet
   - Used as: input, color, name

15. **`width : int, optional`**
   - Line width of text
   - Only for d.label output
   - Allowed values: 1-100

16. **`highlight_color : str, optional`**
   - Highlight color for text
   - Either a standard color name, R:G:B triplet, or "none"
   - Used as: input, color, name

17. **`highlight_width : int, optional`**
   - Line width of highlight color
   - Only for d.label output
   - Allowed values: 0-100

18. **`bgcolor : str, optional`**
   - Background color
   - Either a standard color name, R:G:B triplet, or "none"
   - Used as: input, color, name

19. **`border : str, optional`**
   - Border color
   - Either a standard color name, R:G:B triplet, or "none"
   - Used as: input, color, name

20. **`opaque : str, optional`**
   - Opaque to vector
   - Only relevant if background color is selected
   - Allowed values: yes, no

21. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

22. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

23. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

24. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 24 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/v.lrs.label.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

v.lrs.label generates LRS labels for pretty-printing of a LRS. This
example is written for the Spearfish dataset (it continues the example
from v.lrs.create ).

---

## See Also

Related tools:
- [`v.lrs.create`](https://grass.osgeo.org/grass-devel/manuals/v.lrs.create.html)
- [`v.lrs.segment`](https://grass.osgeo.org/grass-devel/manuals/v.lrs.segment.html)
- [`v.lrs.where`](https://grass.osgeo.org/grass-devel/manuals/v.lrs.where.html)
- [`d.labels`](https://grass.osgeo.org/grass-devel/manuals/d.labels.html)
- [`v.label`](https://grass.osgeo.org/grass-devel/manuals/v.label.html)

---

## Authors

Radim Blazek, ITC-irst/MPA Solutions Documentation update (based on above journal article and available
fragments): Markus Neteler

---

## Resources

- [Official v.lrs.label manual](https://grass.osgeo.org/grass-devel/manuals/v.lrs.label.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/v.lrs.label.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
