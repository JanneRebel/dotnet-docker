# Purpose
Microsoft removed NodeJS from their .NET Core Docker images ([announcement](https://github.com/aspnet/Announcements/issues/298)). This image adds back NodeJS for build time with Webpack pre-installed.

# Ingredients
* Based on docker image [mcr.microsoft.com/dotnet/sdk](https://hub.docker.com/_/microsoft-dotnet-sdk/):11.0.100-resolute
* [NodeJS](https://nodejs.org/) 26.13.1
* [Webpack](https://www.npmjs.com/package/webpack) 5.112.2
* [Webpack-cli](https://www.npmjs.com/package/webpack-cli) 7.3.1
* [TypeScript](https://www.npmjs.com/package/typescript) 5.9.3
* [PostCSS](https://www.npmjs.com/package/postcss) 8.5.33
* [postcss-loader](https://www.npmjs.com/package/postcss-loader) 8.2.1

# Full Tag Listing
## Linux amd64 tags
- [`8.0.428-bookworm-slim`, `8.0-sdk` (*Dockerfile*)](https://github.com/JanneRebel/dotnet-docker/blob/master/8.0/sdk/bookworm-slim/webpack/Dockerfile)
- [`8.0.428-alpine`, `8.0-sdk-alpine` (*Dockerfile*)](https://github.com/JanneRebel/dotnet-docker/blob/master/8.0/sdk/alpine/webpack/Dockerfile)
- [`9.0.321-bookworm-slim`, `9.0-sdk` (*Dockerfile*)](https://github.com/JanneRebel/dotnet-docker/blob/master/9.0/sdk/bookworm-slim/webpack/Dockerfile)
- [`9.0.321-noble` (*Dockerfile*)](https://github.com/JanneRebel/dotnet-docker/blob/master/9.0/sdk/noble/webpack/Dockerfile)
- [`9.0.321-alpine`, `9.0-sdk-alpine` (*Dockerfile*)](https://github.com/JanneRebel/dotnet-docker/blob/master/9.0/sdk/alpine/webpack/Dockerfile)
- [`10.0.404-noble`, `10.0-sdk`, `latest` (*Dockerfile*)](https://github.com/JanneRebel/dotnet-docker/blob/master/10.0/sdk/noble/webpack/Dockerfile)
- [`10.0.404-alpine`, `10.0-sdk-alpine` (*Dockerfile*)](https://github.com/JanneRebel/dotnet-docker/blob/master/10.0/sdk/alpine/webpack/Dockerfile)
- [`11.0.100-resolute`, `11.0-sdk` (*Dockerfile*)](https://github.com/JanneRebel/dotnet-docker/blob/master/11.0/sdk/resolute/webpack/Dockerfile)
- [`11.0.100-alpine`, `11.0-sdk-alpine` (*Dockerfile*)](https://github.com/JanneRebel/dotnet-docker/blob/master/11.0/sdk/alpine/webpack/Dockerfile)
