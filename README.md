# Helpful Containers
[![Build](https://github.com/corebug/helpful-containers/workflows/Build/badge.svg)](https://github.com/corebug/helpful-containers/actions?query=workflow%3ABuild)

A collection of useful Docker images for development and CI/CD workflows.

## Images

| Image                      | Description                                    |
|----------------------------|------------------------------------------------|
| [terragrunt](./terragrunt) | Terragrunt with Terraform for legacy codebases |
| -------                    | -------------                                  |

## Usage

All images are available on Docker Hub under the `corebug` namespace:

```bash
docker pull corebug/<image-name>:<version>
```

## Adding a new image
1. Create a new branch/fork
2. Create a new directory with a `Dockerfile`
3. Add a `values.yaml` with version and labels:

```yaml
version: "1.0.0"

labels:
  org.opencontainers.image.source: "https://github.com/corebug/helpful-containers"
  org.opencontainers.image.description: "Your image description"
```
4. Create a pull request to the main branch

## CI/CD

Images are automatically built and pushed to Docker Hub on every push to the `main` branch. The workflow:

- Detects all directories containing a `Dockerfile`
- Reads version and labels from `values.yaml`
- Builds and pushes with version tag and `latest`
