# Purpose
Microsoft removed NodeJS from their .NET Core Docker images ([announcement](https://github.com/aspnet/Announcements/issues/298)). This image adds back NodeJS for build time with Webpack pre-installed.

# Ingredients
* Based on docker image [mcr.microsoft.com/dotnet/sdk](https://hub.docker.com/_/microsoft-dotnet-sdk/):8.0.404-alpine3.20
* [NodeJS](https://nodejs.org/) 24.21.0
* [Gulp](https://www.npmjs.com/package/gulp) 5.0.1
* [Gulp-cli](https://www.npmjs.com/package/gulp-cli) 3.1.0
* [TypeScript](https://www.npmjs.com/package/typescript) 5.9.3

# Full Tag Listing
## Linux amd64 tags
- [`8.0.425-bookworm-slim`, `8.0-sdk`, `latest` (*Dockerfile*)](https://github.com/Mathieu79FI/dotnet-docker/blob/master/8.0/sdk/bookworm-slim/gulp/Dockerfile)
- [`8.0.425-alpine`, `8.0-sdk-alpine` (*Dockerfile*)](https://github.com/Mathieu79FI/dotnet-docker/blob/master/8.0/sdk/alpine/gulp/Dockerfile)
