FROM microsoft/dotnet:1.1.0-sdk-msbuild-rc4

WORKDIR /dotnetapp

# copy csproj and restore as distinct layers
COPY *.csproj .
RUN dotnet restore /p:TargetFramework=netcoreapp1.1 /p:RuntimeFrameworkVersion=1.1.0

# copy and build everything else
COPY . .
RUN dotnet publish -c Release -o out /p:TargetFramework=netcoreapp1.1 /p:RuntimeFrameworkVersion=1.1.0
