FROM mcr.microsoft.com/dotnet/sdk:8.0.416-alpine3.21 AS base

FROM base AS build
ENV NODE_VERSION=24.11.1
ENV NODE_DOWNLOAD_SHA=ad084dbec243b0645cbc3fd545fb588fa3c5bd7ff92a828eee38c03fb246aef2
RUN curl -SL "https://unofficial-builds.nodejs.org/download/release/v$NODE_VERSION/node-v$NODE_VERSION-linux-x64-musl.tar.gz" --output nodejs.tar.gz \
    && echo "$NODE_DOWNLOAD_SHA  nodejs.tar.gz" | sha256sum -c - \
    && tar -xzf "nodejs.tar.gz" -C /usr/local --strip-components=1 --no-same-owner \
    && ln -s /usr/local/bin/node /usr/local/bin/nodejs \
    && npm install --global webpack@5.103.0 webpack-cli@6.0.1 typescript@5.9.3 postcss@8.5.6 postcss-loader@8.2.0

FROM base AS final
COPY --from=build /usr/local/bin /usr/local/bin
COPY --from=build /usr/local/include /usr/local/include
COPY --from=build /usr/local/lib /usr/local/lib
COPY --from=build /usr/local/share /usr/local/share
COPY --from=build /root/.npm /root/.npm
