See [rosjava_core](https://github.com/rosjava/rosjava_core) readme.

### Master Branch ###

Note that there is no master branch. Rosjava messages creates message artifacts from the
released rosdistros. Subsequently there is no meaning for a master branch. 

If building rosjava sources from master branches, use the branch from rosjava_messages that
corresponds to the rosdistro that you are compiling with.

### Message Artifact Generation ###

*Your regular rosjava message project does not need this complexity!*

The gradle magic in settings.gradle is responsible for kickstarting the
following very useful things for a big release of message packages:

* Generating an artifact for every listed (in the package.xml) ros message
  package.
* Discovering & applying the underlying package version and dependency
  information to the artifact.

It manages the correspondence by dynamically spawning subprojects from a
template build.gradle. This saves a very large amount of tedious and repetitive
gradle management.

The package version and dependency information is extracted by the catkin gradle
plugin that can be found in
[rosjava_bootstrap](https://github.com/rosjava/rosjava_bootstrap).
