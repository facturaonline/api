---
title: "Consultar estatus cancelación de un CFDI"
excerpt: "A continuación se explica como consultar el estatus de la cancelación de un CFDI con un ejemplo de como hacerlo."
---
Podemos consultar el estatus CFDI haciendo uso del siguiente parámetro:
[block:parameters]
{
  "data": {
    "h-0": "Parámetro",
    "h-1": "Tipo",
    "h-2": "Requerido",
    "h-3": "Detalles",
    "0-0": "uid",
    "0-1": "string",
    "0-2": "Requerido",
    "0-3": "Indica el UID o UUID del CFDI que deseas consultar.\n\n**Ejemplo**:\n55c0fdc67593d"
  },
  "cols": 4,
  "rows": 1
}
[/block]

[block:html]
{
  "html": "<div>\n  <h1>Construcción de la URL:</h1>\n</div>\n<style>\n  h1{\n  \tcolor:#173457;\n    font-size: 18px;\n    font-weight:500;\n  }\n</style>"
}
[/block]
**Host**: ** https://factura.com** (producción)     /    **http://devfactura.in** (sandbox)
**Endpoint**:  /api/v3/cfdi33/uid/cancel_status

**Ejemplo**:  https://factura.com/api/v3/cfdi33/c55df8b4-37b3-47cf-9e35-efdb4c3261b4
/cancel_status

**Ejemplo**:  https://factura.com/api/v3/cfdi33/c55df8b4/cancel_status
[block:html]
{
  "html": "<div>\n  <h1>Ejemplo:</h1>\n</div>\n<style>\n  h1{\n  \tcolor:#173457;\n    font-size: 18px;\n    font-weight:500;\n  }\n</style>"
}
[/block]

[block:code]
{
  "codes": [
    {
      "code": "<?php\n$ch = curl_init();\n\ncurl_setopt($ch, CURLOPT_URL, \"https://factura.com/api/v3/cfdi33/uid/cancel\");\ncurl_setopt($ch, CURLOPT_RETURNTRANSFER, TRUE);\ncurl_setopt($ch, CURLOPT_HEADER, FALSE);\n\ncurl_setopt($ch, CURLOPT_HTTPHEADER, array(\n   \"Content-Type: application/json\",\n    \"F-PLUGIN: \" . '9d4095c8f7ed5785cb14c0e3b033eeb8252416ed',\n    \"F-Api-Key: \". 'Ingresa API KEY',\n    \"F-Secret-Key: \" . 'Ingresa SECRET KEY'\n));\n\n$response = curl_exec($ch);\ncurl_close($ch);\n\nvar_dump($response);",
      "language": "php",
      "name": "cancel_status_cfdi.php"
    }
  ]
}
[/block]

[block:callout]
{
  "type": "info",
  "title": "Recuerda",
  "body": "Para probar el código de ejemplo es necesario que reemplaces el texto  **Ingresa API KEY**  por el API KEY de tu cuenta, e **Ingresa SECRET KEY**  por el SECRET KEY correspondiente.\n\nAdemás de reemplazar **uid**  por el UID o UUID del CFDI que deseas consultar."
}
[/block]

[block:html]
{
  "html": "<div>\n  <h1>Respuesta:</h1>\n</div>\n<style>\n  h1{\n  \tcolor:#173457;\n    font-size: 18px;\n    font-weight:500;\n  }\n</style>"
}
[/block]

[block:code]
{
  "codes": [
    {
      "code": "{\n    \"response\": \"success\",\n    \"data\": {\n        \"CodigoEstatus\": \"S - Comprobante obtenido satisfactoriamente.\",\n        \"Estado\": \"Vigente\",\n        \"EsCancelable\": \"Cancelable sin aceptación\",\n        \"EstatusCancelacion\": []\n    }\n}",
      "language": "json",
      "name": "Estatus vigente cancelable"
    },
    {
      "code": "{\n    \"response\": \"success\",\n    \"data\": {\n        \"CodigoEstatus\": \"S - Comprobante obtenido satisfactoriamente.\",\n        \"Estado\": \"Cancelado\",\n        \"EsCancelable\": \"Cancelable sin aceptación\",\n        \"EstatusCancelacion\": \"Cancelado sin aceptación\"\n    }\n}",
      "language": "json",
      "name": "Estatus cancelado"
    },
    {
      "code": "{\n    \"response\": \"success\",\n    \"data\": {\n        \"CodigoEstatus\": \"S - Comprobante obtenido satisfactoriamente.\",\n        \"Estado\": \"Vigente\",\n        \"EsCancelable\": \"No Cancelable\",\n        \"EstatusCancelacion\": []\n    }\n}",
      "language": "json",
      "name": "Estatus vigente no cancelable"
    }
  ]
}
[/block]

[block:callout]
{
  "type": "warning",
  "title": "Sobre los mensajes",
  "body": "El mensaje de respuesta puede variar dependiendo de el estatus en el que se encuentre el CFDI.\n\nEs importante mencionar que, a pesar de que el nuevo método de cancelación entró en vigor el día 1 de noviembre de 2018, el SAT continúa presentando problemas con el servicio de consulta. Debido a esto, es posible que al consultar un CFDI cancelado, su estatus aparezca como vigente por un tiempo."
}
[/block]