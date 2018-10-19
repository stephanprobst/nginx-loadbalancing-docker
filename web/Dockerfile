FROM microsoft/dotnet:2.1-sdk AS builder
WORKDIR /src
COPY web.csproj .
RUN dotnet restore
COPY . .
RUN dotnet publish -c Release -o /publish

FROM microsoft/dotnet:2.1-aspnetcore-runtime
WORKDIR /app
COPY --from=builder /publish .
ENTRYPOINT [ "dotnet", "./web.dll" ]