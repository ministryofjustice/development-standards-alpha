---
category: Builds
---
# Build Artifacts
## Docker Images
 - Each build should produce a docker image, which is self contained (holds everything that is required for the application it contains to run) and publish this to the registry.
 - Any parameters that are required by the contained application should be passed as environment variables.
 - The tag of each docker image produced should contain the build number that produced it to allow for traceability.

The standard pipeline will take care of these requirements automatically, once the correct parameters are set.

Branch builds also follow this pattern however the images are not retained after a successful build.
