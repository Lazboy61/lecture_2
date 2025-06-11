# Runtime-only image (geen SDK nodig)
FROM mcr.microsoft.com/dotnet/aspnet:8.0
WORKDIR /app

# Kopieer de hele inhoud (alle .dll en .json bestanden)
COPY . . 

EXPOSE 8080
LABEL maintainer="1051690@hr.nl"

ENTRYPOINT ["dotnet", "Album.Api.dll"]
