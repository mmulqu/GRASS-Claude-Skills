# i.ortho.init

**Category**: imagery

## Description

Interactively creates or modifies entries in a camera initial exposure station file for imagery group referenced by a sub-block.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.i_ortho_init(group,xc=None,yc=None,zc=None,xc_sd=None,yc_sd=None,zc_sd=None,omega=None,phi=None,kappa=None,omega_sd=None,phi_sd=None,kappa_sd=None,flags=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`group : str, required`**
   - Name of imagery group for ortho-rectification
   - Used as: input, group, name

2. **`xc : float, optional`**
   - Initial Camera Exposure X-coordinate

3. **`yc : float, optional`**
   - Initial Camera Exposure Y-coordinate

4. **`zc : float, optional`**
   - Initial Camera Exposure Z-coordinate

5. **`xc_sd : float, optional`**
   - Apriori X-coordinate standard deviation

6. **`yc_sd : float, optional`**
   - Apriori Y-coordinate standard deviation

7. **`zc_sd : float, optional`**
   - Apriori Z-coordinate standard deviation

8. **`omega : float, optional`**
   - Initial Camera Omega (pitch) degrees

9. **`phi : float, optional`**
   - Initial Camera Phi (roll) degrees

10. **`kappa : float, optional`**
   - Initial Camera Kappa (yaw) degrees

11. **`omega_sd : float, optional`**
   - Apriori Omega (pitch) standard deviation

12. **`phi_sd : float, optional`**
   - Apriori Phi (roll) standard deviation

13. **`kappa_sd : float, optional`**
   - Apriori Kappa (yaw) standard deviation

14. **`flags : str, optional`**
   - Allowed values: r, p
   - r
   - Use initial values at run time
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/i.ortho.init.html#__tabbed_2_3) for all details)*

15. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

16. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

17. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 17 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/i.ortho.init.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

Aerial photographs may be either vertical or oblique. Vertical
photographs can be truly vertical (nadir), or slightly tilted (less than
3 degree from the vertical). Usually aerial photos are tilted to some
degree. We refer to the term vertical photograph up to a tilt of 3
degree. Oblique aerial photographs are purposely taken with an angle between 3
and 90 degree from the nadir direction.

The use of i.ortho.init (menu 6) is only required when rectifying a
tilted or oblique aerial photo.

i.ortho.init creates or modifies entries in a camera initial exposure
station file for imagery group referenced by a sub-block. These entries
include: the (XC,YC,ZC) standard (e.g. UTM) approximate coordinates of
the camera exposure station; initial roll, pitch, and yaw angles (in
degrees) of the cameras attitude; and the a priori standard deviations
for these parameters. During the imagery program, i.ortho.rectify , the
initial camera exposure station file is used for computation of the
ortho-rectification parameters. If no initial camera exposure station
file exist, the default values are computed from the control points file
created in g.gui.image2target .

The following menu is displayed:

The INITIAL values for (XC,YC,ZC) are expressed in standard (e.g. UTM)
coordinates, and represent an approximation for the location of the
camera at the time of exposure.

The INITIAL values for (omega,phi,kappa) are expressed in degrees, and
represent an approximation for the cameras attitude at the time of
exposure.

If ground control points are available, the INITIAL values are
iteratively corrected. This is particularl useful when the INITIAL
values are rather rough estimates.

The standard deviations for (XC,YC,ZC) are expressed in meters, and are
used as a priori values for the standard deviations used in
computation of the ortho rectification parameters. Higher values improve
the refinement of the initial camera exposure. As a rule of thumb, 5% of
the estimated target extents should be used.

The standard deviations for (omega,phi,kappa) are expressed in degrees,
and are used as a priori values for the standard deviations used in
computation of the ortho rectification parameters. As a rule of thumb, 2
degrees should be used.

If Use these values at run time? (1=yes, 0=no) is set to 0, the values
in this menu are not used.

---

## See Also

Related tools:
- [`i.ortho.photo`](https://grass.osgeo.org/grass-devel/manuals/i.ortho.photo.html)
- [`g.gui.photo2image`](https://grass.osgeo.org/grass-devel/manuals/g.gui.photo2image.html)
- [`g.gui.image2target`](https://grass.osgeo.org/grass-devel/manuals/g.gui.image2target.html)
- [`i.ortho.elev`](https://grass.osgeo.org/grass-devel/manuals/i.ortho.elev.html)
- [`i.ortho.camera`](https://grass.osgeo.org/grass-devel/manuals/i.ortho.camera.html)
- [`i.ortho.transform`](https://grass.osgeo.org/grass-devel/manuals/i.ortho.transform.html)
- [`i.ortho.rectify`](https://grass.osgeo.org/grass-devel/manuals/i.ortho.rectify.html)

---

## Resources

- [Official i.ortho.init manual](https://grass.osgeo.org/grass-devel/manuals/i.ortho.init.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/i.ortho.init.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
