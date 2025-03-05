# About
Demonstration on passing parameters' reference to child process via instantiation method.
# The idea
TwinCAT normally initializes FBs in base-first order, meaning all children and base implementation FB_inits will be called before higher level. But, by explicitly passing reference of a parent FB to FB_init method of its child tricks initialization into reverse order. Parents get initialized (FB_init called) first, so that fully initialized instasnce is passed down to child elements. This means higher level's reference to parameters is available and may be requested from child's FB_init method. All parents must implement interface(s) to extract reference(s) to parameter(s) and when passed to children, reference to original parameters can be extracted.
> **Note** - If TwinCAT insisted in its normal initialization order, parameter's property getter would need to ask its parent's property getter for data, which would result in some overhead on data access.
