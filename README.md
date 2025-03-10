# About
Demonstration on passing parameters' reference to child process via FB_init method.
# The idea
FB_init happens after initialization of all static fields. Because that happens before any fb_init call, the parameter, given in declaration line for the child element, must also be initialized before any fb_init call. And the only thing, that is not global or static, is reference to THIS. Convincing THIS to caugh up its parameters was done using interface.

> **Note** - TwinCAT normally initializes FBs in top-down order, parents first. If it would be bottom-up, parameter's property getter would need to ask its parent's property getter for data, which would result in some overhead on data access, because request would bubble up to the upmost declaration.
