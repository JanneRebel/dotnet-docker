FROM mcr.microsoft.com/dotnet/sdk:8.0.416-bookworm-slim AS base

FROM base AS build
ENV NODE_VERSION=24.11.1
ENV NODE_DOWNLOAD_SHA=58a5ff5cc8f2200e458bea22e329d5c1994aa1b111d499ca46ec2411d58239ca
RUN curl -SL "https://nodejs.org/dist/v${NODE_VERSION}/node-v${NODE_VERSION}-linux-x64.tar.gz" --output nodejs.tar.gz \
    && echo "$NODE_DOWNLOAD_SHA  nodejs.tar.gz" | sha256sum -c - \
    && tar -xzf "nodejs.tar.gz" -C /usr/local --strip-components=1 \
    && ln -s /usr/local/bin/node /usr/local/bin/nodejs \
    && npm install --global webpack@5.103.0 webpack-cli@6.0.1 typescript@5.9.3 postcss@8.5.6 postcss-loader@8.2.0

FROM base AS final
COPY --from=build /usr/local/bin /usr/local/bin
COPY --from=build /usr/local/include /usr/local/include
COPY --from=build /usr/local/lib /usr/local/lib
COPY --from=build /usr/local/share /usr/local/share
COPY --from=build /root/.npm /root/.npm
