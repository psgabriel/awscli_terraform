FROM alpine:3.7
LABEL maintainer="Percis Gabriel<psgabriel@gmail.com>"

ENV TERRAFORM_VERSION=0.11.11

RUN apk add --update curl zip && \
    curl -sSL https://releases.hashicorp.com/terraform/${TERRAFORM_VERSION}/terraform_${TERRAFORM_VERSION}_linux_amd64.zip -o /tmp/terraform.zip && \
    unzip /tmp/terraform.zip -d /usr/bin && \
    rm /tmp/terraform.zip && \
    #apk del curl zip && \
    rm -rf /var/cache/apk/*

ENTRYPOINT ["/usr/bin/terraform"]
CMD []