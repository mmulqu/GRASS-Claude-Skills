# r.terraflow

**Category**: raster

## Description

Performs flow computation for massive grids.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_terraflow(elevation,filled=None,direction=None,swatershed=None,accumulation=None,tci=None,d8cut=None,memory=300,directory=None,stats=None,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`elevation : str | np.ndarray, required`**
   - Name of input elevation raster map
   - Used as: input, raster, name

2. **`filled : str | type(np.ndarray) | type(np.array) | type(gs.array.array), optional`**
   - Name for output filled (flooded) elevation raster map
   - Used as: output, raster, name

3. **`direction : str | type(np.ndarray) | type(np.array) | type(gs.array.array), optional`**
   - Name for output flow direction raster map
   - Used as: output, raster, name

4. **`swatershed : str | type(np.ndarray) | type(np.array) | type(gs.array.array), optional`**
   - Name for output sink-watershed raster map
   - Used as: output, raster, name

5. **`accumulation : str | type(np.ndarray) | type(np.array) | type(gs.array.array), optional`**
   - Name for output flow accumulation raster map
   - Used as: output, raster, name

6. **`tci : str | type(np.ndarray) | type(np.array) | type(gs.array.array), optional`**
   - Name for output topographic convergence index (tci) raster map
   - Used as: output, raster, name

7. **`d8cut : float, optional`**
   - Routing using SFD (D8) direction
   - If flow accumulation is larger than this value it is routed using SFD (D8) direction (meaningful only for MFD flow). If no answer is given it defaults to infinity.

8. **`memory : int, optional`**
   - Maximum memory to be used (in MB)
   - Cache size for raster rows
   - Used as: memory in MB

9. **`directory : str, optional`**
   - Directory to hold temporary files (they can be large)

10. **`stats : str, optional`**
   - Name for output file containing runtime statistics

11. **`flags : str, optional`**
   - Allowed values: s
   - s
   - SFD (D8) flow (default is MFD)

12. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

13. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

14. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

15. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 15 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/r.terraflow.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | np.ndarray | tuple[np.ndarray] | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned. If an array type (e.g., np.ndarray) is used for one of the raster outputs, the result will be an array and will have the shape corresponding to the computational region. If an array type is used for more than one raster output, the result will be a tuple of arrays.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

r.terraflow takes as input a raster digital elevation model (DEM) and
computes the flow direction raster and the flow accumulation raster, as
well as the flooded elevation raster, sink-watershed raster (partition
into watersheds around sinks) and TCI (topographic convergence index)
raster maps.

r.terraflow computes these rasters using well-known approaches, with
the difference that its emphasis is on the computational complexity of
the algorithms, rather than on modeling realistic flow. r.terraflow emerged from the necessity of having scalable software able to process
efficiently very large terrains. It is based on theoretically optimal
algorithms developed in the framework of I/O-efficient algorithms. r.terraflow was designed and optimized especially for massive grids
and is able to process terrains which were impractical with similar
functions existing in other GIS systems.

Flow directions are computed using either the MFD (Multiple Flow
Direction) model or the SFD (Single Flow Direction, or D8) model,
illustrated below. Both methods compute downslope flow directions by
inspecting the 3-by-3 window around the current cell. The SFD method
assigns a unique flow direction towards the steepest downslope neighbor.
The MFD method assigns multiple flow directions towards all downslope
neighbors.

Flow direction to the steepest downslope neighbor (SFD).

Flow direction to all downslope neighbors (MFD).

The SFD and the MFD method cannot compute flow directions for cells
which have the same height as all their neighbors (flat areas) or cells
which do not have downslope neighbors (one-cell pits).

In order to flood the terrain, r.terraflow identifies all sinks and
partitions the terrain into sink-watersheds (a sink-watershed contains
all the cells that flow into that sink), builds a graph representing the
adjacency information of the sink-watersheds, and uses this
sink-watershed graph to merge watersheds into each other along their
lowest common boundary until all watersheds have a flow path outside the
terrain. Flooding produces a sink-less terrain in which every cell has a
downslope flow path leading outside the terrain and therefore every cell
in the terrain can be assigned SFD/MFD flow directions as above. Flow
directions are encoded using powers of two clockwise starting from
2^0 for east to 2^7 for north-east.

Flow direction encoding clockwise starting from 2^0 for east
to 2^7 for north-east; 0 for undetermined (sinks) and 1 for
undefined (null cells)
( source )

Once flow directions are computed for every cell in the terrain, r.terraflow computes flow accumulation by routing water using the flow
directions and keeping track of how much water flows through each cell.

If flow accumulation of a cell is larger than the value given by the d8cut option, then the flow of this cell is routed to its neighbors
using the SFD (D8) model. This option affects only the flow accumulation
raster and is meaningful only for MFD flow (i.e. if the -s flag is
not used); If this option is used for SFD flow it is ignored. The
default value of d8cut is infinity .

r.terraflow also computes the tci raster (topographic convergence
index, defined as the logarithm of the ratio of flow accumulation and
local slope).

For more details on the algorithms see [1,2,3] below.

---

## See Also

Related tools:
- [`r.flow`](https://grass.osgeo.org/grass-devel/manuals/r.flow.html)
- [`r.basins.fill`](https://grass.osgeo.org/grass-devel/manuals/r.basins.fill.html)
- [`r.drain`](https://grass.osgeo.org/grass-devel/manuals/r.drain.html)
- [`r.topidx`](https://grass.osgeo.org/grass-devel/manuals/r.topidx.html)
- [`r.topmodel`](https://grass.osgeo.org/grass-devel/manuals/r.topmodel.html)
- [`r.water.outlet`](https://grass.osgeo.org/grass-devel/manuals/r.water.outlet.html)
- [`r.watershed`](https://grass.osgeo.org/grass-devel/manuals/r.watershed.html)

---

## Authors

Original version of program: The TerraFlow project, 1999, Duke
University.
Lars Arge , Jeff
Chase , Pat
Halpin , Laura
Toma , Dean
Urban , Jeff
Vitter , Rajiv Wickremesinghe.
Porting to GRASS GIS, 2002:
Lars Arge , Helena
Mitasova, Laura
Toma .
Contact: Laura Toma

---

## Resources

- [Official r.terraflow manual](https://grass.osgeo.org/grass-devel/manuals/r.terraflow.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.terraflow.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
