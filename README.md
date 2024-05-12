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

The corresponding parameter values per scenario were also used as the naming convention: t_c_o_v. For example, the scenario with 2 transshipment nodes, 20 customers, 15 occasional drivers, and 3 classical vehicles is denoted as 2_20_15_3. The created scenarios are stored in the [scenarios](https://github.com/DimitraTriantali/Probabilistic-Crowdshipping-Model-for-Last-Mile-Delivery/tree/cb0a08ec8adb88e9c20a5674432e1c6c68e437db/data/scenarios) folder. 

The first row of the dataset contains details about the company's permanent installations. The "lat_or" and "lon_or" columns represent the depot's latitude and longitude, respectively, while the "lat_des" and "lon_des" columns indicate the latitude and longitude of the node where the company's permanent fleets finish their routes, respectively. 

If the dataset includes transshipment nodes, their information is listed in rows 1,2,…,t. For each transshipment node, the columns "lat_or" and "lon_or" indicate its latitude and longitude, respectively, while the "max_capacity" column denotes its maximum capacity. 

The customers' information is provided in the rows indexed by t+1,t+2,...,t+c. For each customer, the columns "lat_or" and "lon_or" indicate the latitude and longitude of his location, respectively. The "demand" column denotes the weight of his order, while the "prob" column represents the probability of being delivered by an occasional driver if assigned to one. 

The information on occasional drivers can be found in the rows indexed by t+c+1,t+c+2,...,t+c+o. For each occasional driver, the columns "lat_or" and "lon_or" represent the latitude and longitude of his starting point, respectively. On the other hand, the "lat_des" and "lon_des" columns show the latitude and longitude of his destination, respectively. The "transport_mode" column describes the mode of transportation he uses. The "max_capacity" column represents the maximum weight he can carry, and the "prob" column includes the probability of accepting the assigned order. The "radius" column indicates the maximum distance he is willing to travel to deliver the order. 

Information about classical vehicles is provided in rows indexed by t+c+o+1,t+c+o+2,...,t+c+o+v. The "lat_or" and "lon_or" columns indicate the latitude and longitude of their origin, respectively, while the "lat_des" and "lon_des" columns show the latitude and longitude of their destination, respectively. The "transport_mode" column denotes the mode of transport used by these vehicles, and the "max_capacity" column specifies the maximum weight they can carry. 

The last row provides information on emergency vehicles. The "lat_or" and "lon_or" columns represent the latitude and longitude of their origin, respectively, while their destination coordinates are included in the "lat_des" and "lon_des" columns.

In addition, you can find the distances between the nodes of each scenario in the [distances](https://github.com/DimitraTriantali/Probabilistic-Crowdshipping-Model-for-Last-Mile-Delivery/tree/00f4b4d955f500349154f786af01098f8c7eb8cb/data/distances) folder. The folder is organized into three files based on the value of t. Each scenario's name is followed by a variable m that represents the mode of transportation used, which can be a bicycle, car, motorcycle, pedestrian, or truck.

## Results

The results of the decision-making model for the constructed scenarios can be found in the folder [scenarios_results](https://github.com/DimitraTriantali/Probabilistic-Crowdshipping-Model-for-Last-Mile-Delivery/tree/ba03572fe9926b80238ed645ba4db7fc3b09042d/results/scenarios_results), which are organized by the value of t. For each scenario, the "optimal_solution" folder contains the optimal solutions that we obtained by examining different subsets of selected occasional drivers (F) and the customers assigned to occasional drivers (CO). Each file in the "optimal_solution" folder has a name "c__F=f_CO=co", where c is the obtained cost of the system, f is the list of the IDs of the selected occasional drivers, and co is the set of IDs of the customers that are assigned to the occasional drivers. The file includes the cost of the system (objective), the state of the obtained solution (optimal or near-optimal), the values of the decision variables, the costs of the classical vehicles, emergency vehicles, and the occasional drivers, as well as the running time of CPLEX for this particular examined case.

Especially for the 0_10_10_1 scenario, the file [varying_b_od_ed_fees](https://github.com/DimitraTriantali/Probabilistic-Crowdshipping-Model-for-Last-Mile-Delivery/blob/ba03572fe9926b80238ed645ba4db7fc3b09042d/results/varying_b_od_ed_fees.zip) contains the best solutions that were obtained by varying the acceptance threshold and the fees of the occasional drivers and emergency vehicles. The results are organized into three subfolders based on the acceptance threshold selected, and each subfolder contains sub-subfolders with the name a_b. Here, a represents the fee for each occasional driver, while b represents the cost of hiring an emergency vehicle.

## Licence

[MIT License](https://github.com/DimitraTriantali/Probabilistic-Crowdshipping-Model-for-Last-Mile-Delivery/blob/64a160ea27976dd15d6a9a6a4b97ac2e41ef3fc9/LICENSE)
