# CASOS DE USO:

[Volver al README principal](../README.md)

El protocolo MCP está siendo adoptado por entornos de desarrollo y editores avanzados para interactuar directamente con el sistema del usuario. Tres herramientas actuales que implementan esta arquitectura son:

1.  **Google Antigravity:** 
    Es un entorno de desarrollo agéntico avanzado. Utiliza MCP para orquestar agentes de IA que pueden investigar, planificar y ejecutar flujos de trabajo de ingeniería de software complejos. Gracias a MCP, Antigravity puede conectarse a herramientas del sistema local (como la terminal o el sistema de archivos) para que los agentes operen de manera autónoma sobre el código.
2.  **Cursor (IDE):** 
    Es un editor de código (un *fork* de VS Code) con IA nativa integrada. Funciona como un cliente MCP que utiliza servidores locales para dar a sus modelos subyacentes contexto de toda la base de código. Lo utiliza para leer errores directamente de la terminal, rastrear definiciones a través de múltiples archivos y proponer refactorizaciones masivas en el proyecto.
3.  **Roo Code (anteriormente Cline):** 
    Es una extensión agéntica para VS Code. A diferencia de un modelo de lenguaje puro (como la familia Qwen), Roo Code es la *herramienta concreta* (el cliente) que puede utilizar modelos como Qwen, Claude o GPT bajo el capó. Usa MCP para actuar como un ingeniero de software autónomo: analiza los requerimientos, lee los archivos del proyecto y ejecuta comandos en la terminal integrada.

## ¿Cómo editan repositorios completos sin subir archivos manualmente?

Tradicionalmente, el usuario tenía que arrastrar un archivo al chat web de un LLM, esperar la respuesta y luego copiar y pegar el código de vuelta en su editor. Las herramientas basadas en MCP eliminan por completo este proceso manual mediante la arquitectura de delegación local:

1.  **Conexión Local (`stdio`):** La herramienta se ejecuta en la computadora del usuario e inicia un servidor MCP de Sistema de Archivos en segundo plano de forma local.
2.  **Exploración Autónoma:** En lugar de que el humano suba el código, el Modelo de Lenguaje le pide al servidor MCP que explore el entorno usando herramientas como "list_directory" y "read_file" para entender la estructura del repositorio por sí mismo.
3.  **Edición Directa delegada:** Una vez que el modelo sabe qué cambiar, no imprime el código en una ventana de chat. En su lugar, invoca herramientas de escritura. 
4.  **Aprobación (Human-in-the-loop):** El cliente intercepta esa petición de escritura, le muestra al usuario un comparativo de lo que el modelo quiere cambiar, y con un solo clic de aprobación, la herramienta guarda los cambios directamente en el disco duro del usuario.

## Bibliografía:
- Model Context Protocol, “What is the Model Context Protocol (MCP)?,” Model Context Protocol, Sep. 13, 2026. https://modelcontextprotocol.io/docs/2026-07-28/getting-started/intro
- “servers/src/filesystem at main · modelcontextprotocol/servers,” GitHub. https://github.com/modelcontextprotocol/servers/tree/main/src/filesystem?utm_source=gemini