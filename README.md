# About
Demonstration on passing parameters' reference to child process via instantiation method.
# The idea
is, that classes (FBs) instantiate top down, but all static variables are instantiated before any FB_init is called. So, the only thing, that exists at child variable instatiation time, is its parent. Parents must implement interface(s) to extract reference(s) to parameter(s) and when passed to children, reference to original parameters can be extracted.
