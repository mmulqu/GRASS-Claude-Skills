# i.fft

**Category**: imagery

## Description

Fast Fourier Transform (FFT) for image processing.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.i_fft(input,real,imaginary,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str | np.ndarray, required`**
   - Name of input raster map
   - Used as: input, raster, name

2. **`real : str | type(np.ndarray) | type(np.array) | type(gs.array.array), required`**
   - Name for output real part arrays stored as raster map
   - Used as: output, raster, name

3. **`imaginary : str | type(np.ndarray) | type(np.array) | type(gs.array.array), required`**
   - Name for output imaginary part arrays stored as raster map
   - Used as: output, raster, name

4. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

5. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

6. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

7. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None

### Returns

result : grass.tools.support.ToolResult | np.ndarray | tuple[np.ndarray] | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned. If an array type (e.g., np.ndarray) is used for one of the raster outputs, the result will be an array and will have the shape corresponding to the computational region. If an array type is used for more than one raster output, the result will be a tuple of arrays.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

i.fft is an image processing program based on the FFT algorithm given
by Frigo et al. (1998), that processes a single input raster map layer
( input ) and constructs the real and imaginary Fourier components in
frequency space.

---

## See Also

Related tools:
- [`i.cca`](https://grass.osgeo.org/grass-devel/manuals/i.cca.html)
- [`g.gui.iclass`](https://grass.osgeo.org/grass-devel/manuals/g.gui.iclass.html)
- [`i.ifft`](https://grass.osgeo.org/grass-devel/manuals/i.ifft.html)
- [`i.pca`](https://grass.osgeo.org/grass-devel/manuals/i.pca.html)

---

## Authors

David Satnik, GIS Laboratory, Central Washington University Glynn Clements (FFTW support)

---

## Resources

- [Official i.fft manual](https://grass.osgeo.org/grass-devel/manuals/i.fft.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/i.fft.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
