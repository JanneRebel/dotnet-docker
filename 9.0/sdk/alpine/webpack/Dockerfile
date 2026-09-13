FROM mcr.microsoft.com/dotnet/sdk:9.0.318-alpine3.23 AS base

FROM base AS build
ENV NODE_VERSION=24.21.0
ENV NODE_DOWNLOAD_SHA=01a713e34da98e7b4d2a3191ee7ca3f93dd0384d1a2ef23c379b2161ee6e133a
RUN curl -SL "https://unofficial-builds.nodejs.org/download/release/v$NODE_VERSION/node-v$NODE_VERSION-linux-x64-musl.tar.gz" --output nodejs.tar.gz \
    && echo "$NODE_DOWNLOAD_SHA  nodejs.tar.gz" | sha256sum -c - \
    && tar -xzf "nodejs.tar.gz" -C /usr/local --strip-components=1 --no-same-owner \
    && ln -s /usr/local/bin/node /usr/local/bin/nodejs \
    && npm install --global webpack@5.110.3 webpack-cli@7.2.3 typescript@5.9.3 postcss@8.5.28 postcss-loader@8.2.1

FROM base AS final
COPY --from=build /usr/local/bin /usr/local/bin
COPY --from=build /usr/local/include /usr/local/include
COPY --from=build /usr/local/lib /usr/local/lib
COPY --from=build /usr/local/share /usr/local/share
COPY --from=build /root/.npm /root/.npm
