# Three-Dimensional-Packing-Problem

## 1. Purpose
Finding out the max potential of Bin Fill Rate at a warehouse by assuming the right products will be placed into their best fit locations. 

## 2. Objectives
(1) Maximize Bin Fill Rate at a warehouse Level \
(2) Maximize Bin Fill Rate a each rack dimension Level \
(3) Minimize # of units per location (f) 

## 3. Constraints
(1) Max # of units per location (f_max) = 12 \
(2) No product mix in one location, one location can only have one dimension of carton 

## 4. Assumptions
(1) # of location counts per each rack dimension is limited based on warehouse configuration \
(2) # of product units is limited based on actual inventory on hand \
(3) a carton cannot be taken out once its placement is done \
(4) all six orthogonal orientations of a carton are considered 

## 5. Method
(1) Generate a list of all possible combination of rack dims and carton dims. Possible is defined as the # of units per location > 0. \
(2) Find the best fit location for each carton dimension \
(3) Group by rack dimension and determine placement sequence
    a. Scenario 1: total carton cube (carton units * carton cube) <= total rack cube (location count * rack cube), then place all units of cartons into destination racks \
    b. Scenario 2: single carton total cube > total rack cube, then allocate  f * location count number of cartons, overflow = carton units - f * location count. \
    c. Scenario 3: multiple carton total cube > total rack cube, while all of cartons can fit into 
