# {{Assessment of fisheries impact in the Dutch part of the Northsea, 2009. The BFIAT approach}}

## Introduction

Demersal fisheries are a major contributor to global food supply, but at the same time significantly affect marine ecosystem functioning. Physical contact of fishing gear with the seabed induces many changes to the sediment, including a direct mortality of benthic organisms. 
Understanding the impact of bottom trawling gear on benthic life is a necessary step towards a correct assessment of fisheries impact and eventually fisheries management.

The Bfiat model (Beauchard and Soetaert, 2026) estimates reductions in benthic biomass, density or ecosystem functioning due to bottom trawling. 

Here its methodology is applied to benthic data from EMODnet biology. 

The data are from the Dutch part of the North sea, for the year 2009 (the MWTL data). 
Using the Bfiat model, we quantify how bottom fishing interacts with species life-history traits to shape benthic state in terms of reduction in benthic biomass and the potential of the benthic fauna to mix and ventilate the sediment (the two latter via the so-called bioturbation and bio-irrigation potential). Sediment mixing and ventilation are important ecosystem functions, as they affect sediment geochemistry and global biogeochemical cycles.

The source code is in directory *analysis* as a number of quarto files. The entire procedure can be run from the Terminal (with directory set to analysis) by writing:

```
quarto render
```

This will put the output in the correct directories.

## Directory structure


```
{{Bfiat_application_MWTL_2009}}/
├── analysis (empty)
├── data/
│   ├── derived_data/
│   └── raw_data/
├── docs/
├── product/
└── scripts/
```

* **analysis** - quarto files
* **data** - Raw and derived data 
   - derived_data: several intermediate rda and netcdf files
   - raw_data: shapefiles.rda, contains 3 shape files to mask gridded output.
* **docs** - Rendered reports (HTML files)
* **product** - Output product file: fishing_impact_2009_bfiat.nc
* **scripts** - Reusable code (empty)

## Data series

The data product has used the MWTL macro-benthic data from the EMODnet portal. The MWTL data are describe in Leewis et al., 2015.

Fisheries data were obtained from ICES (ICES Technical Service, 2018).

Trait databases used are described in Beauchard et al, (2021, 2023), Queiros et al., (2013) and Wrede et al., 2018.

All these data were made available from the Btrait package.

```
{{data_wfs_request}}
```

## Data product

The product contains the fractional reductions due to bottom trawling for the following variables:

* macrofaunal biomass (*fraction_biomass_lost*)
* bioturbation potential (*fraction_BPc_lost*)
* bioirrigation potential (*fraction_IPc_lost*)

for the MWTL data for the year 2009. 

fractional loss for biomass is estimated as 

$$fraction_biomass_lost = 1 - \frac{biomass}{K\_biomass},$$ 

where *biomass* is the observed total biomass, as obtained from the EMODnet data portal, and *K_biomass* is the carrying capacity, i.e. the biomass that would be attained in the absence of fishing. 

The larger is the *fraction_biomass_lost*, the higher is the impact of fisheries on benthic biomass.

## More information:

## References

### Model

Beauchard, Olivier, Soetaert, Karline (2026). “Bottom fishing assessment tool: An R package to model
  the effects of bottom trawling on the marine benthos.” _Ecological Applications_, *36*(5), e70282.
  doi:10.1002/eap.70282 <https://doi.org/10.1002/eap.70282>.

### Trait databases:

Beauchard O, Brind'Amour A, Schratzberger M, Laffargue P, Hintzen NT, Somerfield PJ, Piet G (2021) A generic approach to develop a trait-based indicator of trawling-induced disturbance. Mar Ecol Prog Ser 675:35-52. https://doi.org/10.3354/meps13840

Beauchard, O., Murray S.A. Thompson, Kari Elsa Ellingsen, Gerjan Piet, Pascal Laffargue, Karline Soetaert, 2023. Assessing sea floor functional diversity and vulnerability. Marine Ecology Progress Serie v708, p21-43, The CEFAS trait dataset:

Ana M. Queiros, Silvana N. R. Birchenough, Julie Bremner, Jasmin A. Godbold, Ruth E. Parker, Alicia Romero-Ramirez, Henning Reiss, Martin Solan, Paul J. Somerfield, Carl Van Colen, Gert Van Hoey, Stephen Widdicombe, 2013. A bioturbation classification of European marine infaunal invertebrates. Ecology and Evolution 3 (11), 3958-3985

A. Wrede, J.Beermann, J.Dannheim, L.Gutow, T.Brey, 2018. Organism functional traits and ecosystem supporting services - A novel approach to predict bioirrigation. Ecological indicators, 91, 737-743.

### R-packages: 

Karline Soetaert, Olivier Beauchard (2023). R-package Btrait: Working with Biological density,
  taxonomy, and trait composition data. Data product created under the European Marine Observation Data
  Network (EMODnet) Biology Phase IV.

Karline Soetaert, Olivier Beauchard (2024). R-package Bfiat: Tools for estimating the impact of bottom
  disturbance on sediment ecosystems. Data product created under the European Marine Observation Data
  Network (EMODnet) Biology Phase V, under the NECCTON project (New Copernicus Capability for Trophic
  Ocean Networks), and under the OceanICU (understanding Ocean Carbon) project.
  
### Code and methodology

{{link_code}}

### Citation and download link

This product should be cited as:

{{product_citation}}

Available to download in:

{{link_download}}

### Authors

{{Karline Soetaert}}
