FROM mcr.microsoft.com/dotnet/aspnet:8.0 AS base
WORKDIR /app
EXPOSE 8080


ENV ASPNETCORE_URLS=http://+:8080
ENV ASPNETCORE_ENVIRONMENT=Production


COPY . .


LABEL maintainer="1051690@hr.nl"
LABEL version="1.0"
LABEL description="ASP.NET Core REST service for CDDB"


ENTRYPOINT ["dotnet", "Quintor.dll"]