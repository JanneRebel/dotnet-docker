FROM mcr.microsoft.com/dotnet/sdk:10.0.301-alpine3.23 AS base

FROM base AS build
ENV NODE_VERSION=24.16.0
ENV NODE_DOWNLOAD_SHA=50df5d8d474892d4f7b906167df36f77f5b93908f63dc532dc568219cab65841
RUN curl -SL "https://unofficial-builds.nodejs.org/download/release/v$NODE_VERSION/node-v$NODE_VERSION-linux-x64-musl.tar.gz" --output nodejs.tar.gz \
    && echo "$NODE_DOWNLOAD_SHA  nodejs.tar.gz" | sha256sum -c - \
    && tar -xzf "nodejs.tar.gz" -C /usr/local --strip-components=1 --no-same-owner \
    && ln -s /usr/local/bin/node /usr/local/bin/nodejs \
    && npm install --global webpack@5.107.2 webpack-cli@7.0.3 typescript@5.9.3 postcss@8.5.15 postcss-loader@8.2.1

FROM base AS final
COPY --from=build /usr/local/bin /usr/local/bin
COPY --from=build /usr/local/include /usr/local/include
COPY --from=build /usr/local/lib /usr/local/lib
COPY --from=build /usr/local/share /usr/local/share
COPY --from=build /root/.npm /root/.npm
