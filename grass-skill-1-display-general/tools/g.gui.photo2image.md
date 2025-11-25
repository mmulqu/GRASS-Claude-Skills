# g.gui.photo2image

**Category**: general

## Description

Corrects scanning distortions of a paper photo.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.g_gui_photo2image(group,raster,camera,order="1",extension="_ip2i_out",verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`group : str, required`**
   - Name of input imagery group
   - Used as: input, group, name

2. **`raster : str | np.ndarray, required`**
   - Name of input raster map
   - Used as: input, raster, name

3. **`camera : str, required`**
   - The name of the camera (generated in i.ortho.camera)
   - The name of the camera (generated in i.ortho.camera)

4. **`order : str, required`**
   - The rectification order (no of Fiducial=4 -> order=1, no of Fiducial=8 -> order=2)
   - The rectification order (no of Fiducial=4 -> order=1, no of Fiducial=8 -> order=2)
   - Default: 1

5. **`extension : str, required`**
   - The name of the output files extension (used in i.rectify)
   - The name of the output files extension (used in i.rectify)
   - Default: _ip2i_out

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

This module is based on g.gui.gcp , the GCP manager of GRASS. It
is part of i.ortho.photo suite.

The aim of this module is to give absolute location values to the
fiducial points present (in number of 4 or 8) in a scanned aerial
photo.

This is necessary as (manual) scanning introduces distortions, rotations
and also may not be limited to scan the boundary of the photo itself. It
is thus necessary to give to each fiducial the exact coordinates in mm
as given by the aerial photographic instrument design, which is unique
per camera.

This module requires you to have made a group with your aerial photo (i.group) , a camera description file (i.ortho.target) and use
them to launch the module. Additional requirements are the order of
rectification (1 if no of Fiducials is 4, 2 if no of Fiducials is 8) and
an extension file (if not given, defaults to \filename_ip2i_out)

An example for project imagery60 :

Figure: Screenshot of g.gui.photo2image

---

## See Also

Related tools:

---

## Authors

Markus Metz
Based on the Georectifier (GRASS 6.4.0) by Michael Barton Martin Landa, Czech Technical University in Prague, Czech Republic

---

## Resources

- [Official g.gui.photo2image manual](https://grass.osgeo.org/grass-devel/manuals/g.gui.photo2image.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/g.gui.photo2image.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
