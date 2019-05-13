---
title: "Catálogos SAT"
excerpt: "Puedes consultar los catálogos que el SAT provee para el timbrado."
---
El API de factura.com cuenta con endpoints puestos a tu disposición para consultar los catálogos de claves válidas para el SAT.


[block:html]
{
  "html": "<div>\n  <h1>Construcción de la URL</h1>\n</div>\n\n<style>\n  h1{\n  \tcolor:#173457;\n    font-size: 18px;\n    font-weight: 500;\n  }\n  \n</style>"
}
[/block]
**Host**: ** https://factura.com** (producción)     /    **http://devfactura.in** (sandbox)
**Endpoint**:  /api/v3/catalogo/nombre_catalogo

**Ejemplo**:  https://factura.com/api/v3/catalogo/Aduana
[block:callout]
{
  "type": "info",
  "title": "Recuerda",
  "body": "Es necesario cambiar en la url **nombre_catalogo**  por el nombre del catálogo que deseas consultar."
}
[/block]