# Sistema de Servidores:

[Volver al README principal](../README.md)

El MCP (Model Context Protocol) es meramente el estandar de comunicación, no sabe realmente que está comunicando en general, sobre el están las aplicaciones que se pueden construir que funcionen bajo esas reglas. En este caso, para un Sistema de Archivos, usa un sistema de control de acceso de directorio flexible. Los directorios pueden especificarse por medio de comandos o dinamicamente en la raíz (root).<br>
Así cómo existe este  sistema de servidores sobre MCP, existen muchos otros cómo: Everything, Fetch, Git, Memory, Sequential Thinking y Time.

## Herramientas del Sistema:
Se pueden leer y escribir archivos, crear, listar y eliminar directorios, mover archivos o directorios, buscar archivos, obtener los metadatos de un archivo y tener acceso dinámica via root.

## Directorios Permitidos:
Para evitar que el servidor pueda modificar toda la computadora, se deben limitar los accesos mediante "directorios permitidos", y para configurar esos directorios, se deben configurar en la configuración del cliente, se le deben pasar explicitamente las rutas absolutas de la carpeta cómo argumentos cuando se inicie el servidor.<br>
La restricción funciona de forma que cada vez que se haga una petición (se invoque una herramienta), se verificará la ruta absoluta, si se está dentro, se accede, de lo contrario se bloquea y devuelve un error de seguridad.

## Razón del Límite:
El límite existe porque cómo se ha mencionado en otros documentos de este mismo directorio, se ha demostrado que si se dejan vulnerabilidades, no falta quien quiera y pueda aprovecharse o simplemente hacer la maldad. Si no se delimita el área en que se puede trabajar, entonces se podría llegar a eliminar partes importantes del sistema o incluso el sistema operativo, de forma que se inutilice o fallen las conexiones.<br>
Y no bastando con simplemente los problemas por otras personas, el propio servidor puede llegar a alucinar y eliminar esos archivos o modificarlos de formas irreversibles.

## Bibliografía:
- “servers/src/filesystem/README.md at main · modelcontextprotocol/servers.” https://github.com/modelcontextprotocol/servers/blob/main/src/filesystem/README.md
- “modelcontextprotocol/servers: Model Context Protocol Servers.” https://github.com/modelcontextprotocol/servers/tree/main