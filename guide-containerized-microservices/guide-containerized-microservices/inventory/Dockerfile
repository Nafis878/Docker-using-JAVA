FROM icr.io/appcafe/open-liberty:kernel-slim-java11-openj9-ubi

ARG VERSION=1.0
ARG REVISION=SNAPSHOT

LABEL   org.opencontainers.image.authors="Your Name"   org.opencontainers.image.vendor="Open Liberty"   org.opencontainers.image.url="local"   org.opencontainers.image.source="https://github.com/OpenLiberty/guide-containerize"   org.opencontainers.image.version="$VERSION"   org.opencontainers.image.revision="$REVISION"   vendor="Open Liberty"   name="inventory"   version="$VERSION-$REVISION"   summary="The inventory microservice from the Containerizing microservices guide"   description="This image contains the inventory microservice running with the Open Liberty runtime."

COPY --chown=1001:0 src/main/liberty/config /config/

RUN features.sh

COPY --chown=1001:0 target/guide-containerize-inventory.war /config/apps

RUN configure.sh
