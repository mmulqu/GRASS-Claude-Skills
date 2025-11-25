# i.group

**Category**: imagery

## Description

Creates, edits, and lists groups of imagery data.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.i_group(group,subgroup=None,input=None,file=None,format="plain",flags=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`group : str, required`**
   - Name of imagery group
   - Used as: input, group, name

2. **`subgroup : str, optional`**
   - Name of imagery subgroup
   - Used as: input, subgroup, name

3. **`input : str | list[str], optional`**
   - Name of raster map(s) to include in group
   - Used as: input, raster, name

4. **`file : str | io.StringIO, optional`**
   - Input file with one raster map name per line
   - Used as: input, file, name

5. **`format : str, required`**
   - Output format
   - Used as: name
   - Allowed values: plain, shell, json
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/i.group.html#__tabbed_2_3) for all details)*

6. **`flags : str, optional`**
   - Allowed values: r, l, s, g
   - r
   - Remove selected files from specified group or subgroup
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/i.group.html#__tabbed_2_3) for all details)*

7. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

8. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

9. **`superquiet : bool, optional`**
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

i.group allows the user to collect raster map layers in an imagery
group by assigning them to user-named subgroups or other groups. This
enables the user to run analyses on any combination of the raster map
layers in a group. The user creates the groups and subgroups and selects
the raster map layers that are to reside in them. Imagery analysis
programs like g.gui.gcp , i.rectify , i.ortho.photo and others ask the user for the name
of an imagery group whose data are to be analyzed. Imagery analysis
programs like i.cluster and i.maxlik ask the user for the imagery group and imagery subgroup whose data are
to be analyzed.

---

## See Also

Related tools:

---

## Authors

Michael Shapiro, U.S.Army Construction Engineering Research Laboratory Parser support: Bob Covill (Tekmap, Canada)

---

## Resources

- [Official i.group manual](https://grass.osgeo.org/grass-devel/manuals/i.group.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/i.group.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
