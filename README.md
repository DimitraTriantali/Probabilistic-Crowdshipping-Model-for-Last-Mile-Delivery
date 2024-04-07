## Probabilistic-Crowdshipping-Model-for-Last-Mile-Delivery.
- Dimitra G. Triantali (d.triantali@uoi.gr)
- Konstantina Skouri (kskouri@uoi.gr)
- Konstantinos E. Parsopoulos (kostasp@uoi.gr)

## Data

For the experimental analysis of the proposed model, a test suite consisting of 81 scenarios was produced by the combinations of the following values for the underlying parameters:

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

Furthermore, the employed distances between the corresponding nodes of each scenario are included in the [distances](https://github.com/DimitraTriantali/Probabilistic-Crowdshipping-Model-for-Last-Mile-Delivery/tree/00f4b4d955f500349154f786af01098f8c7eb8cb/data/distances) folder organized into 3 files based on the value of t. We append each scenario's name by a variable m &isin; \{bicycle, car, motorcycle, pedestrian, truck\} that denotes the employed mode of transportation.

## Results

The results of the decision-making model for the constructed scenarios are included in the file [scenarios_results](https://github.com/DimitraTriantali/Probabilistic-Crowdshipping-Model-for-Last-Mile-Delivery/tree/ba03572fe9926b80238ed645ba4db7fc3b09042d/results/scenarios_results) organized by the value of t. More specifically, for each scenario, .... Especially for the 0_10_10_1 scenario, the file [varying_b_od_ed_fees](https://github.com/DimitraTriantali/Probabilistic-Crowdshipping-Model-for-Last-Mile-Delivery/blob/ba03572fe9926b80238ed645ba4db7fc3b09042d/results/varying_b_od_ed_fees.zip) contains this information with varying values of the acceptance threshold and the occasional and emergency fees. 

## Licence

[MIT License](https://github.com/DimitraTriantali/VMI/blob/1b942e22cf74f78bf53897459dacd401e654d56a/LICENSE)
