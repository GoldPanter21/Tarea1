# Arquitectura de MCP:

[Volver al README principal](../README.md)

## Modelo Host / Cliente / Servidor:
Los participantes son quienes hacen posible una conexión entre uno o más servidores MCP.
- El HOST MCP: Es la aplicación IA que coordina y maneja multiples clientes. 
- El CLIENT MCP: Es un componente que mantiene una conexión con el servidor y obtiene el contexto del Servidor para el Host.
- El SERVER MCP: Es un programa que proveé el contexto a un cliente.
Para nuestra aplicación, el host es: , el servidor es: y el cliente es: .

## Primitivas del Servidor: 
Son el concepto más importante en MCP, define qué del cliente y qué de los servidores se pueden ofrecer enre sí. Especifican los tipos de información conceptual puede ser compartida con las aplicaciones IA y el rango de acciones que pueden ejecutarse.
- Tools (Herramientas): Funciones ejecutables que la aplicación IA puede invocar para realizar acciones. Es controlado por el modelo.
- Resources (Recursos): Datos que proveen de información contextual a la aplicación IA. Es controlado por la aplicación.
- Prompts (Instrucciones): Modelo reutilizable que ayuda con la interacción con los modelos de lenguaje. Es controlado por el usuario.<br>
Cada primitiva tiene asociados métodos de descubrimiento y hasta ejecución, así cómo otra más. 

## Primitivas del Cliente:
Estas primitivas que el cliente puede exponer sirven para que los autores del servidor MCP puedan hacer interacciones mucho mas completas.
- Elicitation: Permite a los servidores solicitar información adicional de los usuarios y es muy útil cuando el autor quiere obtener más información o preguntar por una confirmación. El servidor solicita una entrada con el método de "elicitation/create".
- ROOT: Define un límite para que el MCP pueda trabajar sin acceder a recursos innecesarios. Es fundamental para servidores cómo los del sistema de archivos ya que gracias a esta primitiva se delimita el área de trabajo. 

## Dos tipos de Transporte:
Las semanticas de transporte son identicas para cada método de transporte. Define cómo los mensajes son definidos y enviados, cómo se envían los metadatos y cómo se señalan la cancelación y la terminación. Esto no define el mensaje, si no la forma en que el mensaje es enviado.
- STDIO: Utilza la entrada y salida estandar del sistema operativo, iniciando el servidor localmente e iniciando un proceso hijo. Es ideal en sistemas de archivos, es muy seguro y rápido.
- STREMEABLE HTTP: Cada mensaje es un "POST" HTTP para un único endpoint MCP, repsonde mediante un objeto JSON. No se conecta a un hilo hijo, por lo que el cliente se  conecta a una URL remota. Se utiliza SERVER-SENT EVENTS para mantener un canal abierto por donde el servidor envía los mensajes en tiempo real.

## Nota sobre la especificación:
Toda la arquitectura y terminología descrita en este documento está basada en la especificación oficial de MCP, **Versión [2026-07-28.]**, consultada el **20/09/2026**.

## Bibliografía:
- Model Context Protocol, “Architecture overview,” Model Context Protocol, Sep. 13, 2026. https://modelcontextprotocol.io/docs/2026-07-28/learn/architecture
- Model Context Protocol, “Understanding MCP servers,” Model Context Protocol, Sep. 13, 2026. https://modelcontextprotocol.io/docs/2026-07-28/learn/server-concepts
- Model Context Protocol, “Overview,” Model Context Protocol, Sep. 13, 2026. https://modelcontextprotocol.io/specification/2026-07-28/basic/transports