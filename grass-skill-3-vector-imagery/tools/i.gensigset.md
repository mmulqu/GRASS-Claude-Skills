# i.gensigset

**Category**: imagery

## Description

Generates statistics for i.smap from raster map.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.i_gensigset(trainingmap,group,subgroup,signaturefile,maxsig=5,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`trainingmap : str | np.ndarray, required`**
   - Ground truth training map
   - Used as: input, raster, name

2. **`group : str, required`**
   - Name of input imagery group
   - Used as: input, group, name

3. **`subgroup : str, required`**
   - Name of input imagery subgroup
   - Used as: input, subgroup, name

4. **`signaturefile : str, required`**
   - Name for output file containing result signatures
   - Used as: output, sigfile, name

5. **`maxsig : int, optional`**
   - Maximum number of sub-signatures in any class
   - Default: 5

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

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

i.gensigset is a non-interactive method for generating input into i.smap . It is used as the first pass in the a two-pass
classification process. It reads a raster map layer, called the training
map, which has some of the pixels or regions already classified. i.gensigset will then extract spectral signatures from an image based
on the classification of the pixels in the training map and make these
signatures available to i.smap .

The user would then execute the GRASS program i.smap to
create the final classified map.

This module generates signature files of type "sigset". Use module i.signatures to manage generated signature files.

For all raster maps used to generate signature file it is recommended to
have semantic label set. Use r.support to set semantic
labels of each member of the imagery group. Signatures generated for one
scene are suitable for classification of other scenes as long as they
consist of same raster bands (semantic labels match). If semantic labels
are not set, it will be possible to use obtained signature file to
classify only the same imagery group used for generating signatures.

An usage example can be found in i.smap documentation.

---

## See Also

Related tools:
- [`r.support`](https://grass.osgeo.org/grass-devel/manuals/r.support.html)
- [`i.group`](https://grass.osgeo.org/grass-devel/manuals/i.group.html)
- [`i.smap`](https://grass.osgeo.org/grass-devel/manuals/i.smap.html)
- [`r.info`](https://grass.osgeo.org/grass-devel/manuals/r.info.html)
- [`r.univar`](https://grass.osgeo.org/grass-devel/manuals/r.univar.html)

---

## Authors

Charles Bouman, School of Electrical Engineering, Purdue University Michael Shapiro, U.S.Army Construction Engineering Research Laboratory Semantic label support: Maris Nartiss, University of Latvia

---

## Resources

- [Official i.gensigset manual](https://grass.osgeo.org/grass-devel/manuals/i.gensigset.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/i.gensigset.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
