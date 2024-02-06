FROM mcr.microsoft.com/devcontainers/base:bullseye

# TODO: use a more recent version of java
# TODO: make sure the build images use the same version
ARG OPEN_JDK_VERSION=17
RUN --mount=target=/var/lib/apt/lists,type=cache,sharing=locked \
    --mount=target=/var/cache/apt,type=cache,sharing=locked \
    apt update \
 && apt install --assume-yes git openjdk-${OPEN_JDK_VERSION}-jre-headless
