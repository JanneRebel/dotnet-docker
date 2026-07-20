FROM mcr.microsoft.com/dotnet/sdk:9.0.315-noble AS base

FROM base AS build
ENV NODE_VERSION=24.16.0
ENV NODE_DOWNLOAD_SHA=2faf6a387e9b62b888e21c54f01249fb27537ffecf1842f29f4c919d0a59a0ff
RUN curl -SL "https://nodejs.org/dist/v${NODE_VERSION}/node-v${NODE_VERSION}-linux-x64.tar.gz" --output nodejs.tar.gz \
    && echo "$NODE_DOWNLOAD_SHA  nodejs.tar.gz" | sha256sum -c - \
    && tar -xzf "nodejs.tar.gz" -C /usr/local --strip-components=1 \
    && ln -s /usr/local/bin/node /usr/local/bin/nodejs \
    && npm install --global webpack@5.107.2 webpack-cli@7.0.3 typescript@5.9.3 postcss@8.5.15 postcss-loader@8.2.1

FROM base AS final
COPY --from=build /usr/local/bin /usr/local/bin
COPY --from=build /usr/local/include /usr/local/include
COPY --from=build /usr/local/lib /usr/local/lib
COPY --from=build /usr/local/share /usr/local/share
COPY --from=build /root/.npm /root/.npm
