# r.topmodel

**Category**: raster

## Description

Simulates TOPMODEL which is a physically based hydrologic model.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_topmodel(parameters,topidxstats,input,output,timestep=None,topidxclass=None,topidx=None,ntopidxclasses=30,outtopidxstats=None,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`parameters : str | io.StringIO, required`**
   - Name of input TOPMODEL parameters file
   - Used as: input, file, name

2. **`topidxstats : str | io.StringIO, required`**
   - Name of input topographic index statistics file
   - Used as: input, file, name

3. **`input : str | io.StringIO, required`**
   - Name of input rainfall and potential evapotranspiration data file
   - Used as: input, file, name

4. **`output : str, required`**
   - Name for output file
   - Used as: output, file, name

5. **`timestep : int, optional`**
   - Time step
   - Generate output for this time step

6. **`topidxclass : int, optional`**
   - Topographic index class
   - Generate output for this topographic index class

7. **`topidx : str | np.ndarray, optional`**
   - Name of input topographic index raster map
   - Must be clipped to the catchment boundary. Used for generating outtopidxstats
   - Used as: input, raster, name

8. **`ntopidxclasses : int, optional`**
   - Number of topographic index classes
   - Used for generating outtopidxstats
   - Default: 30

9. **`outtopidxstats : str, optional`**
   - Name for output topographic index statistics file
   - Requires topidx and ntopidxclasses
   - Used as: output, file, name

10. **`flags : str, optional`**
   - Allowed values: p
   - p
   - Preprocess only and stop after generating outtopidxstats

11. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

12. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

13. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

14. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 14 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/r.topmodel.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

r.topmodel simulates TOPMODEL which is a physically based hydrologic
model.

parameters This file contains TOPMODEL parameters that describe the study area. Any
lines starting with a # sign or empty lines are ignored.

input This file contains observed weather data.

timestep If a time step is specified, output will be generated for the specific
time step in addition to the summary and total flows at the outlet. This
parameter can be combined with topidxclass to specify a time step
and topographic index class at the same time. If no topidxclass is
given, output will be generated for all the topographic index classes.

toptopidxclass If a topographic index class is specified, output will be generated for
the given topographic index class. This parameter can be combined with timestep . If no timestep is given, output will be generated for
all the time steps.

topidx , ntoptopidxclasses , outtoptopidxstats The topidx map can optionally be used for creating a new topographic
index statistics file. This map has to be already clipped to the
catchment boundary. The entire range of topographic index values will be
divided into ntoptopidxclasses and the area ratio of each class will
be reported in the outtoptopidxstats file. These three parameters
can be omitted unless a new topidxstats file needs to be created.

---

## See Also

Related tools:
- [`r.fill.dir`](https://grass.osgeo.org/grass-devel/manuals/r.fill.dir.html)
- [`r.mapcalc`](https://grass.osgeo.org/grass-devel/manuals/r.mapcalc.html)
- [`r.topidx`](https://grass.osgeo.org/grass-devel/manuals/r.topidx.html)

---

## Authors

Huidae Cho , Hydro Laboratory, Kyungpook
National University, South Korea
Based on TMOD9502.FOR by Keith Beven.

---

## Resources

- [Official r.topmodel manual](https://grass.osgeo.org/grass-devel/manuals/r.topmodel.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.topmodel.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
