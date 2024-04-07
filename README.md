## Data-driven demand forecasting for vendor-managed inventory optimization.
- Dimitra G. Triantali (d.triantali@uoi.gr)
- Konstantina Skouri (kskouri@uoi.gr)
- Konstantinos E. Parsopoulos (kostasp@uoi.gr)

## Data

#### Created scenarios

For the experimental analysis of the proposed strategy, a test suite consisting of 36 scenarios was produced by the combinations of the following values for the underlying parameters:

- Time horizon: t &isin; \{1, 3, 7, 14\}
- Number of VMIs: v &isin; \{5, 10, 20\}
- Number of non-VMIs: n &isin; \{5, 10, 20\} 

The corresponding parameter values per scenario were also used as the naming convention: Tt_Vv_Nn. For example, the scenario with a time horizon of 7 time periods, 10 VMIs, and 20 non-VMIs is denoted as T7_V10_N20. 

The created scenarios are stored in the [scenarios](https://github.com/DimitraTriantali/Data-driven-optimization-of-vendor-managed-inventory-for-replenishment-and-distribution-decisions/tree/390f2e8355d99cec7f17cc138dfa3883d6822e53/data/scenarios) folder. Data is stored for both the vendor and all retailers in every scenario. The first column shows the indicators, while the second column displays the title of the information provided. The third column displays the vendor's ordering and holding costs. Each retailer's info is listed in columns retailer_1 to retailer_(m+n), describing its ordering, holding, and lost sales cost, as well as the hyperparameter(s) of its demand distribution.

#### Retailers' demands

To differentiate between the retailers, we have designated two indices for each. The first index, j, indicates the type of retailer, with a value of V for VMIs and N for non-VMIs. The second index, i, corresponds to the retailer's unique ID and ranges from 1 to 20. For the sake of simplicity, we refer to each retailer as j_i. 

The demand history of all retailers is included in the [demands](https://github.com/DimitraTriantali/Data-driven-optimization-of-vendor-managed-inventory-for-replenishment-and-distribution-decisions/tree/390f2e8355d99cec7f17cc138dfa3883d6822e53/data/demands) folder. From each demand time-series, the forecast model employs the last 180 values.

## Results

#### Decisions

The results of the decision-making model are included in the file [decisions_using_boosting_predictions](https://github.com/DimitraTriantali/Data-driven-optimization-of-vendor-managed-inventory-for-replenishment-and-distribution-decisions/blob/aa91360599262e5b278926e65e0f8df58bc06338/results/decisions/decisions_using_boosting_predictions.zip). More specifically, for each scenario, the order quantities, inventory levels, and lost sales for the vendor and each retailer are provided. Especially for the base scenario, the folder [capacities](https://github.com/DimitraTriantali/Data-driven-optimization-of-vendor-managed-inventory-for-replenishment-and-distribution-decisions/tree/cc9df78bc4a1ecca763e4408a7b0ed3560dc9628/results/decisions/capacities) contains this information with varying values of the capacity parameters, while the folder [decisions_on_base_scenario](https://github.com/DimitraTriantali/Data-driven-optimization-of-vendor-managed-inventory-for-replenishment-and-distribution-decisions/tree/cc9df78bc4a1ecca763e4408a7b0ed3560dc9628/results/decisions/decisions_on_base_scenario) provides the data when using the predictions of the four forecasting approaches as well as the real demands during the decision-making process.

#### Predicted demands

The predicted demands are stored in the [forecasted_demands](https://github.com/DimitraTriantali/Data-driven-optimization-of-vendor-managed-inventory-for-replenishment-and-distribution-decisions/tree/ac7ea8203ce8d29d5b5a3d23e090849b26785c40/results/forecasted_demands) folder, with each file named as p_prediction_results_T_t, where p represents the employed forecasting approach (ADD, ARIMA, FFNN, BOOSTING), and t denotes the length of the time horizon (1, 3, 7, 14). Each file contains the top-performing variation of the forecasting approach for each retailer, based on achieving the lowest mean squared error (MSE) within the testing vector. The file also includes the corresponding MSE and the predictions.

## Licence

[MIT License](https://github.com/DimitraTriantali/VMI/blob/1b942e22cf74f78bf53897459dacd401e654d56a/LICENSE)
