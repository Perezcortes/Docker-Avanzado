### 1. Escanear una imagen usando Trivy
```bash
# Escanear una imagen con Trivy para vulnerabilidades
trivy image my-image:latest
```

### 2. Dockerfile Multi-stage
```dockerfile
# Etapa 1: Construir la aplicación
FROM node:14 AS build
WORKDIR /app
COPY . .
RUN npm install
RUN npm run build

# Etapa 2: Imagen final sin herramientas de construcción
FROM node:14-slim
WORKDIR /app
COPY --from=build /app/dist /app
CMD ["npm", "start"]
```

### 3. Dockerfile con imagen Distroless
```dockerfile
FROM gcr.io/distroless/nodejs:14
WORKDIR /app
COPY . .
CMD ["server.js"]
```

### 4. Habilitar `containerd` en Docker Desktop
No hay un código específico para habilitar `containerd`, ya que se hace a través de la configuración de Docker Desktop. Asegúrate de habilitarlo en la interfaz de Docker Desktop, reiniciando el motor de Docker después.

### 5. Usar `--no-cache` en la construcción de una imagen Docker
```bash
# Construir una imagen sin utilizar caché
docker build --no-cache -t my-image .
```

### 6. Cambiar a una imagen base más ligera como Alpine
```dockerfile
FROM node:14-alpine
WORKDIR /app
COPY . .
RUN npm install
CMD ["npm", "start"]
```

### 7. Dockerfile eficiente para un proyecto de .NET
```dockerfile
FROM mcr.microsoft.com/dotnet/aspnet:5.0-alpine AS base
WORKDIR /app
EXPOSE 80
EXPOSE 443

FROM mcr.microsoft.com/dotnet/sdk:5.0 AS build
WORKDIR /src
COPY ["MyApp/MyApp.csproj", "MyApp/"]
RUN dotnet restore "MyApp/MyApp.csproj"
COPY . .
WORKDIR "/src/MyApp"
RUN dotnet build "MyApp.csproj" -c Release -o /app/build

FROM build AS publish
RUN dotnet publish "MyApp.csproj" -c Release -o /app/publish

FROM base AS final
WORKDIR /app
COPY --from=publish /app/publish .
ENTRYPOINT ["dotnet", "MyApp.dll"]
```

### 8. Usar la imagen `Alpine` para reducir el tamaño
```dockerfile
FROM alpine:latest
RUN apk add --no-cache curl
CMD ["curl", "https://example.com"]
```

### 9. Reducir el número de capas en un Dockerfile
```dockerfile
# Mejor práctica: fusionar RUN
RUN apt-get update && apt-get install -y curl && apt-get clean
```

### 10. Usar `.dockerignore` para omitir `node_modules`
```bash
# .dockerignore
node_modules
```

### 11. Archivo `docker-compose.yml` para definir una red `bridge`
```bash
docker network create --driver bridge my-bridge-network
```

### 12. Asignar puertos diferentes para evitar conflictos
```bash
docker run -d -p 8081:80 my-container
docker run -d -p 8082:80 my-other-container
```

### 13. Corregir la indentación en un archivo YAML
```yaml
# Correcto:
version: "3"
services:
  web:
    image: nginx

# Incorrecto:
version: "3"
  services:
    web:
      image: nginx
```

### 14. Ejecutar pruebas automáticas en un contenedor Docker remoto
```bash
docker run my-test-image:latest
```

### 15. Ejecutar `docker compose down` desde una ubicación diferente
No se requiere código adicional. Solo asegúrate de ejecutar `docker compose down` en el mismo directorio donde ejecutaste `docker compose up`.

### 16. Verificar los servicios y sus réplicas en Docker Swarm
```bash
docker service ls
```

### 17. Desplegar una aplicación de prueba localmente sin un orquestador
```bash
# Simplemente usa `docker run` para ejecutar contenedores sin orquestadores
docker run -d -p 80:80 my-container
```

### 18. Usar Dev Containers para unificar entorno de desarrollo
```json
{
  "name": "Node.js",
  "dockerFile": "Dockerfile"
}
```
