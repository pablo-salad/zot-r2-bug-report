FROM busybox:1.36.1 as busybox

FROM ghcr.io/project-zot/zot-minimal-linux-amd64:v2.0.0

ARG R2_ID
ARG R2_BUCKET
ARG R2_ACCESS_KEY
ARG R2_SECRET_KEY
ARG S3_CHUNK_SIZE

COPY config.json /etc/zot/config.json

COPY --from=busybox /bin/sh /bin/sh
COPY --from=busybox /bin/sed /bin/sed

RUN sed -i "s|{R2_ID}|${R2_ID}|g" /etc/zot/config.json
RUN sed -i "s|{R2_BUCKET}|${R2_BUCKET}|g" /etc/zot/config.json
RUN sed -i "s|{R2_ACCESS_KEY}|${R2_ACCESS_KEY}|g" /etc/zot/config.json
RUN sed -i "s|{R2_SECRET_KEY}|${R2_SECRET_KEY}|g" /etc/zot/config.json
RUN sed -i "s|{S3_CHUNK_SIZE}|${S3_CHUNK_SIZE}|g" /etc/zot/config.json