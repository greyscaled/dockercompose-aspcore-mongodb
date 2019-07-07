FROM mcr.microsoft.com/dotnet/core/aspnet:2.2-stretch-slim AS base
WORKDIR /app
EXPOSE 80
EXPOSE 443

FROM mcr.microsoft.com/dotnet/core/sdk:2.2-stretch AS build
WORKDIR /src
COPY ["MongoBooksApi/MongoBooksApi.csproj", "MongoBooksApi/"]
RUN dotnet restore "MongoBooksApi/MongoBooksApi.csproj"
COPY . .
WORKDIR "/src/MongoBooksApi"
RUN dotnet build "MongoBooksApi.csproj" -c Release -o /app

FROM build AS publish
RUN dotnet publish "MongoBooksApi.csproj" -c Release -o /app

FROM base AS final
WORKDIR /app
COPY --from=publish /app .
ENTRYPOINT ["dotnet", "MongoBooksApi.dll"]
