FROM mcr.microsoft.com/dotnet/sdk:8.0 AS build
WORKDIR /app
COPY . ./

RUN dotnet tool install --global dotnet-ef

ENV PATH="$PATH:/root/.dotnet/tools"

RUN dotnet restore
RUN dotnet build -c Release --no-restore

RUN dotnet publish -c Release -o out --no-restore

FROM mcr.microsoft.com/dotnet/aspnet:8.0
WORKDIR /app

COPY --from=build /app/out ./

ENV PATH="$PATH:/root/.dotnet/tools"

RUN dotnet tool install --global dotnet-ef
LABEL maintainer="1051690@hr.nl"
EXPOSE 8080

ENTRYPOINT ["sh", "-c", "dotnet ef database update && dotnet Album.Api.dll"]
