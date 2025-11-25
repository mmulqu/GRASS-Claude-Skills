# i.gensig

**Category**: imagery

## Description

Generates statistics for i.maxlik from raster map.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.i_gensig(trainingmap,group,subgroup,signaturefile,overwrite=None,verbose=None,quiet=None,superquiet=None)
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

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

i.gensig is a non-interactive method for generating input into i.maxlik . It can be used as the first pass in the GRASS
two-pass classification process (instead of i.cluster or g.gui.iclass ) . It reads a raster map layer,
called the training map, which has some of the pixels or regions already
classified. i.gensig will then extract spectral signatures from an
image based on the classification of the pixels in the training map and
make these signatures available to i.maxlik .

The user would then execute the GRASS program i.maxlik to actually create the final classified map.

This module generates signature files of type "sig". Use module i.signatures to manage generated signature files.

All raster maps used to generate signature file can have semantic label
set. Use r.support to set semantic labels of each
member of the imagery group. Signatures generated for one scene are
suitable for classification of other scenes as long as they consist of
same raster bands (semantic labels match).

Input trainingmap map must be prepared by the user in advance
using vector or raster
digitizer. Of course other methods could be devised by the user for
creating this training map - i.gensig makes no assumption about the
origin of this map layer. It simply creates signatures for the classes
defined in the training map for the image to be classified (the image is
specified in other options - see below). The wxGUI vector
digitizer can be used for interactively creating the
training map.

Input group is the name of the group that contains the band files which
comprise the image to be analyzed. The i.group command
is used to construct groups of raster layers which comprise an image.

Input subgroup names the subgroup within the group that selects a subset of the
bands to be analyzed. The i.group command is also used
to prepare this subgroup. The subgroup mechanism allows the user to
select a subset of all the band files that form an image.

Input signaturefile is the resultant signature file (containing the means and
covariance matrices) for each class in the training map that is
associated with the band files in the subgroup select.
Resultant signature file can be used with any other
imagery group as long as semantic labels match.

---

## See Also

Related tools:
- [`r.support`](https://grass.osgeo.org/grass-devel/manuals/r.support.html)
- [`g.gui.iclass`](https://grass.osgeo.org/grass-devel/manuals/g.gui.iclass.html)
- [`i.group`](https://grass.osgeo.org/grass-devel/manuals/i.group.html)
- [`i.cca`](https://grass.osgeo.org/grass-devel/manuals/i.cca.html)
- [`i.maxlik`](https://grass.osgeo.org/grass-devel/manuals/i.maxlik.html)
- [`i.smap`](https://grass.osgeo.org/grass-devel/manuals/i.smap.html)
- [`r.info`](https://grass.osgeo.org/grass-devel/manuals/r.info.html)
- [`r.univar`](https://grass.osgeo.org/grass-devel/manuals/r.univar.html)

---

## Authors

Michael Shapiro, U.S.Army Construction Engineering Research Laboratory Semantic label support: Maris Nartiss, University of Latvia

---

## Resources

- [Official i.gensig manual](https://grass.osgeo.org/grass-devel/manuals/i.gensig.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/i.gensig.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
