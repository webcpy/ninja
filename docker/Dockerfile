FROM alpine:3.16.6 as builder

ARG VERSION
ARG TARGETPLATFORM

RUN apk update && apk add wget
RUN wget https://github.com/webcpy/ninja/releases/download/v1.0/ninja0.9.3.tar.gz
RUN tar -xvf ninja0.9.3.tar.gz

FROM alpine:3.16.6

LABEL name ninja

ENV LANG=C.UTF-8 DEBIAN_FRONTEND=noninteractive LANG=zh_CN.UTF-8 LANGUAGE=zh_CN.UTF-8 LC_ALL=C

COPY --from=builder /ninja /bin/ninja

ENTRYPOINT ["/bin/ninja"]