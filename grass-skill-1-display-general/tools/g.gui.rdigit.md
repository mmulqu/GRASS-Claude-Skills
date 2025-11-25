# g.gui.rdigit

**Category**: general

## Description

Interactive editing and digitizing of raster maps.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.g_gui_rdigit(create=None,base=None,type="CELL",edit=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`create : str | type(np.ndarray) | type(np.array) | type(gs.array.array), optional`**
   - Name of new raster map to create
   - Name for output raster map
   - Used as: output, raster, name

2. **`base : str | np.ndarray, optional`**
   - Name of base raster map
   - Used as: input, raster, name

3. **`type : str, optional`**
   - Type of raster map to be created
   - Storage type for resultant raster map
   - Allowed values: CELL, FCELL, DCELL
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/g.gui.rdigit.html#__tabbed_2_3) for all details)*

4. **`edit : str | np.ndarray, optional`**
   - Name of existing raster map to edit
   - Name of input raster map
   - Used as: input, raster, name

5. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

6. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

7. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

8. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None

### Returns

result : grass.tools.support.ToolResult | np.ndarray | tuple[np.ndarray] | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned. If an array type (e.g., np.ndarray) is used for one of the raster outputs, the result will be an array and will have the shape corresponding to the computational region. If an array type is used for more than one raster output, the result will be a tuple of arrays.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

Raster Digitizer is a simple tool to quickly draw lines, areas, and
circles and save these features in a raster map. It is accessible from
the Map Display toolbar (from the combo box on the right).

Raster Digitizer currently allows you to:

The typical workflow includes these steps:

---

## See Also

Related tools:
- [`r.in.poly`](https://grass.osgeo.org/grass-devel/manuals/r.in.poly.html)
- [`g.gui.vdigit`](https://grass.osgeo.org/grass-devel/manuals/g.gui.vdigit.html)

---

## Authors

Anna Petrasova, NCSU GeoForALL Laboratory Tomas Zigo (standalone module)

---

## Resources

- [Official g.gui.rdigit manual](https://grass.osgeo.org/grass-devel/manuals/g.gui.rdigit.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/g.gui.rdigit.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
