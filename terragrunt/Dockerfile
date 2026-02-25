FROM hashicorp/terraform:1.10.0

RUN apk add --no-cache git ca-certificates curl && curl -Ls -o /usr/local/bin/terragrunt \
            https://github.com/gruntwork-io/terragrunt/releases/download/v0.75.0/terragrunt_linux_amd64 && \
            chmod +x /usr/local/bin/terragrunt

ENTRYPOINT /usr/local/bin/terragrunt