# i.atcorr

**Category**: imagery

## Description

Performs atmospheric correction using the 6S algorithm. 6S - Second Simulation of Satellite Signal in the Solar Spectrum.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.i_atcorr(input,range="0,255",elevation=None,visibility=None,parameters,output,rescale="0,255",flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`input : str | np.ndarray, required`**
   - Name of input raster map
   - Used as: input, raster, name

2. **`range : tuple[int, int] | list[int] | str, optional`**
   - Input range
   - Used as: min,max
   - Default: 0,255

3. **`elevation : str | np.ndarray, optional`**
   - Name of input elevation raster map (in m)
   - Used as: input, raster, name

4. **`visibility : str | np.ndarray, optional`**
   - Name of input visibility raster map (in km)
   - Used as: input, raster, name

5. **`parameters : str | io.StringIO, required`**
   - Name of input text file with 6S parameters
   - Used as: input, file, name

6. **`output : str | type(np.ndarray) | type(np.array) | type(gs.array.array), required`**
   - Name for output raster map
   - Used as: output, raster, name

7. **`rescale : tuple[int, int] | list[int] | str, optional`**
   - Rescale output raster map
   - Used as: min,max
   - Default: 0,255

8. **`flags : str, optional`**
   - Allowed values: i, r, a, b
   - i
   - Output raster map as integer
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/i.atcorr.html#__tabbed_2_3) for all details)*

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


*Showing 10 of 12 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/i.atcorr.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | np.ndarray | tuple[np.ndarray] | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned. If an array type (e.g., np.ndarray) is used for one of the raster outputs, the result will be an array and will have the shape corresponding to the computational region. If an array type is used for more than one raster output, the result will be a tuple of arrays.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

i.atcorr performs atmospheric correction on the input raster map
using the 6S algorithm ( Second Simulation of Satellite Signal in the
Solar Spectrum ). A detailed algorithm description is available at the Land Surface Reflectance Science Computing Facility
website .

Important: Current region settings are ignored! The region is adjusted
to cover the input raster map before the atmospheric correction is
performed. The previous settings are restored afterwards.

If the -r flag is used, the input raster map is treated as reflectance . Otherwise, the input raster map is treated as radiance values and it is converted to reflectance at the i.atcorr runtime. The
output data are always reflectance.

The satellite overpass time has to be specified in Greenwich Mean Time
(GMT).

An example of the 6S parameters could be:

If the position is not available in longitude-latitude (WGS84), the m.proj conversion module can be used to reproject from a
different reference system.

---

## Authors

Original version of the program for GRASS 5: Christo Zietsman, 13422863(at)sun.ac.za
Code clean-up and port to GRASS 6.3, 15.12.2006: Yann Chemin, ychemin(at)gmail.com
Documentation clean-up + IRS LISS sensor addition 5/2009: Markus Neteler, FEM, Italy
ASTER sensor addition 7/2009: Michael Perdue, Canada
AVNIR, IKONOS sensors addition 7/2010: Daniel Victoria, Anne Ghisla
RapidEye sensors addition 11/2010: Peter Löwe, Anne Ghisla
VGT1 and VGT2 sensors addition from 6SV-1.1
sources ,
addition 07/2011: Alfredo Alessandrini, Anne Ghisla
Added Landsat 8 from NASA
sources ,
addition 05/2014: Nikolaos Ves
Geoeye1 addition 7/2015: Marco Vizzari
Worldview3 addition 8/2016: Markus Neteler, mundialis.de, Germany
Sentinel-2A addition 12/2016: Markus Neteler, mundialis.de, Germany
Sentinel-2B addition 1/2018: Stefan Blumentrath, Zofie Cimburova, Norwegian Institute for Nature
Research, NINA, Oslo, Norway
Worldview4 addition 12/2018: Markus Neteler, mundialis.de, Germany
AVIRIS/Hyperion addition 11/2023: Yann Chemin, SOPHIA Engineering, FR

---

## Resources

- [Official i.atcorr manual](https://grass.osgeo.org/grass-devel/manuals/i.atcorr.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/i.atcorr.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
