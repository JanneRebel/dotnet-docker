FROM mcr.microsoft.com/dotnet/sdk:9.0.312-bookworm-slim AS base

FROM base AS build
ENV NODE_VERSION=24.14.1
ENV NODE_DOWNLOAD_SHA=ace9fa104992ed0829642629c46ca7bd7fd6e76278cb96c958c4b387d29658ea
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
