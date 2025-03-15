# Preguntas y respuestas sobre Docker

## 1. ¿Cuál es una práctica recomendada para asegurar que las imágenes de Docker sean seguras antes de desplegarlas en producción?
**Respuesta**: Escanear las imágenes en busca de vulnerabilidades conocidas.

## 2. ¿Cuál es la ventaja principal de utilizar un Dockerfile multi-stage en un proyecto complejo?
**Respuesta**: Reduce el tamaño de la imagen final al incluir solo lo necesario.

## 3. ¿Qué ventaja principal ofrece el uso de imágenes distroless en Docker?
**Respuesta**: Reducen el tamaño de la imagen al eliminar componentes innecesarios.

## 4. ¿Qué debes hacer si Docker te muestra un error relacionado con el almacenamiento de contenedores al intentar crear una imagen multiplataforma?
**Respuesta**: Habilitar el containerd en Docker Desktop y reiniciar el motor de Docker.

## 5. Si necesitas asegurarte de que Docker no reutilice el caché para ningún paso durante la construcción de una imagen, ¿qué comando deberías usar?
**Respuesta**: `docker build --no-cache`

## 6. Si tienes una imagen de Docker que pesa 1.19 GB y deseas reducir su tamaño sin sacrificar el rendimiento, ¿qué estrategia podrías utilizar?
**Respuesta**: Cambiar a una imagen base más ligera como Alpine.

## 7. Al crear un Dockerfile para un proyecto de .NET, ¿qué aspecto es crucial para asegurar que la imagen resultante sea eficiente?
**Respuesta**: Seleccionar una imagen base adecuada que equilibre tamaño y rendimiento.

## 8. Si quisieras minimizar el tamaño de una imagen de Linux para un contenedor, ¿cuál sería una buena opción?
**Respuesta**: Usar la imagen de Alpine.

## 9. Si deseas mejorar el rendimiento de una imagen Docker, ¿qué estrategia deberías considerar?
**Respuesta**: Reducir el número de capas.

## 10. ¿Cómo podrías reducir el tamaño de una imagen Docker al construir un proyecto de Node.js?
**Respuesta**: Usando un archivo `.dockerignore` para omitir la carpeta `node_modules`.

## 11. Si al construir una imagen Docker no se omiten archivos innecesarios, ¿qué problema podrías enfrentar?
**Respuesta**: La imagen será más grande de lo necesario, ocupando más espacio.

## 12. Si necesitas que dos contenedores se comuniquen en una red específica, ¿qué tipo de red deberías crear?
**Respuesta**: Bridge.

## 13. Si tienes dos contenedores Docker ejecutándose en la misma máquina, ¿qué debes considerar al asignar puertos para evitar conflictos?
**Respuesta**: Asignar puertos diferentes a cada contenedor.

## 14. Si encuentras un error de ejecución debido a un espacio en un archivo YAML, ¿cuál sería la mejor manera de solucionarlo?
**Respuesta**: Corregir la indentación en la misma columna del archivo.

## 15. ¿Qué estrategia podrías usar para ejecutar pruebas automáticas en un contenedor Docker que no está disponible localmente?
**Respuesta**: Descargar y ejecutar el contenedor de manera remota en tiempo de ejecución.

## 16. ¿Qué sucede si ejecutas 'docker compose down' desde una ubicación diferente a donde ejecutaste 'docker compose up'?
**Respuesta**: No se detendrán ni eliminarán los contenedores.

## 17. ¿Cómo podrías verificar que todas las réplicas de un servicio en Docker Swarm están activas después de un despliegue?
**Respuesta**: Usar el comando `docker service ls` para listar los servicios y sus réplicas.

## 18. Si estás desarrollando una aplicación de prueba con pocos contenedores, ¿cuál es la mejor opción para desplegarla?
**Respuesta**: Desplegarla localmente sin un orquestador.

## 19. ¿Cómo podrías utilizar Docker para asegurar que todos los miembros de tu equipo de desarrollo trabajen con la misma versión de Node.js?
**Respuesta**: Usando Dev Containers para unificar el entorno de desarrollo.

## 20. ¿Qué ventaja ofrece un Dev Container al clonar un repositorio de GitHub con esta configuración?
**Respuesta**: Permite trabajar sin configurar manualmente el entorno de desarrollo.
