FROM microsoft/dotnet-nightly:2.0.0-beta-sdk

WORKDIR /dotnetapp

# copy csproj, NuGet.config, and restore as distinct layers
COPY *.csproj .
COPY 2.0.0-beta/NuGet.config .
RUN dotnet restore /p:TargetFramework=netcoreapp2.0 /p:RuntimeFrameworkVersion=2.0.0-beta-*

# copy and build everything else
COPY . .
RUN dotnet publish -c Release -o out /p:TargetFramework=netcoreapp2.0 /p:RuntimeFrameworkVersion=2.0.0-beta-*
