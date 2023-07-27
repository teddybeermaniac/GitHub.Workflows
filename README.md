# GitHub.Workflows
A collection of reusable GitHub workflows.

## Examples
The directories with workflow name contain usage examples.

## caprover-deploy-dockerfile.yml
Builds a Dockerfile, pushes the image to ghcr.io, and deploys it to the specified CapRover instance. Uses [docker-build-image.yml](#docker-build-imageyml) and [caprover-deploy-image.yml](#caprover-deploy-imageyml)

### Inputs
|Name|Required|Default|Description|
|-|-|-|-|
|context||.|Path to Docker context|
|file||`{context}/Dockerfile`|Path to Dockerfile|
|platforms||amd64|Platforms to build image for|
|authors|✅||Author contact information|
|application|✅||Application name|

### Secrets
|Name|Required|Description|
|-|-|-|
|host|✅|CapRover instance URL|
|token|✅|Application token|
|header_name||Additional header name|
|header_value||Additional header value|

## caprover-deploy-image.yml
Deploys a Docker image to the specified CapRover instance.

### Inputs
|Name|Required|Default|Description|
|-|-|-|-|
|image|✅||Image to deploy|
|application|✅||Application name|

### Secrets
|Name|Required|Description|
|-|-|-|
|host|✅|CapRover instance URL|
|token|✅|Application token|
|header_name||Additional header name|
|header_value||Additional header value|

## docker-build-image.yml
Builds a Dockerfile and pushes the image to ghcr.io.

### Inputs
|Name|Required|Default|Description|
|-|-|-|-|
|context||.|Path to Docker context|
|file||`{context}/Dockerfile`|Path to Dockerfile|
|platforms||amd64,arm64|Platforms to build image for|
|authors|✅||Author contact information|
|image_name||`lowercase repository name`|Image name|

### Outputs
|Name|Description|
|-|-|
|image|Image tag|
