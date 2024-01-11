# Q-Learning

Q-Learning poses an idea of assessing the quality of an action that is taken to move to a state rather than determining the possible value of the state (value footprint) being moved to.  

Unlike **policy gradient** methods, which attempt to learn functions which directly map an observation to an action, **Q-Learning** attempts to learn the value of being in a given state, and taking a specific action there. While both approaches ultimately allow us to take intelligent actions given a situation, **the means of getting to that action differ significantly**.