  
FROM mcr.microsoft.com/dotnet/core/sdk:2.2 AS build
WORKDIR /app

# copy proj files needed for package restore
COPY . .

# restore packages
RUN dotnet restore

# copy everything else
COPY . .

# build app
WORKDIR /app/WebApp/
RUN dotnet publish -c Release -o out

# runtime stage
FROM mcr.microsoft.com/dotnet/core/aspnet:2.2 AS runtime
WORKDIR /app
COPY --from=build /app/WebApp/out ./
RUN ls

ENTRYPOINT ["dotnet", "WebApp.dll"]