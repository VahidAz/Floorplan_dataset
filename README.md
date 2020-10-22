# houseExpo++ dataset
## HouseExpo Dataset Augmented with Crowd Behavioral Features

The original dataset was create by Tingguang Li and et al. at Robotics, Perception, and AI Laboratory, The Chinese University of Hong Kong. The paper and video can be found at: https://arxiv.org/abs/1903.09845 . It contained about 35,126 2D floor plans with 252,550 rooms in total, together with the category label of each room(https://github.com/TeaganLi/HouseExpo).

houseExpo++: The new dataset which is augmented with crowd behaviroal features and design semantic features.

### Folder structures:
##### images: includes images of each floorplan
##### graphs: a json file for each floorplan which has the design semnatic features including square footage, connection between rooms and their direction
##### human behavioral features: a json file for each floorplan which includes the original json of houseExpo dataset plus human behavioral features for each room.

##### Data Format:
##### graphs:
A list of dictionaries which inclides:
- label: an unique label for each room

- position [X,Y]: the center coordinate of each room

- square footage: caclculated square footage of each room

- connections: a list of dictionaries to connected nodes and direction of connection

##### original floorplans plus human behaviroal features
The floorplans are stored as .json files. The data format is as follows:

- id (string): the unique house ID number.

- room_num (int): the number of rooms of this house.

- bbox (dict): bounding box of the whole house
-- "min": (x1, y1)
-- "max": (x2, y2)

- verts (list): each element (x, y) represents a vertex location (in meter).

- room_category (dict): the room categories and its bounding box, for example
-- "kitchen": (x1, y1, x2, y2), bounding box of each kitchen.
--- simulation_statistics (list): a list of simulation statistics for each bounding box within a room_category. 

----- not_completed_agents (int): number of agents who couldn't complete the crowd simulation scenario

----- max_evacuation_time (float): maximum time in seconds took by an agent in completing the simulation scenario

----- min_evacuation_time (float): minimum time in seconds took by an agent in completing the simulation scenario 

----- exit_flow_rate (float): the rate at which agents complete the simulation scenario (agents/second)

----- completed_agents (int): number of agents who successfully completed the crowd simulation scenario

----- max_traveled_distance (float): maximum distance in meter traveled by an agent in completing the simulation scenario

----- avg_evacuation_time (float): average time in seconds took by all the agent in completing the simulation scenario

----- avg_traveled_distance (float): average distance in meter traveled by all the agent in completing the simulation scenario

----- min_traveled_distance (float): minimum distance in meter traveled by an agent in completing the simulation scenario 

