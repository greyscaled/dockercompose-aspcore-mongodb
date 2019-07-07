# dockercompose-aspcore-mongodb

## Overview

This repository is a rework of the tutorial titled ["Create a web API with ASP.NET Core and MongoDB"][1] from Microsoft's ASP.NET Core documentation.

## Outline of Differences

- Docker (via `docker-compose`) is used instead of local installations
- There is a seed script included so that the Mongo container can be initialized upon container start
- [Mongo Express][2] is added to view the Database through a browser
- A layered architecture is used

[1]: https://docs.microsoft.com/en-us/aspnet/core/tutorials/first-mongo-app?view=aspnetcore-2.2&tabs=visual-studio
[2]: https://hub.docker.com/_/mongo-express
