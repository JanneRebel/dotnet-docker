FROM mcr.microsoft.com/dotnet/core/sdk:3.1.426-buster AS base

FROM base AS build
ENV NODE_VERSION 16.13.0
ENV NODE_DOWNLOAD_SHA 589b7e7eb22f8358797a2c14a0bd865459d0b44458b8f05d2721294dacc7f734
RUN curl -SL "https://nodejs.org/dist/v${NODE_VERSION}/node-v${NODE_VERSION}-linux-x64.tar.gz" --output nodejs.tar.gz \
    && echo "$NODE_DOWNLOAD_SHA  nodejs.tar.gz" | sha256sum -c - \
    && tar -xzf "nodejs.tar.gz" -C /usr/local --strip-components=1 \
    && ln -s /usr/local/bin/node /usr/local/bin/nodejs \
    && npm install --global gulp-cli@2.3.0

FROM base AS final
COPY --from=build /usr/local/bin /usr/local/bin
COPY --from=build /usr/local/include /usr/local/include
COPY --from=build /usr/local/lib /usr/local/lib
COPY --from=build /usr/local/share /usr/local/share
COPY --from=build /root/.npm /root/.npm
