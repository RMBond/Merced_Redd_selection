Merced River Redd Site Selection
================
Rosealea Bond
12 March, 2019

-   [General Goals](#general-goals)
-   [Logistic Regression Analysis - RB](#logistic-regression-analysis---rb)
-   [Interpolate a grainsize raster - CN](#interpolate-a-grainsize-raster---cn)
-   [Next To Do's](#next-to-dos)

<!-- README.md is generated from README.Rmd. Please edit that file -->
General Goals
-------------

This space is to document analyses preformed as part of the Harrison et al. Merced River Redd Site Selection paper. The GIT repository can be found here <https://github.com/RMBond/Merced_Redd_selection.git>

Logistic Regression Analysis - RB
---------------------------------

The goal is to perform a logistic regression investigating redd persistence (redd=1) and absence (redd=0). Potential parameters include depth, velocity, CSI, WSG, and DAR for each site (Merced River Ranch (mrr) and Robinson Reach (rr)) individually. The steps include generating a candidate set of models, run AIC, and additional statistics as needed. This analysis is similar to Benjankar et al., (2016).

-   The candidate model set was updated to include the five variables on their own plus CSI + DAR. Two notes on our candidate set of modes:
    -   Our data is on the same spatial grid (scale) so the interaction term used in Benjankar et al., (2016) was not included in the candidate set.
    -   DAR and WSG are highly correlated (and interrelated) so model comparison was not made between them (We did not propose the model CSI + WSG as part of the candidate set though we expect results would be simmilar to CSI + DAR).
-   The candiate set of models was run for each site separately since comparisons are being made *between* sites. If the sites were analysed at the same time (e.g. DAR + site), the question would be more general to that area of the Merced River (e.g. *among* sites).

**Description of Datasets:**
Logistic Regression input file **mHabVarsSite.csv** was generated by L. Harrison on 14 February 2019. The script <span style="color:purple">*Redd\_logisticregression.R*</span> was created to run the logistic regression analysis.

Interpolate a grainsize raster - CN
-----------------------------------

The goal here is to recalculate a `D50` and `D84` for each position/bend combination. From there we will use ArcGIS to merge the two pebble count datasets into one point shapefile, then interpolate a TIN and DEM within the wetted channel.

**Description of Datasets:** Currently there are two grainsize datasets. DWR from 2012 and Sam Emerson's thesis pebble count data from 2015. The DWR data is summarized to one `D50` and one `D84` value for each cross section, while Emerson's data has pebble count in the outer, middle and inner positions of each bend.

**Note:** for now CN is not uploading any of the spatial data to this repo, but can do that if it seems like it makes sense.

Next To Do's
------------

1.  ?
