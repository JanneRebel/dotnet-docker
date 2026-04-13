FROM mcr.microsoft.com/dotnet/sdk:9.0.312-alpine3.23 AS base

FROM base AS build
ENV NODE_VERSION=24.14.1
ENV NODE_DOWNLOAD_SHA=4cdc6bf5891d1f51903c663b2f7f6a636c24dd5940a62a1785ea3d911284b008
RUN curl -SL "https://unofficial-builds.nodejs.org/download/release/v$NODE_VERSION/node-v$NODE_VERSION-linux-x64-musl.tar.gz" --output nodejs.tar.gz \
    && echo "$NODE_DOWNLOAD_SHA  nodejs.tar.gz" | sha256sum -c - \
    && tar -xzf "nodejs.tar.gz" -C /usr/local --strip-components=1 --no-same-owner \
    && ln -s /usr/local/bin/node /usr/local/bin/nodejs \
    && npm install --global webpack@5.106.1 webpack-cli@6.0.1 typescript@5.9.3 postcss@8.5.9 postcss-loader@8.2.1

FROM base AS final
COPY --from=build /usr/local/bin /usr/local/bin
COPY --from=build /usr/local/include /usr/local/include
COPY --from=build /usr/local/lib /usr/local/lib
COPY --from=build /usr/local/share /usr/local/share
COPY --from=build /root/.npm /root/.npm
