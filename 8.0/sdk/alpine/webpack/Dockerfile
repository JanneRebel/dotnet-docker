FROM mcr.microsoft.com/dotnet/sdk:8.0.420-alpine3.23 AS base

FROM base AS build
ENV NODE_VERSION=24.15.0
ENV NODE_DOWNLOAD_SHA=f55af5bd489c5347b113ca6594cae00a54b30ba57ac5875324311bfc6f4762e3
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
