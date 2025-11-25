# r.patch

**Category**: raster

## Description

Creates a composite raster map layer by using known category values from one (or more) map layer(s) to fill in areas of "no data" in another map layer.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_patch(input,output,nprocs=0,memory=300,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str | list[str], required`**
   - Name of raster maps to be patched together
   - Used as: input, raster, name

2. **`output : str | type(np.ndarray) | type(np.array) | type(gs.array.array), required`**
   - Name for resultant raster map
   - Used as: output, raster, name

3. **`nprocs : int, optional`**
   - Number of threads for parallel computing
   - 0: use OpenMP default; >0: use nprocs; <0: use MAX-nprocs
   - Default: 0

4. **`memory : int, optional`**
   - Maximum memory to be used (in MB)
   - Cache size for raster rows
   - Used as: memory in MB

5. **`flags : str, optional`**
   - Allowed values: z, s
   - z
   - Use zero (0) for transparency instead of NULL
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/r.patch.html#__tabbed_2_3) for all details)*

6. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

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

result : grass.tools.support.ToolResult | np.ndarray | tuple[np.ndarray] | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned. If an array type (e.g., np.ndarray) is used for one of the raster outputs, the result will be an array and will have the shape corresponding to the computational region. If an array type is used for more than one raster output, the result will be a tuple of arrays.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

The GRASS program r.patch allows the user to build a new raster map
the size and resolution of the current region by assigning known data
values from input raster maps to the cells in this region. In case of overlapping input raster maps this is done by filling in "no
data" cells, those that do not yet contain data, contain NULL data, or,
optionally contain 0 data, with the data from the first input map. Once
this is done the remaining holes are filled in by the next input map,
and so on. In case of adjacent input raster maps the output map contains the map
mosaic.

Hence this command is useful for

The current geographic region definition and mask settings are
respected.

Figure: Result of patching of two raster maps containing NULLs using
the default settings.

The first name listed in the string input = name , name , name ,...
is the name of the first map whose data values will be used to fill in
cells in the current region. Then, the second through the last input
maps (..., name , name , ...) will be used, in order, to supply data
values for the remaining "no data" cells (or cells with value 0 with -z flag).

In other words, the first raster map is used first and if it had some
"no data" cells, then second raster map is used for these cells, then
the third and so on. So the formal command line syntax can be also
written as input = primary , secondary , tertiary ,... For two raster
maps, the first one can be viewed as the primary one or the default one
and the second one as the secondary one or a fallback.

Figure: Result of patching of two raster maps using the -z flag to
treat zeros as NULLs. Note the value 1 being preserved from the first
raster while the value 6 is taken from the second raster instead of the
value 0 from the first raster because zeros are replaced with the -z flag active.

The module is corresponds to the SQL COALESCE() function. This function
takes two or more arguments and returns a copy of its first non-NULL
argument. If all arguments are NULL, the function returns NULL.

The r.patch module iterates over all cells and for each cell of the
output raster map uses the first corresponding non-NULL cell in the
series of the input raster maps.

Below, the raster map layer on the far left is patched with the
middle ( patching ) raster map layer, to produce the composite raster
map layer on the right. The example assumes zero values to be treated as
NULLs ( -z flag).

Switching the patched and the patching raster map layers produces
the following results:

---

## See Also

Related tools:
- [`g.region`](https://grass.osgeo.org/grass-devel/manuals/g.region.html)
- [`g.remove`](https://grass.osgeo.org/grass-devel/manuals/g.remove.html)
- [`g.rename`](https://grass.osgeo.org/grass-devel/manuals/g.rename.html)
- [`r.mapcalc`](https://grass.osgeo.org/grass-devel/manuals/r.mapcalc.html)
- [`r.support`](https://grass.osgeo.org/grass-devel/manuals/r.support.html)
- [`r.series`](https://grass.osgeo.org/grass-devel/manuals/r.series.html)
- [`v.mkgrid`](https://grass.osgeo.org/grass-devel/manuals/v.mkgrid.html)

---

## Authors

Michael Shapiro, U.S. Army Construction Engineering Research
Laboratory Huidae Cho (-z flag and performance improvement) Aaron Saw Min Sern (OpenMP support).

---

## Resources

- [Official r.patch manual](https://grass.osgeo.org/grass-devel/manuals/r.patch.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.patch.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
