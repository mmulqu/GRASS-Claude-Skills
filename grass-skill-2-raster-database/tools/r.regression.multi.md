# r.regression.multi

**Category**: raster

## Description

Calculates multiple linear regression from raster maps.

---

## grass.tools API (Recommended for new code)

⚠️ **Status**: Experimental in GRASS 8.5, will be stable in 8.6

### Function Signature

```python
tools.r_regression_multi(mapx,mapy,residuals=None,estimates=None,output=None,format="shell",flags=None,overwrite=None,verbose=None,quiet=None,superquiet=None)
```

### Parameters

1. **`mapx : str | list[str], required`**
   - Map for x coefficient
   - Used as: input, raster, name

2. **`mapy : str | np.ndarray, required`**
   - Map for y coefficient
   - Used as: input, raster, name

3. **`residuals : str | type(np.ndarray) | type(np.array) | type(gs.array.array), optional`**
   - Map to store residuals
   - Used as: output, raster, name

4. **`estimates : str | type(np.ndarray) | type(np.array) | type(gs.array.array), optional`**
   - Map to store estimates
   - Used as: output, raster, name

5. **`output : str, optional`**
   - ASCII file for storing regression coefficients (output to screen if file not specified).
   - Used as: output, file, name

6. **`format : str, required`**
   - Output format
   - Used as: name
   - Allowed values: shell, json
   - *(see [full docs](https://grass.osgeo.org/grass-devel/manuals/r.regression.multi.html#__tabbed_2_3) for all details)*

7. **`flags : str, optional`**
   - Allowed values: g
   - g
   - Print in shell script style [deprecated]

8. **`overwrite : bool, optional`**
   - Allow output files to overwrite existing files
   - Default: None

9. **`verbose : bool, optional`**
   - Verbose module output
   - Default: None

10. **`quiet : bool, optional`**
   - Quiet module output
   - Default: None

11. **`superquiet : bool, optional`**
   - Very quiet module output
   - Default: None


*Showing 10 of 11 parameters - see [full documentation](https://grass.osgeo.org/grass-devel/manuals/r.regression.multi.html#__tabbed_2_3) for all*

### Returns

result : grass.tools.support.ToolResult | np.ndarray | tuple[np.ndarray] | None
If the tool produces text as standard output, a ToolResult object will be returned. Otherwise, None will be returned. If an array type (e.g., np.ndarray) is used for one of the raster outputs, the result will be an array and will have the shape corresponding to the computational region. If an array type is used for more than one raster output, the result will be a tuple of arrays.

### Raises

grass.tools.ToolError: When the tool ended with an error.

---

---

## Detailed Description

r.regression.multi calculates a multiple linear regression from raster
maps, according to the formula

where

In R notation:

r.regression.multi is designed for large datasets that can not be
processed in R. A p value is therefore not provided, because even very
small, meaningless effects will become significant with a large number
of cells. Instead it is recommended to judge by the estimator b, the
amount of variance explained (R squared for a given variable) and the
gain in AIC (AIC without a given variable minus AIC global must be
positive) whether the inclusion of a given explaining variable in the
model is justified.

The b coefficients (b0 is offset), R squared or coefficient of
determination (Rsq) and F are identical to the ones obtained from
R-stats's lm() function and R-stats's anova() function. The AIC value is
identical to the one obtained from R-stats's stepAIC() function (in case
of backwards stepping, identical to the Start value). The AIC value
corrected for the number of explaining variables and the BIC (Bayesian
Information Criterion) value follow the logic of AIC.

R squared for each explaining variable represents the additional amount
of explained variance when including this variable compared to when
excluding this variable, that is, this amount of variance is explained
by the current explaining variable after taking into consideration all
the other explaining variables.

The F score for each explaining variable allows testing if the inclusion
of this variable significantly increases the explaining power of the
model, relative to the global model excluding this explaining variable.
That means that the F value for a given explaining variable is only
identical to the F value of the R-function summary.aov if the given
explaining variable is the last variable in the R-formula. While R
successively includes one variable after another in the order specified
by the formula and at each step calculates the F value expressing the
gain by including the current variable in addition to the previous
variables, r.regression.multi calculates the F-value expressing the
gain by including the current variable in addition to all other
variables, not only the previous variables.

The AIC value is identical to the one obtained from the R-function
stepAIC() when excluding this variable from the full model. The AIC
value corrected for the number of explaining variables and the BIC value
(Bayesian Information Criterion) value follow the logic of AIC. BIC is
identical to the R-function stepAIC with k = log(n). AICc is not
available through the R-function stepAIC.

---

## See Also

Related tools:
- [`d.correlate`](https://grass.osgeo.org/grass-devel/manuals/d.correlate.html)
- [`r.regression.line`](https://grass.osgeo.org/grass-devel/manuals/r.regression.line.html)
- [`r.stats`](https://grass.osgeo.org/grass-devel/manuals/r.stats.html)

---

## Resources

- [Official r.regression.multi manual](https://grass.osgeo.org/grass-devel/manuals/r.regression.multi.html)
- [grass.tools API documentation](https://grass.osgeo.org/grass-devel/manuals/r.regression.multi.html#__tabbed_1_3)
- [GRASS GIS Documentation](https://grass.osgeo.org/grass85/manuals/)

---

*Generated from GRASS GIS 8.5 documentation*
