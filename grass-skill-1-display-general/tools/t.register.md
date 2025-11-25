# t.register

**Category**: temporal

## Description

Assigns timestamps and registers raster, vector and raster3d maps in a space time dataset.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.t_register(input=None,maps=None,type="raster",file=None,start=None,end=None,unit=None,increment=None,separator="pipe",flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str, optional`**
   - Name of the input space time dataset
   - Used as: input, stds, name

2. **`maps : str | list[str], optional`**
   - Name of the input maps
   - Used as: input, map, name

3. **`type : str, optional`**
   - Type of the input map
   - Used as: name
   - Allowed values: raster, vector, raster_3d

4. **`file : str | io.StringIO, optional`**
   - Input file with map names, one per line
   - Additionally the start time and the end time can be specified per line
   - Used as: input, file, name

5. **`start : str, optional`**
   - Valid start date and time of the first map
   - Format for absolute time: "yyyy-mm-dd HH:MM:SS +HHMM", relative time is of type integer.

6. **`end : str, optional`**
   - Valid end date and time of all map
   - Format for absolute time: "yyyy-mm-dd HH:MM:SS +HHMM", relative time is of type integer.

7. **`unit : str, optional`**
   - Time stamp unit
   - Unit must be set in case of relative timestamps
   - Allowed values: years, months, days, hours, minutes, seconds

8. **`increment : str, optional`**
   - Time increment, works only in conjunction with start option
   - Time increment between maps for creation of valid time intervals (format for absolute time: NNN seconds, minutes, hours, days, weeks, months, years; format for relative time is of type integer: 5)

9. **`separator : str, optional`**
   - Field separator character of the input file
   - Special characters: pipe, comma, space, tab, newline
   - Used as: input, separator, character

10. **`flags : str, optional`**
   - Allowed values: i
   - i
   - Create an interval (start and end time) in case an increment and the start time are provided

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


*Showing 10 of 14 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/t.register.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

The module t.register has double functionality: it either only assigns
timestamps to raster, 3D raster and vector maps in the temporal database
(if input option is not provided, see below) or additionally, it also
registers them within input space time datasets (stds). The existing
timestamp modules r.timestamp , r3.timestamp and v.timestamp do not
register the maps in the temporal database of GRASS. However,
timestamps that have been created with these modules can be read and
used by t.register . This works only for maps that are not already
registered in the temporal database.

If the input option is not used (i.e., no stds is provided), maps will
be only registered in the temporal database with assigned timestamps.
If, on the other hand, the input option is used and a stds is
provided, maps will be first registered in the temporal database (if not
registered before) and then, in the stds specified. If the user wants to
register maps that are already registered in the temporal database in a
different stds, there is no need to pass information regarding start and
end time, t.register will read timestamps from the temporal database
(i.e., in this case only passing map names will be enough).

Maps can be specified both with their fully qualified map name, meaning
e.g. map@mapset and without the mapset name included. If the mapset
name is not provided in the input, t.register will look for the given
map on the current search path and assign the matching mapset. If the
map is not found on the current search path the module will fail. Thus,
registering maps with fully qualified map name is slightly faster.

The module t.register supports absolute and relative time. The
absolute temporal type refers to a fixed date while the relative
temporal type refers to data without fixed timestamps (e.g., sequential
maps used to calculate multi-decadal averages).

Maps can be registered by command line argument (i.e., a list of comma
separated map names) or using an input file. The start time, end time
and a temporal increment can be provided through command line or in the
input file. End time and increment are mutually exclusive. The user can
register single maps or a list of maps at once. Maps can be registered
in several space time datasets using the same timestamp. For the case of
vector time series, the user can also register a single vector map
connected to different layers representing time steps using the map:layer notation (See example below).

The increment option and the -i flag (to create time intervals)
work only in conjunction with the start option. If an input file
with timestamps (either start time or start time and end time) is used,
then the increment option and the -i flag are not supported.

Start time and end time with absolute time must be provided using the
format yyyy-mm-dd HH:MM:SS +HHMM . It is also supported to specify
only the date yyyy-mm-dd . In case of relative time, the temporal
unit (years, months, days, hours, minutes or seconds) must be provided.
In this case, the relative start time, end time and increment are
integers.

---

## See Also

Related tools:
- [`r.timestamp`](https://grass.osgeo.org/grass-devel/manuals/r.timestamp.html)
- [`t.create`](https://grass.osgeo.org/grass-devel/manuals/t.create.html)
- [`t.info`](https://grass.osgeo.org/grass-devel/manuals/t.info.html)

---

## Resources

- [Official t.register manual](https://grass.osgeo.org/grass-devel/manuals/t.register.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/t.register.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
