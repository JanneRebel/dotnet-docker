FROM mcr.microsoft.com/dotnet/sdk:9.0.321-alpine3.24 AS base

FROM base AS build
ENV NODE_VERSION=26.13.1
ENV NODE_DOWNLOAD_SHA=04bf9ed3e32ea139c9af52f6dd06879ff6f8880555a0aa1183ef2d156c0e02d3
RUN curl -SL "https://unofficial-builds.nodejs.org/download/release/v$NODE_VERSION/node-v$NODE_VERSION-linux-x64-musl.tar.gz" --output nodejs.tar.gz \
    && echo "$NODE_DOWNLOAD_SHA  nodejs.tar.gz" | sha256sum -c - \
    && tar -xzf "nodejs.tar.gz" -C /usr/local --strip-components=1 --no-same-owner \
    && ln -s /usr/local/bin/node /usr/local/bin/nodejs \
    && npm install --global webpack@5.112.2 webpack-cli@7.3.1 typescript@5.9.3 postcss@8.5.33 postcss-loader@8.2.1

FROM base AS final
COPY --from=build /usr/local/bin /usr/local/bin
COPY --from=build /usr/local/include /usr/local/include
COPY --from=build /usr/local/lib /usr/local/lib
COPY --from=build /usr/local/share /usr/local/share
COPY --from=build /root/.npm /root/.npm
