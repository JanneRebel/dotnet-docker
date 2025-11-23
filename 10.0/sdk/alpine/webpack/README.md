# Purpose
Microsoft removed NodeJS from their .NET Core Docker images ([announcement](https://github.com/aspnet/Announcements/issues/298)). This image adds back NodeJS for build time with Webpack pre-installed.

# Ingredients
* Based on docker image [mcr.microsoft.com/dotnet/sdk](https://hub.docker.com/_/microsoft-dotnet-sdk/):10.0.100-alpine3.22
* [NodeJS](https://nodejs.org/) 24.11.1
* [Webpack](https://www.npmjs.com/package/webpack) 5.103.0
* [Webpack-cli](https://www.npmjs.com/package/webpack-cli) 6.0.1
* [TypeScript](https://www.npmjs.com/package/typescript) 5.9.3
* [PostCSS](https://www.npmjs.com/package/postcss) 8.5.6
* [postcss-loader](https://www.npmjs.com/package/postcss-loader) 8.2.0

# Full Tag Listing
## Linux amd64 tags
- [`8.0.416-bookworm-slim`, `8.0-sdk` (*Dockerfile*)](https://github.com/JanneRebel/dotnet-docker/blob/master/8.0/sdk/bookworm-slim/webpack/Dockerfile)
- [`8.0.416-alpine`, `8.0-sdk-alpine` (*Dockerfile*)](https://github.com/JanneRebel/dotnet-docker/blob/master/8.0/sdk/alpine/webpack/Dockerfile)
- [`9.0.308-bookworm-slim`, `9.0-sdk` (*Dockerfile*)](https://github.com/JanneRebel/dotnet-docker/blob/master/9.0/sdk/bookworm-slim/webpack/Dockerfile)
- [`9.0.308-alpine`, `9.0-sdk-alpine` (*Dockerfile*)](https://github.com/JanneRebel/dotnet-docker/blob/master/9.0/sdk/alpine/webpack/Dockerfile)
- [`10.0.100-noble`, `10.0-sdk`, `latest` (*Dockerfile*)](https://github.com/JanneRebel/dotnet-docker/blob/master/10.0/sdk/noble/webpack/Dockerfile)
- [`10.0.100-alpine`, `10.0-sdk-alpine` (*Dockerfile*)](https://github.com/JanneRebel/dotnet-docker/blob/master/10.0/sdk/alpine/webpack/Dockerfile)
