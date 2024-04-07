## Probabilistic-Crowdshipping-Model-for-Last-Mile-Delivery.
- Dimitra G. Triantali (d.triantali@uoi.gr)
- Konstantina Skouri (kskouri@uoi.gr)
- Konstantinos E. Parsopoulos (kostasp@uoi.gr)

## Data

#### Created scenarios

For the experimental analysis of the proposed strategy, a test suite consisting of 81 scenarios was produced by the combinations of the following values for the underlying parameters:

- Number of transshipment nodes: t &isin; \{0, 1, 2\}
- Total number of customers: c &isin; \{10, 15, 20\}
- Available occasional drivers: o &isin; \{10, 15, 20\}
- Number of classical vehicles: v &isin; \{1, 2, 3\}

The corresponding parameter values per scenario were also used as the naming convention: t_c_o_v. For example, the scenario with 2 transshipment nodes, 20 customers, 15 occasional drivers, and 3 classical vehicles is denoted as 2_20_15_3. 

The created scenarios are stored in the [scenarios](https://github.com/DimitraTriantali/Probabilistic-Crowdshipping-Model-for-Last-Mile-Delivery/tree/cb0a08ec8adb88e9c20a5674432e1c6c68e437db/data/scenarios) folder. The first row of the dataset contains details about the company's permanent installations. The "lat_or" and "lon_or" columns represent the depot's latitude and longitude, while the "lat_des" and "lon_des" columns indicate the latitude and longitude of the node where the company's permanent fleets finish their routes. 

If the dataset includes transshipment nodes, their information is listed in rows 1,2,…,t. "lat_or" and "lon_or" indicate the node's latitude and longitude, while "max_capacity" denotes its maximum capacity. 

The customers' information is provided in the rows indexed by t+1,t+2,...,t+c. "lat_or" and "lon_or" indicate the latitude and longitude of their location, respectively. The "demand" field denotes the weight of their order, while the "prob" column represents the probability of being delivered by an occasional driver if assigned to one. 

The information on occasional drivers can be found in the rows indexed by t+c+1,t+c+2,...,t+c+o. The columns "lat_or" and "lon_or" represent the latitude and longitude of their starting point. On the other hand, the "lat_des" and "lon_des" columns show the latitude and longitude of their destination. The "transport_mode" column describes the mode of transportation the occasional driver uses. The "max_capacity" column represents the maximum weight they can carry, and the "prob" column includes the probability of accepting the assigned order. The "radius" column indicates the maximum distance they are willing to travel to deliver the order. 

The information about classical vehicles is provided in rows indexed by t+c+o+1,t+c+o+2,...,t+c+o+v. The "lat_or" and "lon_or" indicate the latitude and longitude of their origin, while the "lat_des" and "lon_des" columns show their destination. The "transport_mode" column denotes the mode of transport used by these vehicles, and the "max_capacity" column specifies the maximum weight they can carry. 

The emergency vehicle's information is provided in the last row. The "lat_or" and "lon_or" represent the latitude and longitude of its origin, while its destination is included in the "lat_des" and "lon_des" columns.

Furthermore, the employed distances between the corresponding nodes of each scenario are included in the [distances]() folder. We append each scenario's name by a variable m &isin; \{bicycle, car, motorcycle, pedestrian, truck\} that denotes the employed mode of transportation.

## Results

#### Decisions

The results of the decision-making model are included in the file [decisions_using_boosting_predictions](https://github.com/DimitraTriantali/Data-driven-optimization-of-vendor-managed-inventory-for-replenishment-and-distribution-decisions/blob/aa91360599262e5b278926e65e0f8df58bc06338/results/decisions/decisions_using_boosting_predictions.zip). More specifically, for each scenario, the order quantities, inventory levels, and lost sales for the vendor and each retailer are provided. Especially for the base scenario, the folder [capacities](https://github.com/DimitraTriantali/Data-driven-optimization-of-vendor-managed-inventory-for-replenishment-and-distribution-decisions/tree/cc9df78bc4a1ecca763e4408a7b0ed3560dc9628/results/decisions/capacities) contains this information with varying values of the capacity parameters, while the folder [decisions_on_base_scenario](https://github.com/DimitraTriantali/Data-driven-optimization-of-vendor-managed-inventory-for-replenishment-and-distribution-decisions/tree/cc9df78bc4a1ecca763e4408a7b0ed3560dc9628/results/decisions/decisions_on_base_scenario) provides the data when using the predictions of the four forecasting approaches as well as the real demands during the decision-making process.

#### Predicted demands

The predicted demands are stored in the [forecasted_demands](https://github.com/DimitraTriantali/Data-driven-optimization-of-vendor-managed-inventory-for-replenishment-and-distribution-decisions/tree/ac7ea8203ce8d29d5b5a3d23e090849b26785c40/results/forecasted_demands) folder, with each file named as p_prediction_results_T_t, where p represents the employed forecasting approach (ADD, ARIMA, FFNN, BOOSTING), and t denotes the length of the time horizon (1, 3, 7, 14). Each file contains the top-performing variation of the forecasting approach for each retailer, based on achieving the lowest mean squared error (MSE) within the testing vector. The file also includes the corresponding MSE and the predictions.

## Licence

[MIT License](https://github.com/DimitraTriantali/VMI/blob/1b942e22cf74f78bf53897459dacd401e654d56a/LICENSE)
