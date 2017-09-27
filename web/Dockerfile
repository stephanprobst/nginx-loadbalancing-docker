FROM microsoft/aspnetcore-build:2 AS builder
WORKDIR ./app
COPY web.csproj .
RUN dotnet restore
COPY *.* ./
RUN dotnet publish -c Release -o ./publish

FROM microsoft/aspnetcore:2
WORKDIR ./app
COPY --from=builder /app/publish/* ./
ENTRYPOINT [ "dotnet", "./web.dll" ]