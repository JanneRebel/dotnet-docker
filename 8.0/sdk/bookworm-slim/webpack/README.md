# Purpose
Microsoft removed NodeJS from their .NET Core Docker images ([announcement](https://github.com/aspnet/Announcements/issues/298)). This image adds back NodeJS for build time with Webpack pre-installed.

# Ingredients
* Based on docker image [mcr.microsoft.com/dotnet/sdk](https://hub.docker.com/_/microsoft-dotnet-sdk/):8.0.425-bookworm-slim
* [NodeJS](https://nodejs.org/) 24.21.0
* [Webpack](https://www.npmjs.com/package/webpack) 5.110.3
* [Webpack-cli](https://www.npmjs.com/package/webpack-cli) 7.2.3
* [TypeScript](https://www.npmjs.com/package/typescript) 5.9.3
* [PostCSS](https://www.npmjs.com/package/postcss) 8.5.28
* [postcss-loader](https://www.npmjs.com/package/postcss-loader) 8.2.1

# Full Tag Listing
## Linux amd64 tags
- [`8.0.425-bookworm-slim`, `8.0-sdk` (*Dockerfile*)](https://github.com/JanneRebel/dotnet-docker/blob/master/8.0/sdk/bookworm-slim/webpack/Dockerfile)
- [`8.0.425-alpine`, `8.0-sdk-alpine` (*Dockerfile*)](https://github.com/JanneRebel/dotnet-docker/blob/master/8.0/sdk/alpine/webpack/Dockerfile)
