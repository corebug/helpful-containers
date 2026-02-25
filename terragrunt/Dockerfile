FROM hashicorp/terraform:1.10.0

RUN apk add --no-cache git ca-certificates curl && curl -Ls -o /usr/local/bin/terragrunt \
            https://github.com/gruntwork-io/terragrunt/releases/download/v0.75.0/terragrunt_linux_amd64 && \
            chmod +x /usr/local/bin/terragrunt

RUN addgroup tguser && adduser -D tguser -G tguser && mkdir /code && chown tguser /code

WORKDIR /code
USER tguser

ENTRYPOINT ["/usr/local/bin/terragrunt"]
