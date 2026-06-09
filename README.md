# Exoplanet Transit Analysis — WASP-39b
Analysis of the WASP-39b exoplanet transit using real observational 
data from the TESS mission via the MAST archive.

## What This Project Does
- Reads TESS light curve data directly from FITS format 
  using Lightkurve
- Cleans the data by removing NaNs and flattening 
  long-term stellar variability
- Normalizes stellar flux for consistent analysis
- Phase-folds the light curve using WASP-39b's known 
  orbital period (6.101 days)
- Exports processed data to CSV for further analysis

## The Science Behind It
WASP-39b is a hot Saturn-type exoplanet orbiting its host star every ~6.1 days. When it transits (passes in front of its star), it blocks a small fraction of starlight — visible as a dip in the light curve.
Phase folding stacks multiple transits on top of each other by aligning them to the planet's orbital period, making the transit signal clearer and stronger.

## Key Parameters Used
| Parameter | Value |
|---|---|
| Orbital Period | 6.101 days |
| Epoch (Transit Time) | 2457670.6 BJD |
| TESS Sector | 51 |
| Flatten Window | 401 cadences |

## Libraries Used
- Lightkurve
- Matplotlib

## Data Source
TESS light curve data accessed via MAST archive
https://mast.stsci.edu

## What I Learned
Flattening removes slow brightness variations caused by stellar activity — without it, the transit signal gets buried in noise. Phase folding revealed the transit dip clearly across multiple orbital periods.

## Results
Transit depth: 0.0268 (2.68% stellar brightness decrease). 
Derived planetary radius: 1.068 × 10⁸ m (cf. literature value 9.13 × 10⁷ m, ~17% overestimate attributed to noise in raw light curve). 
Equilibrium temperature: ~1170K. 
Density: 0.104 g/cm³.
Results consistent with published characterization of WASP-39b as an inflated hot gas giant.
