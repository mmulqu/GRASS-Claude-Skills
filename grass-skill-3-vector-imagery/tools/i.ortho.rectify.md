# i.ortho.rectify

**Category**: imagery

## Description

Orthorectifies an image by using the image to photo coordinate transformation matrix.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.i_ortho_rectify(group,input=None,extension,resolution=None,memory=300,method="nearest",angle=None,flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`group : str, required`**
   - Name of input imagery group
   - Used as: input, group, name

2. **`input : str | list[str], optional`**
   - Name of input raster map(s)
   - Used as: input, raster, name

3. **`extension : str, required`**
   - Output raster map(s) suffix

4. **`resolution : float, optional`**
   - Target resolution (ignored if -c flag used)

5. **`memory : int, optional`**
   - Maximum memory to be used (in MB)
   - Cache size for raster rows
   - Used as: memory in MB

6. **`method : str, optional`**
   - Interpolation method to use
   - Allowed values: nearest, linear, cubic, lanczos, linear_f, cubic_f, lanczos_f
   - Default: nearest

7. **`angle : str | type(np.ndarray) | type(np.array) | type(gs.array.array), optional`**
   - Raster map with camera angle relative to ground surface
   - Used as: output, raster, name

8. **`flags : str, optional`**
   - Allowed values: c, a, p
   - c
   - Use current region settings in target project (location) (def.=calculate smallest area)
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/i.ortho.rectify.html#__tabbed_2_3) for all details)*

9. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

10. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

11. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

12. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 12 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/i.ortho.rectify.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | np.ndarray | tuple[np.ndarray] | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned. If an array type (e.g., np.ndarray) is used for one of the raster outputs, the result will be an array and will have the shape corresponding to the computational region. If an array type is used for more than one raster output, the result will be a tuple of arrays.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

i.ortho.rectify rectifies an image by using the image to photo
coordinate transformation matrix created by g.gui.photo2image and the rectification
parameters created by g.gui.image2target .
Rectification is the process by which the geometry of an image is made
planimetric. This is accomplished by mapping an image from one
coordinate system to another. In i.ortho.rectify the parameters
computed by g.gui.photo2image and g.gui.image2target are used in equations to
convert x,y image coordinates to standard map coordinates for each pixel
in the image. The result is an image with a standard map coordinate
system, compensated for relief distortions and photographic tilt. Upon
completion of the program the rectified image is deposited in a
previously targeted GRASS project (location).

Images can be resampled with various different interpolation methods:
nearest neighbor assignment, bilinear and bicubic interpolation. The
bilinear and bicubic interpolation methods are also available with a
fallback option. These methods "fall back" to simpler interpolation
methods along NULL borders. That is, from bicubic to bilinear to
nearest.

The process may take an hour or more depending on the size of the image,
the speed of the computer, the number files, and the size and resolution
of the selected window.

The rectified image will be located in the target project when the
program is completed. The original unrectified files are not modified or
removed.

The optional angle output holds the camera angle in degrees to the
local surface, considering local slope and aspect. A value of 90 degrees
indicates that the camera angle was orthogonal to the local surface, a
value of 0 degrees indicates that the camera angle was parallel to the
local surface and negative values indicate that the surface was
invisible to the camera. As a rule of thumb, values below 30 degrees
indicate problem areas where the orthorectified output will appear
blurred. Because terrain shadowing effects are not considered, areas
with high camera angles may also appear blurred if they are located
(viewed from the camera position) behind mountain ridges or peaks.

i.ortho.rectify can be run directly, specifying options in the command
line or the GUI, or it can be invoked as OPTION 8 through i.ortho.photo . If invoked though i.ortho.photo , an interactive terminal is used to
determine the options.

You are first asked if all images within the imagery group should be
rectified. If this option is not chosen, you are asked to specify for
each image within the imagery group whether it should be rectified or
not.

More than one file may be rectified at a time. Each file should have a
unique output file name. The next prompt asks you for an extension to be
appended to the rectified images.

The next prompt will ask you whether a camera angle map should be
produced and if yes, what should be its name.

After that you are asked if overwriting existing maps in the target
project and mapset should be allowed.

The next prompt asks you to select one of two windows:

If you choose option 2, you can also specify a desired target
resolution.

i.ortho.rectify will only rectify that portion of the image that
occurs within the chosen window. Only that portion will be relocated in
the target database. It is therefore important to check the current
window in the target project if choice number one is selected.

Next you are asked to select an interpolation method.

The last prompt will ask you about the amount of memory to be used by i.ortho.rectify .

---

## See Also

Related tools:
- [`i.ortho.photo`](https://grass.osgeo.org/grass-devel/manuals/i.ortho.photo.html)
- [`i.ortho.camera`](https://grass.osgeo.org/grass-devel/manuals/i.ortho.camera.html)
- [`g.gui.photo2image`](https://grass.osgeo.org/grass-devel/manuals/g.gui.photo2image.html)
- [`g.gui.image2target`](https://grass.osgeo.org/grass-devel/manuals/g.gui.image2target.html)
- [`i.ortho.init`](https://grass.osgeo.org/grass-devel/manuals/i.ortho.init.html)
- [`i.rectify`](https://grass.osgeo.org/grass-devel/manuals/i.rectify.html)

---

## Authors

Mike Baba, DBA Systems, Inc. Updated rectification and elevation map to FP 1/2002 Markus Neteler Bugfixes and enhancements 12/2010 Markus Metz

---

## Resources

- [Official i.ortho.rectify manual](https://grass.osgeo.org/grass-devel/manuals/i.ortho.rectify.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/i.ortho.rectify.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
