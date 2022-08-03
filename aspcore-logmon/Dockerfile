FROM mcr.microsoft.com/dotnet/sdk:6.0 AS build-env
WORKDIR /app

COPY aspnetcoreapp/*.csproj ./
RUN dotnet restore

COPY aspnetcoreapp ./
RUN dotnet publish -c Release -o out

FROM mcr.microsoft.com/dotnet/aspnet:6.0
WORKDIR /app
COPY --from=build-env /app/out .
# copy the LogMinitor.exe and LogMonitorConfig.json to C:\LogMonitor
COPY LogMonitor/ /LogMonitor
ENTRYPOINT ["C:\\LogMonitor\\LogMonitor.exe", "dotnet", "aspnetcoreapp.dll"]
