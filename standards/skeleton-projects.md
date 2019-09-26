---
category: Skeleton Projects
---
# Skeleton Projects
Two basic skeleton projects are available and should be used as the starting point for any new services.
They are complete projects, with tests, jenkins files ready to be build and deployed. They use the technologies from the tech menu.

## Java
A basic springboot project is available here, this is intended for restful api's. To use this project copy it into a new repository. Then rename it, including package references (search and replace on *skeleton* case insensitive).
Then update the parameters in the jenkins file in the root of the project. The new project should then be added to the build and deployment server.

## Javascript
A basic express project is available here, this is intended for user facing services/websites. To use this project copy it into a new repository. Then rename it (search and replace on *skeleton* case insensitive).

## Updating the skeleton projects
When you go to use the skeleton project(s) for a new service check that they are still using the latest
stable versions of their frameworks and dependencies. If not then the skeleton projects should be updated first, and the tech menu updated to reflect the new versions.
