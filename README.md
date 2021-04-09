## Code documentation of the "Disparities and Equity Issues in Electric Vehicles Rebate Allocation" journal article.
The preliminary research results were presented at TRB 2021. 
The complete scientific work is hosted at [SSRN](https://ssrn.com/abstract=3687504), and accepted by Energy Policy journal.

### Rcode and RMarkDown
We used R to process socioeconomic data including [California rebate data](https://cleanvehiclerebate.org/eng/rebate-statistics) from 2010 to 2018, median income and population data from [Census Bureau](https://www.census.gov/data/data-tools.html), and the [CES3.0 score record](https://oehha.ca.gov/calenviroscreen/report/calenviroscreen-30) from The Office of Environmental Health Hazard Assessment (OEHHA) in California.
The main processing is to compute the Gini index and Suit index leveraging the aforementioned data. The detailed codes are included in '''data_visualization.rmd'''.

### Geoda 

After preliminary processing of the data in R, we feed the rebate, income, CES3.0 score into Geoda for spatial distribution and autocorrelation tested, achieved by Moran's I statistic.
The well-developed functions and tools in Geoda enable processing that can be easily reproduced. The brief steps are summarized as below:
1. Import geoda/tl_2016_06_tract.shp to Geoda
2. Access the ClusterMaps section, select Univariate Local Moran's I (or Bivariate Local Moran's I accordingly).
3. Import dependent variable as income/CES3.0 score and independent variable as rebate. We have data on varying temporal horizons, e.g., per year, average of before-/after-income-cap policy, and average over years.
4. As a recommendation, the metrics that we selected are per-year and before-/after policy ones.

We are happy to help if you have any question. If you used any part of the code, please cite the following paper: 

@article{guo2020disparities,
  title={Disparities and Equity Issues in Electric Vehicles Rebate Allocation},
  author={Guo, Shuocheng and Kontou, Eleftheria},
  journal={Available at SSRN 3687504},
  year={2020}
}
