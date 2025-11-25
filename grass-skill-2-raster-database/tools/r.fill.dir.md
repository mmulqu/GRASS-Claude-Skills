# r.fill.dir

**Category**: raster

## Description

Filters and generates a depressionless elevation map and a flow direction map from a given elevation raster map.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_fill_dir(input,output,direction,areas=None,format="grass",flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str | np.ndarray, required`**
   - Name of input elevation raster map
   - Used as: input, raster, name

2. **`output : str | type(np.ndarray) | type(np.array) | type(gs.array.array), required`**
   - Name for output depressionless elevation raster map
   - Used as: output, raster, name

3. **`direction : str | type(np.ndarray) | type(np.array) | type(gs.array.array), required`**
   - Name for output flow direction map for depressionless elevation raster map
   - Used as: output, raster, name

4. **`areas : str | type(np.ndarray) | type(np.array) | type(gs.array.array), optional`**
   - Name for output raster map of problem areas
   - Used as: output, raster, name

5. **`format : str, optional`**
   - Aspect direction format
   - Allowed values: agnps, answers, grass
   - Default: grass

6. **`flags : str, optional`**
   - Allowed values: f
   - f
   - Find unresolved areas only

7. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

8. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

9. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

10. **`superquiet : bool, optional`**
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

r.fill.dir filters and generates a depressionless elevation map and a
flow direction map from a given raster elevation map. The method adopted
to filter the elevation map and rectify it is based on the paper titled
"Extracting topographic structure from digital elevation model data for
geographic information system analysis" by S.K. Jenson and J.O. Domingue
(1988).

The procedure takes an elevation layer as input and initially fills all
the depressions with one pass across the layer. Next, the flow direction
algorithm tries to find a unique direction for each cell. If the
watershed program detects areas with pothholes, it delineates this area
from the rest of the area and once again the depressions are filled
using the neighborhood technique used by the flow direction routine. The
final output will be a depressionless elevation layer and a unique flow
direction layer.

This (D8) flow algorithm performs as follows: At each raster cell the
code determines the slope to each of the 8 surrounding cells and assigns
the flow direction to the highest slope out of the cell. If there is
more than one equal, non-zero slope then the code picks one direction
based on preferences that are hard-coded into the program. If the
highest slope is flat and in more than one direction then the code first
tries to select an alternative based on flow directions in the adjacent
cells. r.fill.dir iterates that process, effectively propagating flow
directions from areas where the directions are known into the area where
the flow direction cannot otherwise be resolved.

The format parameter is the type of format at which the user wishes
to create the flow direction map. The flow direction map can be
encoded in GRASS aspect format, ANSWERS (Beasley et.al, 1982), or
AGNPS (Young et.al, 1985) format, so that it can be readily used as
input to other GRASS modules or the aforementioned hydrological
models. The grass format gives the same category values as r.slope.aspect gives for aspect, i.e. angles in
degrees counter-clockwise from east in 45 degree increments. The agnps format gives category values from 1-8, with 1 facing north and
increasing values in the clockwise direction. The answers format gives
category values from 0-360 degrees, with 0 (represented as 360) facing
east and values increasing in the counter-clockwise direction at 45
degree increments. In all cases, NULL (no data) values are used for
cells where direction cannot be determined.

In case of local problems, those unfilled areas can be stored
optionally. Each unfilled area in this maps is numbered. The -f flag
instructs the program to fill single-cell pits but otherwise to just
find the undrained areas and exit. With the -f flag set the program
writes an elevation map with just single-cell pits filled, a direction
map with unresolved problems and a map of the undrained areas that were
found but not filled. This option was included because filling DEMs was
often not the best way to solve a drainage problem. These options let
the user get a partially-fixed elevation map, identify the remaining
problems and fix the problems appropriately.

In some cases it may be necessary to run r.fill.dir repeatedly (using
output from one run as input to the next run) before all of problem
areas are filled.

The resulting depressionless elevation raster map can further be
processed to derive slopes and other attributes required by other
hydrological models.

As any GRASS module, r.fill.dir respects the computational region
settings. Thus, the module can be used to generate a flow direction map
for any sub-area within the full raster map layer. Also, r.fill.dir will take into account an active raster mask.

---

## See Also

Related tools:
- [`d.rast.arrow`](https://grass.osgeo.org/grass-devel/manuals/d.rast.arrow.html)
- [`d.shade`](https://grass.osgeo.org/grass-devel/manuals/d.shade.html)
- [`g.region`](https://grass.osgeo.org/grass-devel/manuals/g.region.html)
- [`r.fillnulls`](https://grass.osgeo.org/grass-devel/manuals/r.fillnulls.html)
- [`r.relief`](https://grass.osgeo.org/grass-devel/manuals/r.relief.html)
- [`r.slope.aspect`](https://grass.osgeo.org/grass-devel/manuals/r.slope.aspect.html)

---

## Authors

Fortran version: Raghavan Srinivasan, Agricultural Engineering
Department, Purdue University Rewrite to C with enhancements: Roger S. Miller

---

## Resources

- [Official r.fill.dir manual](https://grass.osgeo.org/grass-devel/manuals/r.fill.dir.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.fill.dir.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
