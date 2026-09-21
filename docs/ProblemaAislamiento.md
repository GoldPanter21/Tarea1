# Problema del Aislamiento
 
## ¿Por qué una LLM no puede acceder a un sistema?:
Un LLM es un algoritmo de generación de texto, no de ejecución, incluso revisnaod las herramientas de Antropic para la implementación de Claude a herramientas externas o API´s (mediante Tools), el LLM simplemente recibe cómo parametros lo que se quiere contestar, no realmente accede al sistema, solo conectan la función de generación mediante una petición incluso limitando el uso de tokens. Con esto explicado, los LLm son modelos en una estructura en la nube, no dentro del sistema de ejecución donde se está llamando, por lo que le falta incluso el contexto y así se reduce a que la entrada y salida, son texto.

## ¿Por qué se diseñó así la arquitectura?:
Si el sistema hubiera sido diseñado para ejecutarse en el sistema usuario, los problemas de seguridad en caso de vulneración serían catastroficos.<br>
Iniciando por la parte de hackeos, en caso de que el LLM tuviera acceso al sistema y el disco duro, si se hiciera un "Prompt Injection" ignorando instrucciones pasadas y eliinando ficheros importantes, drivers o en el peor de los cosas, el disco duro entero, dejando inutilizable el sistema.<br>
Todas estas medidas de seguridad no naces de la paranoia, pues ya existen problemas cuando se levanta un servidor en la nube con Ubuntu y se le dan permisos de administrador, dejando empresa sin sistema o con fallos terribles. También se sugiere el uso de estos modelos cómo asesores y no ejecutores, ya que si se les diera permiso insupervisado sobre un sistema y en algún problema de análisis decidiera eliminar algo que no pensara necesario en falta de contexto durante un momento, se podrían hacer varias perdidas.

## Bibliografía:

- “Tool use with Claude,” Claude Platform Docs. https://platform.claude.com/docs/en/agents-and-tools/tool-use/overview