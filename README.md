**M**ultiscale **G**eographically **W**eighted **R**egression (MGWR)
=======================================

[![Build Status](https://travis-ci.org/pysal/mgwr.svg?branch=master)](https://travis-ci.org/pysal/mgwr)
[![Documentation Status](https://readthedocs.org/projects/mgwr/badge/?version=latest)](https://mgwr.readthedocs.io/en/latest/?badge=latest)
[![PyPI version](https://badge.fury.io/py/mgwr.svg)](https://badge.fury.io/py/mgwr)

This module provides functionality to calibrate multiscale (M)GWR as well as traditional GWR. It is
built upon the sparse generalized linear modeling (spglm) module. 

Features
--------

- GWR model calibration via iteratively weighted least squares for Gaussian,
  Poisson, and binomial probability models.
- GWR bandwidth selection via golden section search or equal interval search
- GWR-specific model diagnostics, including a multiple hypothesis test
  correction and local collinearity
- Monte Carlo test for spatial variability of parameter estimate surfaces
- GWR-based spatial prediction
- MGWR model calibration via GAM iterative backfitting for Gaussian model
- Parallel computing for GWR and MGWR
- MGWR covariate-specific inference, including a multiple hypothesis test
  correction and local collinearity 
- Bandwidth confidence intervals for GWR and MGWR

Citation
--------
Oshan, T. M., Li, Z., Kang, W., Wolf, L. J., & Fotheringham, A. S. (2019). mgwr: A Python implementation of multiscale geographically weighted regression for investigating process spatial heterogeneity and scale. ISPRS International Journal of Geo-Information, 8(6), 269.

Creating a New Release (GeoLandSolutions Fork)
-----------------------------------------------

This fork is used by the model-pipeline project. To create a new release:

1. **Make and commit your changes:**
   ```bash
   git add .
   git commit -m "Description of changes"
   git push origin master
   ```

2. **Create a release tag:**

   Tags follow the format `v{version}-pinv.{increment}` where:
   - `{version}` is the mgwr version (e.g., `2.2.1`)
   - `{increment}` is the fork version (e.g., `0`, `1`, `2`, ...)

   Example:
   ```bash
   git tag -a v2.2.1-pinv.2 -m "Add pseudo-inverse implementation"
   git push origin v2.2.1-pinv.2
   ```

3. **Wait for GitHub Actions to complete:**

   - The workflow automatically builds a wheel and creates a GitHub Release
   - Check the [Actions tab](https://github.com/GeoLandSolutions/mgwr/actions) to monitor progress (~2-3 minutes)
   - The wheel will be attached to the release at: https://github.com/GeoLandSolutions/mgwr/releases

4. **Update model-pipeline:**

   See instructions in the [model-pipeline README](https://github.com/GeoLandSolutions/model-pipeline#updating-the-mgwr-fork) for how to update the dependency.

**Note:** The wheel filename will be `mgwr-2.2.1-py3-none-any.whl` (based on the version in `setup.py`), regardless of the tag increment number.
  
