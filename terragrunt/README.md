# Terragrunt

Docker image containing Terragrunt with Terraform for legacy codebases.

## Image

```
docker pull corebug/terragrunt:v0.75.0
```

## Contents

- Terraform 1.10.0
- Terragrunt 0.75.0
- Git, curl, ca-certificates

## Usage

```bash
docker run --rm -v $(pwd):/app -w /app corebug/terragrunt plan
```

With AWS credentials:

```bash
docker run --rm \
  --name terragrunt \
  -v $(pwd):/code \
  -w /code \
  -v ~/.aws:/home/tguser/.aws \
  -e AWS_PROFILE=YOUR_PROFILE \
  corebug/terragrunt plan
```

## Building locally

```bash
docker build -t corebug/terragrunt:v0.75.0 .
```
