# API-Azure-DevOps
Colección de API's en Azure DevOps
# pullrequestbyrepo.py
##Flujo del código:
parametros de entrada:
- Configura los valores de la organización (organization), 
- el proyecto (project),
- el repositorio (repository_name) y
- el token personal de acceso (personal_access_token).

1) Obtiene los repositorios:

Hace una petición GET a la API de Azure DevOps para listar todos los repositorios del proyecto.
Busca el ID del repositorio cuyo nombre coincide con back-create-pipelines.
Si el repositorio existe:
Busca Pull Requests completados:
Filtra las PRs que tienen estado "completed".
Si encuentra PRs completadas, extrae su: ID (pullRequestId)

2) Resultado: 
Descripción
Título
Branch de origen
Repositorio de origen
Busca Builds asociadas a la Pull Request:
Consulta la API de builds usando el pullRequestId de la PR más reciente.

Si encuentra builds asociadas, imprime el Build ID.
Errores:
Si alguna petición falla, imprime el código de estado y el mensaje de error.
