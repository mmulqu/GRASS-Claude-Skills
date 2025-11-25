# i.ortho.camera

**Category**: imagery

## Description

Select and modify the imagery group camera reference file.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.i_ortho_camera(group=None,camera,name=None,id=None,clf=None,pp=None,fid=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`group : str, optional`**
   - Name of imagery group for ortho-rectification
   - Used as: input, group, name

2. **`camera : str, required`**
   - Name of camera reference file
   - Name of input file
   - Used as: input, file, name

3. **`name : str, optional`**
   - Camera name

4. **`id : str, optional`**
   - Camera id

5. **`clf : float, optional`**
   - Calibrated focal length

6. **`pp : tuple[float, float] | list[float] | str, optional`**
   - Principal point coordinates
   - Coordinates
   - Used as: input, coords, east,north

7. **`fid : list[tuple[float, float]] | tuple[float, float] | list[float] | str, optional`**
   - Fiducial coordinates
   - Coordinates
   - Used as: input, coords, east,north

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

i.ortho.camera creates or modifies entries in a camera reference file.
For ortho-photo rectification, a camera reference file is required for
computation of scanned image to photo-coordinate transformation
parameters. There are two coordinate systems: The image coordinate
system (in pixels) and the photo coordinate system (in milli-meters).
The inner orientation establishes a relation between the pixels and the
image coordinates with help of fiducial marks.

The first prompt in the program will ask you for the name of the camera
reference file to be created or modified. You may create a new camera
reference file by entering a new name, or modify an existing camera
reference file by entering the name of an existing camera file.

After entering the camera file name, following menu is displayed:

Please provide the following information

The camera name and identification describe the camera reference file.
The calibrated focal length and the point of symmetry are used in
computing the photo-to-target transformation parameters. These values
should be entered from the camera calibration report (usually available
from the photograph supplier).

This example is the camera Zeiss LMK9 265-002A belonging to the
Hellenic Military Geographical Survey (HMGS) and calibrated in December
1985

The photo coordinate system origin is the so-called calibrated principal
point (PP, Principal Point of Symmetry) which is in the center of the
image. The origin of the axes is at the intersection of the radii traced
from the fiducial marks. In the ideal case of no deviations in the
camera (see camera calibration certificate) the center is the origin and
the values are 0 for both X and Y of Point of Symmetry. But usually the
principal point does not fall on the intersection of the radii at the
center of the picture. This eccentricity is usually of the order of a
few micrometers.

You are then asked to enter the X and Y photo coordinates of each
fiducial as follows. These fiducials (or reseau) marks are index marks
imaged on film which serve as reference photo coordinate system. The
maximum number of fiducials will determine the number of fiducial or
reseau coordinate pairs to be entered below. The origin is the center of
the image (or the point of symmetry) and X and Y are left-right and
up-down. The order is up to the user, but must be kept consistent
throughout the rectification process.

On this screen you should enter the fiducial or reseau photo-coordinates
as given in the camera calibration report. The X, and Y coordinates are
in milli-meters from the principle point.

Please provide the following information

The input display is repeated until the number of MAXIMUM FIDUCIALS is
reached.

---

## See Also

Related tools:
- [`i.ortho.photo`](https://grass.osgeo.org/grass-devel/manuals/i.ortho.photo.html)
- [`g.gui.photo2image`](https://grass.osgeo.org/grass-devel/manuals/g.gui.photo2image.html)
- [`g.gui.image2target`](https://grass.osgeo.org/grass-devel/manuals/g.gui.image2target.html)
- [`i.ortho.init`](https://grass.osgeo.org/grass-devel/manuals/i.ortho.init.html)

---

## Resources

- [Official i.ortho.camera manual](https://grass.osgeo.org/grass-devel/manuals/i.ortho.camera.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/i.ortho.camera.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
