FROM mcr.microsoft.com/dotnet/sdk:9.0.313-bookworm-slim AS base

FROM base AS build
ENV NODE_VERSION=24.15.0
ENV NODE_DOWNLOAD_SHA=44836872d9aec49f1e6b52a9a922872db9a2b02d235a616a5681b6a85fec8d89
RUN curl -SL "https://nodejs.org/dist/v${NODE_VERSION}/node-v${NODE_VERSION}-linux-x64.tar.gz" --output nodejs.tar.gz \
    && echo "$NODE_DOWNLOAD_SHA  nodejs.tar.gz" | sha256sum -c - \
    && tar -xzf "nodejs.tar.gz" -C /usr/local --strip-components=1 \
    && ln -s /usr/local/bin/node /usr/local/bin/nodejs \
    && npm install --global webpack@5.106.1 webpack-cli@6.0.1 typescript@5.9.3 postcss@8.5.9 postcss-loader@8.2.1

FROM base AS final
COPY --from=build /usr/local/bin /usr/local/bin
COPY --from=build /usr/local/include /usr/local/include
COPY --from=build /usr/local/lib /usr/local/lib
COPY --from=build /usr/local/share /usr/local/share
COPY --from=build /root/.npm /root/.npm
