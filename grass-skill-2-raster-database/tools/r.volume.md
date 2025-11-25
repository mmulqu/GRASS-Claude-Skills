# r.volume

**Category**: raster

## Description

Calculates the volume of data "clumps". Optionally produces a GRASS vector points map containing the calculated centroids of these clumps.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_volume(input,clump=None,centroids=None,output=None,separator=None,format="plain",flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str | np.ndarray, required`**
   - Name of input raster map representing data that will be summed within clumps
   - Used as: input, raster, name

2. **`clump : str | np.ndarray, optional`**
   - Name of input clump raster map
   - Preferably the output of r.clump. If no clump map is given, raster mask is used instead.
   - Used as: input, raster, name

3. **`centroids : str, optional`**
   - Name for output vector points map to contain clump centroids
   - Used as: output, vector, name

4. **`output : str, optional`**
   - Name for output file to hold the report
   - If no output file given report is printed to standard output
   - Used as: output, file, name

5. **`separator : str, optional`**
   - Field separator
   - Special characters: pipe, comma, space, tab, newline
   - Used as: input, separator, character

6. **`format : str, required`**
   - Output format
   - Used as: name
   - Allowed values: plain, csv, json
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/r.volume.html#__tabbed_2_3) for all details)*

7. **`flags : str, optional`**
   - Allowed values: f, p
   - f
   - Generate unformatted report (items separated by colon) [deprecated]
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/r.volume.html#__tabbed_2_3) for all details)*

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


*Showing 10 of 11 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/r.volume.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

r.volume is a tool for summing cell values within clumps and
calculating volumes and centroids of patches or clumps.

r.volume generates a table containing the sum of all cells from a input raster map sorted by category on a clump raster map, and
optionally generates a vector points map of the centroids for each
clump. If a clump map is not specified, the current raster mask is used.
The raster mask can be defined by r.mask . The sum is
multiplied by the area of a cell to give the volume occupied by that
cell. See below for an example of the output table.

---

## See Also

Related tools:
- [`r.clump`](https://grass.osgeo.org/grass-devel/manuals/r.clump.html)
- [`r.mask`](https://grass.osgeo.org/grass-devel/manuals/r.mask.html)
- [`r.mapcalc`](https://grass.osgeo.org/grass-devel/manuals/r.mapcalc.html)

---

## Authors

Dr. James Hinthorne, Central Washington University GIS Laboratory,
December 1988. Updated to GRASS 7 by Martin Landa, Czech Technical University in
Prague, Czech Republic

---

## Resources

- [Official r.volume manual](https://grass.osgeo.org/grass-devel/manuals/r.volume.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.volume.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
