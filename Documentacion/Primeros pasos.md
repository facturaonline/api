---
title: "Primeros pasos"
excerpt: ""
---
Para hacer uso del API de Factura.com es necesario hacer uso del formato **JSON** .
Todas las respuestas, exitosas o de error, están en formato **JSON**.
Es necesario incluir en las cabeceras el token de acceso llamado **API KEY** y **SECRET KEY**
[block:html]
{
  "html": "<div>\n  <h1>Obtener API KEY y SECRET KEY</h1>\n</div>\n\n<style>\n  h1{\n  \tcolor:#173457;\n    font-size: 18px;\n    font-weight:500;\n  }\n</style>"
}
[/block]
Para obtener tus llaves de acceso deber seguir los siguientes pasos:
  * Iniciar sesión (Si es en producción en https://factura.com, si es en sandbox en http://devfactura.in).
  * En el menú lateral dirígete a **Configuraciones** - **API** - **Datos de acceso **.
  * Haz clic en el botón que se encuentra junto a cada token de acceso para copiarlo.

[block:html]
{
  "html": "<div>\n  <h1>Agregar a la cabecera</h1>\n</div>\n\n<style>\n  h1{\n  \tcolor:#173457;\n    font-size: 18px;\n    font-weight:500;\n  }\n</style>"
}
[/block]
Dentro de las cabeceras de la petición es necesario agregar las llaves para poder acceder al API.
[block:callout]
{
  "type": "warning",
  "title": "Importante",
  "body": "Es necesario incluir una cabecera  **F-PLUGIN** cuyo valor siempre será: **9d4095c8f7ed5785cb14c0e3b033eeb8252416ed**."
}
[/block]
A continuación se muestra un ejemplo:
[block:code]
{
  "codes": [
    {
      "code": "    \"Content-Type: application/json\",\n    \"F-PLUGIN: \" . '9d4095c8f7ed5785cb14c0e3b033eeb8252416ed',\n    \"F-Api-Key: \". JDJ5JDEwJGRuT1Y3cUM3WnJEMUNaaXRwVW5UUmVMS3RLUHhHMjlYZndaeWxyRXVpUjBLVmwxOHBPWFXX,\n    \"F-Secret-Key: \" . JDJ5JDEwJDZaTjRhWDVVRXh3ejZIRmxEU1pjeE9GMVRHakh4OGY0MG5lRS5DclhISGFoeUFmaThxaUXX",
      "language": "json",
      "name": "cabeceras.json"
    }
  ]
}
[/block]