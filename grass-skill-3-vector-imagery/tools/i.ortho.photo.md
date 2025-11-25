# i.ortho.photo

**Category**: imagery

## Description

Menu driver for the photo imagery programs.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.i_ortho_photo(group,productname,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`group : str, required`**
   - Name of imagery group for ortho-rectification
   - Used as: input, group, name

2. **`productname : str, required`**
   - Name of Modules
   - Allowed values: i.group, i.ortho.target, i.ortho.elev, i.ortho.camera, g.gui.photo2image, i.ortho.init, g.gui.image2target, i.ortho.rectify
   - i.group: 1 - Select/Modify imagery group
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/i.ortho.photo.html#__tabbed_2_3) for all details)*

3. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

4. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

5. **`superquiet : bool, optional`**
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

i.ortho.photo is a menu to launch the different parts of the ortho
rectification process of aerial imagery. i.ortho.photo allows the user
to ortho-rectify imagery group files consisting of several scanned
aerial photographs (raster maps) of a common area. i.ortho.photo guides the user through 8 steps required to ortho-rectify the raster
maps in a single imagery group. Alternatively, all the steps can be
performed separately by running the appropriate modules.

The ortho-rectification procedure in GRASS places the image pixels
on the surface of the earth by matching the coordinate system of the
aerial image in pixels ( image coordinate system ) and the coordinate
system of the camera sensor in millimetres ( photo coordinate system )
for the interior orientation of the image, and further to the
georeferenced coordinate system defined by projection parameters
( target coordinate system ) for exterior orientation.

---

## See Also

Related tools:
- [`g.gui.image2target`](https://grass.osgeo.org/grass-devel/manuals/g.gui.image2target.html)
- [`g.gui.photo2image`](https://grass.osgeo.org/grass-devel/manuals/g.gui.photo2image.html)
- [`i.group`](https://grass.osgeo.org/grass-devel/manuals/i.group.html)
- [`i.ortho.camera`](https://grass.osgeo.org/grass-devel/manuals/i.ortho.camera.html)
- [`i.ortho.elev`](https://grass.osgeo.org/grass-devel/manuals/i.ortho.elev.html)
- [`i.ortho.init`](https://grass.osgeo.org/grass-devel/manuals/i.ortho.init.html)
- [`i.ortho.rectify`](https://grass.osgeo.org/grass-devel/manuals/i.ortho.rectify.html)
- [`i.ortho.target`](https://grass.osgeo.org/grass-devel/manuals/i.ortho.target.html)

---

## Authors

Mike Baba, DBA Systems, Inc. GRASS development team, 199?-2017

---

## Resources

- [Official i.ortho.photo manual](https://grass.osgeo.org/grass-devel/manuals/i.ortho.photo.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/i.ortho.photo.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
