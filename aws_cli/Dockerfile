FROM alpine:3.7
LABEL maintainer="Percis Gabriel<psgabriel@gmail.com>"

RUN ln -sf /usr/share/zoneinfo/Etc/UTC /etc/localtime

RUN apk update
RUN apk add --no-cache --virtual .build-deps && \
    apk add bash && \
    apk add make && \
    apk add curl && \
    apk add openssh && \
    apk add git

RUN apk -Uuv add groff less python py-pip
RUN pip install awscli
RUN apk --purge -v del py-pip
RUN rm /var/cache/apk/*

ENTRYPOINT ["/usr/bin/aws"]
CMD []