The data that support the findings of the EVRPTW-FSL problem study.

1.File Format

Each instance is stored as a JSON file. The file contains four main parts:

  -(1)places
  -(2)jobs
  
  (3)electric_vehicle
  
  (4)time_span
  
2.Description of “places”

The field “places” is a list of all physical locations in the instance, including the depot, charging stations, original customer service locations, and additional flexible service locations.

Each location contains the following fields:

  (1)location_id: Unique identifier of the location.
  
  (2)x: x-coordinate of the location.
  
  (3)y: y-coordinate of the location.
  
  (4)depot: Boolean value indicating whether the location is the depot.
  
  (5)station: Boolean value indicating whether the location is a charging station.
  
  (6)capacity: Maximum number of customers that can be served at this service location. For depot and charging stations, this value is set to 0.
  
  (7)serving_customers: List of customers that can be served at this location. For depot and charging stations, this list is empty.
  
Location types are identified as follows:

  (1)depot = true and station = false: depot.
  
  (2)depot = false and station = true: charging station.
  
  (3)depot = false and station = false: service location.

3. Description of “jobs”

The field “jobs” is a list of all customer requests. Each customer contains the following fields:

  (1)customer_id: Unique identifier of the customer.
  
  (2)ReadyTime: Earliest service start time of the customer.
  
  (3)DueDate: Latest service start time of the customer.
  
  (4)demand: Demand of the customer.
  
  (5)ServiceTime: Service duration of the customer.
  
  (6)preferredLocationId: The original or preferred service location of the customer.
  
  (7)availableLocationsId: List of candidate service locations where the customer can be served.
  
Each customer must be assigned to exactly one location from its availableLocationsId list. If the selected service location is different from the preferredLocationId, a deviation cost is incurred.<br>4. Description of “electric_vehicle”

The field “electric_vehicle” gives the main vehicle-related parameters:

  (1)Q: Battery capacity of the electric vehicle.
  
  (2)C: Vehicle loading capacity.
  
  (3)r: Energy consumption rate.
  
  (4)g: Recharging rate.
  
  (5)v: Vehicle speed.
  
These parameters are used to evaluate vehicle capacity feasibility, battery feasibility, travel time, and charging time.

5.Description of “time_span”

The field “time_span” defines the planning horizon of the instance:

  (1)beginning: Start time of the planning horizon.
  
  (2)end: End time of the planning horizon.
  
6.Data Availability

The generated EVRPTW-FSL instances are provided for reproducibility of the computational experiments. Users can parse each JSON file to obtain the depot, charging stations, service locations, customer information, candidate service-location sets, and electric vehicle parameters.


