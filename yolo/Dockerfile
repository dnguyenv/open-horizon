ARG BUILD_FROM=dcmartin/amd64_base-ubuntu:0.0.2

FROM $BUILD_FROM as darknet

ARG BUILD_ARCH=amd64

# Environment variables
ENV \
    HOME="/root" \
    LANG="C.UTF-8" \
    PS1="$(whoami)@$(hostname):$(pwd)$ " \
    TERM="xterm"

RUN apt-get update && apt-get install -q -y --no-install-recommends \
  ca-certificates \
  curl \
  build-essential \
  socat \
  imagemagick \
  fswebcam \
  jq \
  git

# configure darknet
ARG DARKNET=/darknet
ARG DARKNET_GIT="http://github.com/pjreddie/darknet"
ENV DARKNET=${DARKNET} DARKNET_GIT=${DARKNET_GIT}

ENV DARKNET_TINYV2_WEIGHTS="${DARKNET}/yolov2-tiny-voc.weights"
ENV DARKNET_TINYV2_CONFIG="${DARKNET}/cfg/yolov2-tiny-voc.cfg"
ENV DARKNET_TINYV2_DATA="${DARKNET}/cfg/voc.data"
ENV DARKNET_TINYV2_WEIGHTS_URL="http://pjreddie.com/media/files/yolov2-tiny-voc.weights"

ENV DARKNET_TINYV3_WEIGHTS="${DARKNET}/yolov3-tiny.weights"
ENV DARKNET_TINYV3_CONFIG="${DARKNET}/cfg/yolov3-tiny.cfg"
ENV DARKNET_TINYV3_DATA="${DARKNET}/cfg/codo.data"
ENV DARKNET_TINYV3_WEIGHTS_URL="http://pjreddie.com/media/files/yolov3-tiny.weights"

ENV DARKNET_V2_WEIGHTS="${DARKNET}/yolov2.weights"
ENV DARKNET_V2_CONFIG="${DARKNET}/cfg/yolov2.cfg"
ENV DARKNET_V2_DATA="${DARKNET}/cfg/coco.data"
ENV DARKNET_V2_WEIGHTS_URL="https://pjreddie.com/media/files/yolov2.weights"

ENV DARKNET_V3_WEIGHTS="${DARKNET}/yolov3.weights"
ENV DARKNET_V3_CONFIG="${DARKNET}/cfg/yolov3.cfg"
ENV DARKNET_V3_DATA="${DARKNET}/cfg/coco.data"
ENV DARKNET_V3_WEIGHTS_URL="https://pjreddie.com/media/files/yolov3.weights"

# Clone darknet
RUN mkdir -p ${DARKNET} 
RUN cd ${DARKNET} && git clone ${DARKNET_GIT} .

# Build darknet
RUN \
    cd ${DARKNET} \
    \
    && make

FROM darknet

# Copy compiled darknet
COPY --from=darknet /darknet /darknet

# Copy usr
COPY rootfs/usr /usr

CMD [ "/usr/bin/run.sh" ]

# Build arguments
ARG BUILD_DATE
ARG BUILD_REF
ARG BUILD_VERSION

# Labels
LABEL \
    org.label-schema.schema-version="1.0" \
    org.label-schema.build-date="${BUILD_DATE}" \
    org.label-schema.build-arch="${BUILD_ARCH}" \
    org.label-schema.name="yolo" \
    org.label-schema.description="yolo/darknet as a service" \
    org.label-schema.vcs-url="http://github.com/dcmartin/open-horizon/master/yolo/" \
    org.label-schema.vcs-ref="${BUILD_REF}" \
    org.label-schema.version="${BUILD_VERSION}" \
    org.label-schema.vendor="David C Martin <github@dcmartin.com>"
