---
title: "Listar productos"
excerpt: "A continuación se explica como listar los productos, con un ejemplo y muestra de posibles respuestas obtenidas."
---
Podemos consultar los productos que tenemos dados de alta, o filtrar por algunos parámetros:
[block:parameters]
{
  "data": {
    "h-0": "Parámetro",
    "h-1": "Tipo",
    "h-2": "Requerido",
    "h-3": "Detalles",
    "0-0": "page",
    "1-0": "per_page",
    "0-1": "int",
    "1-1": "int",
    "0-2": "Opcional",
    "1-2": "Opcional",
    "0-3": "Indica número de página a consultar, por default posiciona en la página 1.",
    "1-3": "Indica el limite de resultados para mostrar, por default retorna 100 registros."
  },
  "cols": 4,
  "rows": 2
}
[/block]

[block:html]
{
  "html": "<div>\n  <h1>Construcción de la URL</h1>\n</div>\n<style>\n  h1{\n  \tcolor:#173457;\n    font-size: 18px;\n    font-weight:500;\n  }\n</style>"
}
[/block]
**Host**: ** https://factura.com** (producción)     /    **http://devfactura.in** (sandbox)
**Endpoint**:  /api/v3/products/list

**Ejemplo**:  https://factura.com/api/v3/products/list
[block:html]
{
  "html": "<div>\n  \n  <h1>Ejemplo:</h1>\n</div>\n<style>\n  h1{\n  \tcolor:#173457;\n    font-size: 18px;\n    font-weight:500;\n  }\n</style>"
}
[/block]

[block:code]
{
  "codes": [
    {
      "code": "\n<?php\n$ch = curl_init();\n\ncurl_setopt($ch, CURLOPT_URL, \"https://factura.com/api/v3/products/list\");\ncurl_setopt($ch, CURLOPT_RETURNTRANSFER, TRUE);\ncurl_setopt($ch, CURLOPT_HEADER, FALSE);\n\ncurl_setopt($ch, CURLOPT_HTTPHEADER, array(\n    \"Content-Type: application/json\",\n    \"F-PLUGIN: \" . '9d4095c8f7ed5785cb14c0e3b033eeb8252416ed',\n    \"F-Api-Key: \".'Ingresa API KEY',\n    \"F-Secret-Key: \" .'Ingresa SECRET KEY'\n));\n\n$response = curl_exec($ch);\ncurl_close($ch);\n\nvar_dump($response);",
      "language": "php",
      "name": "listar_productos.php"
    }
  ]
}
[/block]

[block:callout]
{
  "type": "info",
  "title": "Recuerda",
  "body": "Para probar el código de ejemplo es necesario que reemplaces el texto  **Ingresa API KEY**  por el API KEY de tu cuenta, e **Ingresa SECRET KEY**  por el SECRET KEY correspondiente."
}
[/block]

[block:html]
{
  "html": "<div>\n  \n  <h1>Respuesta:</h1>\n</div>\n<style>\n  h1{\n  \tcolor:#173457;\n    font-size: 18px;\n    font-weight:500;\n  }\n</style>"
}
[/block]

[block:code]
{
  "codes": [
    {
      "code": "[\n  {\n    \"status\": \"success\",\n    \"total\": 4,\n    \"per_page\": 100,\n    \"current_page\": 1,\n    \"last_page\": 1,\n    \"from\": 1,\n    \"to\": 4,\n    \"data\": [\n      {\n        \"code\": \"59fa4f114751d\",\n        \"name\": \"Servicio técnico de orientación\",\n        \"price\": 1048.95,\n        \"sku\": \"sku-003\",\n        \"unidad\": \"Unidad de servicio\",\n        \"claveprodserv\": \"43232107\",\n        \"claveunidad\": \"E48\"\n      },\n      {\n        \"code\": \"59ea2a6886b4e\",\n        \"name\": \"SERVICIO DE HOSPEDAJE PARA ELEMENTOS DEL SERVICIO DE PROTECCION FEDERAL DEL 01 AL 09 DE OCTUBRE\",\n        \"price\": 100,\n        \"sku\": \"HOSP2\",\n        \"unidad\": \"Segundo [unidad de ángulo]\",\n        \"claveprodserv\": \"22101708\",\n        \"claveunidad\": \"D62\"\n      },\n      {\n        \"code\": \"59ee370e03253\",\n        \"name\": \"Prubea de sin catalgo\",\n        \"price\": 123,\n        \"sku\": \"12212121\",\n        \"unidad\": \"Radián\",\n        \"claveprodserv\": \"0\",\n        \"claveunidad\": \"C81\"\n      },\n      {\n        \"code\": \"59ee7312578f1\",\n        \"name\": \"Producto de servicio de divisas\",\n        \"price\": 8888,\n        \"sku\": \"4533\",\n        \"unidad\": \"Valor monetario\",\n        \"claveprodserv\": \"84121603\",\n        \"claveunidad\": \"M4\"\n      }\n    ]\n  }\n]",
      "language": "json",
      "name": "respuesta exitosa"
    }
  ]
}
[/block]

[block:callout]
{
  "type": "danger",
  "title": "Sobre errores",
  "body": "El mensaje de error puede variar dependiendo el nodo en el que haya información incorrecta.\n\nTe sugerimos leer cuidadosamente el mensaje del error ya que en el mismo se indica donde es necesario corregir la información."
}
[/block]