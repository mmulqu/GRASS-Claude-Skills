# t.vect.export

**Category**: temporal

## Description

Exports a space time vector dataset as GRASS specific archive file.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.t_vect_export(input,output,directory="/tmp",compression="bzip2",format="GML",where=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str, required`**
   - Name of the input space time vector dataset
   - Used as: input, stvds, name

2. **`output : str, required`**
   - Name of a space time vector dataset archive
   - Used as: output, file, name

3. **`directory : str, optional`**
   - Path to the work directory, default is /tmp
   - Used as: input, dir, name
   - Default: /tmp

4. **`compression : str, optional`**
   - Compression method of the tar archive
   - Allowed values: no, gzip, bzip2
   - Default: bzip2

5. **`format : str, optional`**
   - The export format of a single vector map
   - Supported are GML and GPKG via v.out.ogr and the GRASS package format of v.pack
   - Allowed values: GML, GPKG, pack

6. **`where : str, optional`**
   - WHERE conditions of SQL statement without 'where' keyword used in the temporal GIS framework
   - Example: start_time > '2001-01-01 12:30:00'
   - Used as: sql_query

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

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

t.vect.export exports a space time vector dataset (stvds) to a tar
archive as either GML (using v.out.ogr ) or GRASS pack
files. In addition to the pack or GML files, several metadata files are
also created in the archive that describe the temporal layout. All time
stamps are stored in the file "list.txt", for each map one row. The name
of the map, the start time and the end time are written. In case of a
time instance, the start time is equal to the end time. The "init.txt"
file stores the temporal type, the number of maps, the chosen export
format and some other metadata. The "proj.txt" file stores the
coordinate reference system information as a proj4 string of the project
the space time vector dataset was exported from. The file "readme.txt"
describes the file format. The output of v.info for each vector map in
the space time dataset is stored in "metadata.txt".

The tar archive can be compressed using the compress option. Gzip
and bzip2 (default) are available. A where option can be specified,
to export only a subset of the space time dataset. Archives exported
with t.vect.export can be imported with t.vect.import .

---

## See Also

Related tools:
- [`t.vect.import`](https://grass.osgeo.org/grass-devel/manuals/t.vect.import.html)
- [`t.create`](https://grass.osgeo.org/grass-devel/manuals/t.create.html)
- [`t.info`](https://grass.osgeo.org/grass-devel/manuals/t.info.html)
- [`v.out.ogr`](https://grass.osgeo.org/grass-devel/manuals/v.out.ogr.html)
- [`v.unpack`](https://grass.osgeo.org/grass-devel/manuals/v.unpack.html)
- [`t.rast.export`](https://grass.osgeo.org/grass-devel/manuals/t.rast.export.html)

---

## Resources

- [Official t.vect.export manual](https://grass.osgeo.org/grass-devel/manuals/t.vect.export.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/t.vect.export.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
