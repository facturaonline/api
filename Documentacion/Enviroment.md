---
title: "Enviroment"
excerpt: ""
---
El API de Factura.com cuenta con dos entornos disponibles:
[block:html]
{
  "html": "<div>\n  <h1>Sandbox</h1>\n</div>\n\n<style>\n  h1{\n  \tcolor:#173457;\n    font-size: 18px;\n    font-weight:500;\n  }\n</style>"
}
[/block]
Host:  **http://devfactura.in**

Es un entorno de pruebas que simula el funcionamiento de nuestra API en producción, generando CFDIs sin validez fiscal.
[block:callout]
{
  "type": "warning",
  "title": "Importante",
  "body": "Es necesario solicitar una cuenta para el entorno de desarrollo **sandbox** antes de comenzar a utilizarlo, para esto envía un correo a [soporte@factura.com](mailto:soporte@factura.com)."
}
[/block]

[block:html]
{
  "html": "<div>\n  <h1>Producción</h1>\n</div>\n\n<style>\n  h1{\n  \tcolor:#173457;\n    font-size: 18px;\n    font-weight:500;\n  }\n</style>"
}
[/block]
Host:  **https://factura.com** 

Es el host para realizar el timbrado real, te recomendamos hacer pruebas en la versión sandbox primero, ya que los CFDIs generados en este entorno si tienen validez fiscal.
[block:html]
{
  "html": "<div>\n  <h1>Composición de la URL</h1>\n</div>\n\n<style>\n  h1{\n  \tcolor:#173457;\n    font-size: 18px;\n    font-weight:500;\n  }\n</style>"
}
[/block]
Independientemente del entorno en el que estés trabajando, la estructura de la url se compone de la siguiente forma:

  * **Host** = sandbox (http://devfactura.in) o producción (https://factura.com)
  * **Version** = Versión de la API = api/v1 ó api/v3 
  * **End_point** = Describe el método al que se está haciendo la petición.


Por ejemplo, para traer listado de facturas en el entorno de producción la url es la siguiente:

https://factura.com/api/v1/invoices
[block:callout]
{
  "type": "info",
  "title": "Actualizaciones",
  "body": "Las** versiones 1 (v1) y 2 (v2)** de CFDI ya no se encuentran disponibles, actualmente la versión para timbrar es la** versión 3**."
}
[/block]