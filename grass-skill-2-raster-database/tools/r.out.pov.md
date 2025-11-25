# r.out.pov

**Category**: raster

## Description

Converts a raster map layer into a height-field file for POV-Ray.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_out_pov(input,output,hftype=None,bias=None,scale=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str | np.ndarray, required`**
   - Name of input raster map
   - Used as: input, raster, name

2. **`output : str, required`**
   - Name of output povray file (TGA height field file)
   - Used as: output, file, name

3. **`hftype : int, optional`**
   - Height-field type (0=actual heights 1=normalized)

4. **`bias : float, optional`**
   - Elevation bias

5. **`scale : float, optional`**
   - Vertical scaling factor

6. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

7. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

8. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

9. **`superquiet : bool, optional`**
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

r.out.pov converts a user-specified raster map layer (map==name) into
a height-field file for POVray (tga==name). The hftype==value option
(where value is either 0 or 1) specifies the height-field type. When the
user enters 0 the output will be actual heights. If entered 1 the
cell-values will be normalized. If hftype is 0 (actual heights) the
bias==value can be used to add or subtract a value from heights. Use
scale==value to scale your heights by value. The GRASS program r.out.pov
can be used to create height- field files for Persistence of Vision
(POV) raytracer. POV can use a height-field defined in Targa (.TGA)
image file format where the RGB pixel values are 24 bits (3 bytes). A 16
bit unsigned integer height-field value is assigned as follows: RED =
high byte, GREEN = low byte, BLUE = empty.

---

## Resources

- [Official r.out.pov manual](https://grass.osgeo.org/grass-devel/manuals/r.out.pov.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.out.pov.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
