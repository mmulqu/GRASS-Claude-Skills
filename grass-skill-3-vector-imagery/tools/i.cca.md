# i.cca

**Category**: imagery

## Description

Canonical components analysis (CCA) program for image processing.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.i_cca(group,subgroup,signature,output,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`group : str, required`**
   - Name of input imagery group
   - Used as: input, group, name

2. **`subgroup : str, required`**
   - Name of input imagery subgroup
   - Used as: input, subgroup, name

3. **`signature : str, required`**
   - File containing spectral signatures
   - Used as: input, sigfile, name

4. **`output : str | type(np.ndarray) | type(np.array) | type(gs.array.array), required`**
   - Output raster map prefix name
   - Used as: output, raster, name

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

i.cca is an image processing program that takes any number of
(raster) band files and a signature file, and outputs the same number of
raster band files transformed to provide maximum separability of the
categories indicated by the signatures. This implementation of the
canonical components transformation is based on the algorithm contained
in the LAS image processing
system . CCA is also
known as "Canonical components transformation".

Typically the user will use the g.gui.iclass program to collect a set of signatures and then pass those signatures
along with the raster band files to i.cca . The raster band file names
are specified on the command line by giving the group and subgroup that
were used to collect the signatures.

The output raster map names are built by appending a ".1", ".2", etc. to
the output raster map name specified on the command line.

group = name Name of the imagery group to which the raster band files
used belong.

subgroup = name Name of the imagery subgroup to which the raster band
files used belong.

signature = name Name of an ASCII file containing spectral signatures.

output = name Output raster map prefix name. The output raster map layer names are
built by appending a ".1", ".2", etc. onto the output name specified
by the user.

---

## See Also

Related tools:
- [`g.gui.iclass`](https://grass.osgeo.org/grass-devel/manuals/g.gui.iclass.html)
- [`i.gensig`](https://grass.osgeo.org/grass-devel/manuals/i.gensig.html)
- [`i.cluster`](https://grass.osgeo.org/grass-devel/manuals/i.cluster.html)
- [`i.pca`](https://grass.osgeo.org/grass-devel/manuals/i.pca.html)
- [`r.covar`](https://grass.osgeo.org/grass-devel/manuals/r.covar.html)
- [`r.mapcalc`](https://grass.osgeo.org/grass-devel/manuals/r.mapcalc.html)

---

## Authors

David Satnik, GIS Laboratory, Central Washington University Ali R. Vali, University of Texas Semantic label support: Maris Nartiss, University of Latvia

---

## Resources

- [Official i.cca manual](https://grass.osgeo.org/grass-devel/manuals/i.cca.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/i.cca.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
