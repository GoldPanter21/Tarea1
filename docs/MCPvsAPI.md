# MCP frente a una API:

[Volver al README principal](../README.md)

## ¿Qué es una API?:
Es la forma de conectar una aplicación o servicio a una aplicación que ocupe de esos servicios, de esta manera, se pueden implementar funciones sin la necesidad de programarlas de forma nativa, incluso la API pudiese beneficiarse de sus usos cómo retroalimentación. <br> 
Lo que si se debe programar es la forma en la que los datos se estarán intercambiando, ya que suelen venir en algún formato específico y nosotros debemos encargarnos de traducir los datos de llegada y de salida en su debido caso.<br>
Funciona cómo cliente servidor mediante HTTP. Funciona mediante métodos "GET", "PUT", "POST" y "DELETE", no tiene estado ni ocupa autenticación.

## ¿Qué es un MCP?
Es el "ingreso" de una IA dentro de una aplicación, de forma que se puede llegar a modificar la aplicación mediante el uso del lenguaje natural, de esta forma, se puede conectar a archivos locales, bases de datos, motores de búsqueda, calculadoras y flujos de trabajo, así permitiendole el acceso a información clave y tareas de desarrollo. <br>
En palabras de la documentación oficial "pensar en MCP cómo un puerto USB para aplicaciones IA, que provee una forma estandarizada de conectar aplicaciones a servicios externos".<br>
Ahora, la base "JSON-RPC 2.0" no reinventa la forma de comunicarse, si no que utiliza un estandar ligero para intercambiar peticiones y respuestas sin estado. Es un equema dinámico que detalla el nombre de cada herramienta. La diferenci principal radica en condicionales. Ya no se usarán if/else para decidir la herramienta oara utilizar, si no, que se le pasan los parámetros necesarios a un LLM y este ejecuta hasta obtener una respuesta.

## Tabla Comparativa MCP vs API:

# MCP frente a una API

| Característica | Application Programming Interface (API) | Model Context Protocol (MCP) |
| :--- | :--- | :--- |
| **Quién decide qué se invoca** | El programador decide qué se invoca, ya sea mediante el uso de condicionales o por sentido de la aplicación. No hay forma externa o aparte de manipular esa desición. | El LLM es el enacargado de decidir basandose en la petición y el esquema dinámico, se manda la petición y se devuelve la respuesta del LLM. |
| **Cómo se descubren las capacidades** | Se debe de leer o de mínimo ver un video que explique la documentación completa, de forma que se puedan entender los "endpoints" y la forma en que se conectan (los métodos existentes y los parámetros que se requieren) | El catálogo dinamico muestra las capacidades, define las herramientas, una descripición y los parámetros necesarios sin intervención humana. De forma que el LLM descubre que puede hacer apenas conectarse. |
| **Acoplamiento cliente-servicio** | EL acomplamiento es especializado a la aplicación, si se cambia la forma en que la API recibe o entrega los datos, el código creado inicial ya no servirá. | No es especializado, puede incluso llegar a ser portable, ya que solo requiere de la comunicación JSON RPC 2.0 que opera de forma estandar. |
| **Formato de los mensajes** | Cómo ya se mencionó, funciona mediante REST en su mayoría, pero no hay un método normalizado, es específico a la forma seleccionada por el programador. | El intercambio se realiza mediante JSON RPC 2.0, de forma que toda petición en este formato si cumple, puede llamar a la herramienta necesaria. |
| **Autenticación y consentimiento** | Funciona meramente en código, mediante tokens o autorizaciones en las cabeceras por ejemplo. Una vez el cliente obtiene el token de autorización, se autorizan las llamadas. | Si se presentan alucinaciones, es peligroso darle el permiso de modificación sin supervisión, por lo que mediante una aceptación explicita cuando se trata con directorios o archivos delicados, se deben aprobar las ejecuciones. |
| **Reutilización entre aplicaciones** | Para reutilizar el servicio en otros códigos, con lo único con lo que se cuenta es con la experiencia previa y el código existente, no hay una forma real de mandar la funcionalidad a otro código. | La reutilización es nativa y automática, con programar un MCP y tener otro cliente estandar, se puede migrar el servicio, sin necesidad de nuevas lineas de integración. |

**ACLARACIÓN:** <br>
Un MCP no sustituye una API, en realidad, debido a su funcionamiento, no tienen formas de sustituir la una a la otra.
Ya que las API´s resuleven problemas específicos y requieren de codificación especial para funcionar, pero pueden hacer acciones mucho más específicas, a diferencia del MCP que es una herramienta de ayuda y que si bien puede modificar directorios y encontrar respuestas, no puede hacer más que la generación de texto o modificación, le es imposible realizar acciones específicas cómo recuperar datos de algún hardware. <br>
Y aunque en este documento nos hemos visto encueltos en un enfrentamiento entre ambos, es imporatnte mencionar que no son enemigos, en realidad pueden trabajar en conjunto para obtener mejores resultados.


## Bibliografía:
- Vida MRR - Programacion web, “Diferencia entre API y MCP,” YouTube. Jul. 08, 2026. [Online]. Available: https://www.youtube.com/watch?v=FdVkE8u2C_Q
- Model Context Protocol, “What is the Model Context Protocol (MCP)?,” Model Context Protocol, Sep. 13, 2026. https://modelcontextprotocol.io/docs/2026-07-28/getting-started/intro
- Model Context Protocol, “Tools,” Model Context Protocol, Sep. 13, 2026. https://modelcontextprotocol.io/specification/2026-07-28/server/tools
- Model Context Protocol, “Architecture overview,” Model Context Protocol, Sep. 13, 2026. https://modelcontextprotocol.io/docs/2026-07-28/learn/architecture
- Amazon Web Services, “¿Qué es una interfaz de programación de aplicaciones (API)?,” Amazon Web Services, Inc. https://aws.amazon.com/es/what-is/api/
- “¿Qué es una API REST (API RESTful)? | IBM,” Aug. 06, 2026. https://www.ibm.com/es-es/think/topics/rest-apis
- Model Context Protocol, “Overview,” Model Context Protocol, Sep. 13, 2026. https://modelcontextprotocol.io/specification/2026-07-28/basic/transports
- Auth, “¿Qué es OAuth 2.0 y para qué sirve? - Auth0,” Auth0. https://auth0.com/es/intro-to-iam/what-is-oauth-2