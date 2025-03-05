# About
Demonstration on passing parameters' reference to child process via FB_init method.
# The idea
TwinCAT normally initializes FBs in bottom-up order, meaning all children and base implementation's FB_inits will be called firstly. But, by explicitly passing reference of a parent FB (well, its proper interface according to child's FB_init signature) to the child FB_init method tricks initialization into reverse order. Parents get initialized (FB_init called) first, so that fully initialized instance is passed down to child elements. This means higher level's reference to parameters is available and may be requested from child's FB_init method. All parents must implement interface(s) to extract reference(s) to parameter(s) and when passed to children, reference to original parameters can be extracted.
> **Note** - If TwinCAT insisted in its normal initialization order, parameter's property getter would need to ask its parent's property getter for data, which would result in some overhead on data access.

> **Note2** - This sample may be used also to only force reverse (top-down) initialization order.
