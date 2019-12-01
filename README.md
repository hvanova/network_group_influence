# Network-Group-Influence

## Group Influence on Spatially Connected and Random Networks 
### Complex Systems Independent Study
### Hannah VanWingen and Scott Page 

## Introduction 
This study directs attention to modeling groups within a network, and observing the influence of group behavior with regards to network convergence toward a value. Regarding the modeling of natural phenomena, specifically with groups of people that adopt social trends, defined groups are an important aspect to account for within the model as they have a large influence on an individual’s own presence and values. 

The models developed for this project are complicated in nature, as they attempt to address a variety of information (values), initial information distributions, probability distributions associated with an individual changing its value, the probability that any individual joins a group, a variation in the number of groups, the ‘meeting’ times and frequencies of groups, and individual actions within the groups as well as outside groups concerning how information is spread. For simplicity, the model allows for individuals to be a member of one group or a member of no group. 

## Summary of Terms 
For the purposes of observing the convergence of different types of information, two models are developed – one to observe averageable values, and one to observe distinct and non-averageable values. One model is coded with initial information drawn from 100 possible averageable values, and the other is coded with initial information drawn from N possible distinct values. They are referenced as 100-trait and N-trait respectively. The following terms are used within the models. 

Spatially Clustered Network – The number of links l is defined in relation to the average node degree d and the number of nodes n such that l = (d + n) / 2. Links are then created by asking one of the nodes to create a link with a node closest in proximity. 

Random Network – With a set average node degree, a normal distribution of the number of links from a given individual is established. For each node, a degree is chosen from this normal distribution and links are made to random nodes that exclude itself. 

Random Initial Information Distribution – Each node is assigned a random integer value from 0 to 99 for the 100-trait model. For the N-trait model, each node is assigned a random integer value from 0 to the predefined number of distinct traits. 

Normal Initial Information Distribution – Each node is assigned a random value drawn from a normal distribution with a mean of 50 and standard deviation of 34.1 for the 100-trait model.  

Uniform Initial Information Distribution – As it is only implemented in the N-trait model, for each value there is an equal (or offset by 1) number of nodes that initially adopt the value. 

Skewed Initial Information Distribution – As it is only implemented in the N-trait model, each node is assigned an integer value from a random exponential distribution of N values. 

Random Flip Distribution – Each individual is assigned a random probability of ‘flipping’ its value, that is, changing its value given the influence from a connecting link to a neighboring node. 

Uniform Flip Distribution – Each individual is assigned a ‘flip’ probability of 1. 

Normal Flip Distribution –  Each individual is assigned a ‘flip’ probability drawn from a normal distribution. 

Individual Action: Copy – Given the influence of a link to a neighboring node on a given individual node, and given the individual node’s probability of ‘flipping,’ the individual node may copy its neighbor’s value. 

Individual Action: Average – Given the influence of a link to a neighboring node on a given individual node, and given the individual node’s probability of ‘flipping,’ the individual node may adopt the average of its own value and its neighbor’s value. 

Group Action: High Influencer – Members within a group will all adopt the value of the node within the given group with the highest degree, taking into account links within and outside the group. 

Group Action: Average – As it is only implemented in the 100-trait model, members within a group will all adopt an average of all member values within the group. 

Group Action: Random Copy – Members within a group will all adopt the value of a random member within the group. 

Non-Uniform Meeting Time – Each group is assigned an individual time to meet. The offset is uniform, with group meetings equally dispersed within the range of the defined meeting frequency. 

## Model Functionality 
With each node’s probability of joining a group, a node may be assigned to a random group given the predefined number of groups. Groups are identified in the model by color, while information of individual ‘values’ are identified by node size. 

Upon ‘go’, each group meets if the modulo of the group’s meeting frequency with the current number of ticks is 0. The model runs until all nodes have adopted the same value. With one iteration, each node is influenced by each of its neighboring nodes given its individual flip probability. Upon ‘reset,’ information is reinitialized in the same network configuration of links and groups. 

## Results 
After running many enumerations of settings for both models, the most differential and interesting behavior is defined as follows. In general, the 100-trait model is excluded as it exhibits much more variation and randomness that is difficult to identify as group influence verses inherent network influence given the large variation in values. Additionally, with the 100-trait model, averaging becomes an irrelevant metric as group influence has little effect and the mean value wavers around the expected value after many resets. 

To increase the influence of group dynamics on a network, results are summarized over networks with 100 nodes in a spatially clustered configuration. Through running many trials, it is clear that group dynamics become more effective when the group sizes are larger. Additionally, for the purposes of summarizing results, semi-uniformity enforced among spatially clustered network configurations remain most significant. 

3-trait, Average Node Degree = 5, Skewed Initial Information, Normal Flip Distribution, Probability Joining Group = 1, Number of Groups = 10, Uniform Meeting Time, High Influencer Group Action, Meeting frequency = 2 

With skewed information, one would expect that with every reset of initial information distribution on a network, the network would converge to the value which initially dominates a higher percentage of the population. With the plot below, even when the values while trait 2 dominates initially, the initially least prevalent trait being 0 dominates in the end. Though this sort of behavior does not significantly prevail after may resets, it remains significant compared to the frequency of this behavior with similar networks with no groups. 

For a similar configuration but with no groups, common behavior is exhibited with the plot as follows. After many resets, similar behavior occurs where the initially dominant trait prevails. Overall, after many resets the convergence is more predictable for a network with no group than for a network with any number of groups. Additionally, the number of ticks toward convergence is significantly larger for networks with groups as opposed to networks without groups. 

Many enumerations of varied settings exhibit more variable behavior that does not have a clear dependence on groups. To discern clear dependence, the 3-trait model should be simplified and thoroughly tested to differentiate group influence from inherent network influence, or model influence. 

## Reflection 
What remains clear from these models is that a complicated model produces seemingly random results. With further investigation, network dynamics must be defined more simply in order to distinguish clear differences between group influence and inherent network influence. Moving forward, the 3-trait model should be more carefully assessed technically and mathematically to determine a consistent behavior. Though these models show interesting trial-run behaviors, simply re-running and re-setting does not prove any definitive behavior. 

