---
title: "Listar CFDI's"
excerpt: "A continuación se explica como listar los CFDI's , con un ejemplo y  muestra de posibles respuestas obtenidas."
---
Podemos consultar los CFDI's filtrando por los siguientes parámetros:
[block:parameters]
{
  "data": {
    "h-0": "Parámetro",
    "h-1": "Tipo",
    "h-2": "Requerido",
    "h-3": "Detalles",
    "0-0": "month",
    "1-0": "year",
    "2-0": "rfc",
    "3-0": "type_document",
    "4-0": "page",
    "5-0": "per_page",
    "0-1": "number",
    "1-1": "number",
    "2-1": "string",
    "3-1": "string",
    "4-1": "int",
    "5-1": "int",
    "0-2": "Opcional",
    "1-2": "Opcional",
    "2-2": "Opcional",
    "3-2": "Opcional",
    "4-2": "Opcional",
    "5-2": "Opcional",
    "0-3": "Induca el número de mes que deseas consultar. Éste debe estar escrito en 2 dígitos.\n\n **Ejemplo**: Enero = 01, Diciembre = 12, etc.",
    "1-3": "Indica el año que deseas consultar. Éste debe estar escrito en 4 dígitos. \n\n**Ejemplo**: 2017.",
    "2-3": "Indica un RFC para traer todos los CFDI's timbrados al mismo.\n\n**Ejemplo**: XAXX010101000.",
    "3-3": "Indica un tipo de CFDI para  listar solo los CFDI's de ese tipo. Para ello enviar la clave indicada en el catálogo de **Tipos de CFDI**.\n\n**Ejemplo**: factura\n\n Consulta el catálogo de tipos de CFDIs.",
    "4-3": "Indica número de página a consultar, por default posiciona en la página 1.",
    "5-3": "Indica el limite de resultados para mostrar, por default retorna 100 registros."
  },
  "cols": 4,
  "rows": 6
}
[/block]

[block:html]
{
  "html": "<div>\n  <h1>Construcción de la URL</h1>\n</div>\n<style>\n  h1{\n  \tcolor:#173457;\n    font-size: 18px;\n    font-weight:500;\n  }\n</style>"
}
[/block]
**Host**: ** https://factura.com** (producción)     /    **http://devfactura.in** (sandbox)
**Endpoint**:  /api/v3/cfdi33/list

**Ejemplo**:  https://factura.com/api/v3/cfdi33/list
[block:html]
{
  "html": "<div>\n  \n  <h1>Ejemplo:</h1>\n</div>\n<style>\n  h1{\n  \tcolor:#173457;\n    font-size: 18px;\n    font-weight:500;\n  }\n</style>"
}
[/block]

[block:code]
{
  "codes": [
    {
      "code": "<?php\n$ch = curl_init();\n\ncurl_setopt($ch, CURLOPT_URL, \"http://devfactura.in/api/v3/cfdi33/list\");\ncurl_setopt($ch, CURLOPT_RETURNTRANSFER, TRUE);\ncurl_setopt($ch, CURLOPT_HEADER, FALSE);\n\ncurl_setopt($ch, CURLOPT_HTTPHEADER, array(\n    \"Content-Type: application/json\",\n    \"F-PLUGIN: \" . '9d4095c8f7ed5785cb14c0e3b033eeb8252416ed',\n    \"F-Api-Key: \".'Ingresa API KEY',\n    \"F-Secret-Key: \" .'Ingresa SECRET KEY'\n));\n\n$response = curl_exec($ch);\n\nreturn die($response);\n\ncurl_close($ch);\n\n?>\n",
      "language": "php",
      "name": "listar_cfdi.php"
    }
  ]
}
[/block]

[block:callout]
{
  "type": "info",
  "title": "Recuerda que",
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
      "code": "{\n  \"status\": \"success\",\n  \"response\": \"success\",\n  \"total\": 2479,\n  \"per_page\": 100,\n  \"current_page\": 1,\n  \"last_page\": 25,\n  \"from\": 1,\n  \"to\": 100,\n  \"data\": [\n    {\n      \"RazonSocialReceptor\": \"Venta Al Público en General\",\n      \"Folio\": \"F 01\",\n      \"UID\": \"5c04c662exxxx\",\n      \"UUID\": \"1750d757-577d-xxxx-xxxx-518b87b24a87\",\n      \"Subtotal\": \"5.000000\",\n      \"Descuento\": null,\n      \"Total\": \"5.800000\",\n      \"ReferenceClient\": 0,\n      \"NumOrder\": null,\n      \"Receptor\": \"XAXX010101000\",\n      \"FechaTimbrado\": \"2018-12-03\",\n      \"Status\": \"enviada\",\n      \"Version\": \"3.3\"\n    },\n    {\n      \"RazonSocialReceptor\": \"Cliente ejemplo\",\n      \"Folio\": \"F 160\",\n      \"UID\": \"5c033ca2e4xxx\",\n      \"UUID\": \"c25c6c99-xxx-xxx-810e-e5ae7e12eb15\",\n      \"Subtotal\": \"10000.000000\",\n      \"Descuento\": null,\n      \"Total\": \"11600.000000\",\n      \"ReferenceClient\": 15,\n      \"NumOrder\": null,\n      \"Receptor\": \"XAXX010101000\",\n      \"FechaTimbrado\": \"2018-12-01\",\n      \"Status\": \"enviada\",\n      \"Version\": \"3.3\"\n    }\n  ]\n}",
      "language": "json",
      "name": "Respuesta exitosa"
    },
    {
      "code": "{\n  \"status\": \"error\",\n  \"message\": \"La cuenta que intenta autenticarse no existe\",\n  \"Data\": \"$2y$10$dnOV7qC7ZrD1CZitpUnTReLKtKPxG29XfwZylrEuiR0KVl18pOXXX\",\n  \"Secret\": \"$2y$10$6ZN4aX5UExwz6HFlDSZcxOF1TGjHx8f40neE.CrXHHahyAfi8qiXXX\"\n}",
      "language": "json",
      "name": "Respuesta error"
    }
  ]
}
[/block]