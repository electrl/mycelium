# Mycelium 
## Simple 2D simulation of mycelium growth

Simulation aims to study myceliea branching and colonization patterns.

##### Requirements
The simulation is prepared in Python 2.7. Apart from well know packages for scientific computing such as Numpy and Scipy we use Shapely (https://github.com/Toblerity/Shapely). For visualization we use Matplotlib.

##### Reference

[1] Steven D. Harris, Branching of fungal hyphae: regulation, mechanisms and comparison with other branching systems, Mycologia 100 (6), 2008

### Rule for branching and model implementation
We assume there is only one expanding branch. On each round, if possible - we expand leading branch. Then from all nodes we choose random but positive number of other nodes to expand. We assume the branches do not cross each other. We decide how close we allow two segments to be. Segments are added one at a time. Number of possible branches at a given node is limited. Segments' length and angle are random from given ranges.

The leading node is called expander node.

### Parameters
#### Model parameters

Paremeters to decide about actuall shape of output 

max - max angle for expander node

max_branch - max angle for drawed segment

bfactor - segment branch length

min_dist - minimal distance between segments

branches - maximal number of branches at given node (not counting in parent segment)

bfrac - at each iteration we choose from 1 to node_idx/bfrac nodes to expand

#### Technical parameters of simulation

iterations - no of iterations to run

segments_term - here we store node coordinates - initially we need here one point to start with

expander - expander node for leading branch - by default set to 1

expander_iters - max iterations for expander node loop

drawed_iters - max iterations for drawed node loop

node_idx - count of nodes


### Possible extentions to add

1. profiling and optimization
2. branching between existing nodes
3. smoothing graph shape
4. add other agents or objects interacting with model
