---
title: "Consulta LCO"
excerpt: "A continuación se explica como consultar el RFC de tu cliente en la lista de la LCO (Lista de Contribuyentes con Obligación ante el SAT), con un ejemplo y muestra de posibles respuestas obtenidas."
---
Servicio para identificar que los RFC (emisores y receptores) que intervienen en el proceso sean válidos, es decir que estén en la LCO (Lista de Contribuyentes con Obligación ante el SAT).
[block:html]
{
  "html": "<div>\n  <h1>Construcción de la URL</h1>\n</div>\n<style>\n  h1{\n  \tcolor:#173457;\n    font-size: 18px;\n    font-weight:500;\n  }\n</style>"
}
[/block]
**Host**: ** https://factura.com** (producción)     /    **http://devfactura.in** (sandbox)
**Endpoint**:  /api/v1/clients/lco/{RFC}

**Ejemplo**:  https://factura.com/api/v1/clients/lco/{RFC}
[block:html]
{
  "html": "<div>\n  \n  <h1>Ejemplo:</h1>\n</div>\n<style>\n  h1{\n  \tcolor:#173457;\n    font-size: 18px;\n    font-weight:500;\n  }\n</style>"
}
[/block]

[block:code]
{
  "codes": [
    {
      "code": "<?php\n$ch = curl_init();\n\ncurl_setopt($ch, CURLOPT_URL, \"https://factura.com/api/v1/clients/lco/XAXX010101000\");\ncurl_setopt($ch, CURLOPT_RETURNTRANSFER, TRUE);\ncurl_setopt($ch, CURLOPT_HEADER, FALSE);\n\ncurl_setopt($ch, CURLOPT_HTTPHEADER, array(\n    \"Content-Type: application/json\",\n    \"F-PLUGIN: \" . '9d4095c8f7ed5785cb14c0e3b033eeb8252416ed',\n    \"F-Api-Key: \".'Ingresa API KEY',\n    \"F-Secret-Key: \" .'Ingresa SECRET KEY'\n));\n$response = curl_exec($ch);\ncurl_close($ch);\n\nvar_dump($response);",
      "language": "php",
      "name": "listar_cliente.php"
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
      "code": "[\n    {\n        \"status\": \"success\",\n        \"message\": \"El RFC se encuentra el la lista de LCO (Lista de Contribuyentes con Obligación ante el SAT).\"\n    }\n]",
      "language": "json",
      "name": "Respues exitosa"
    },
    {
      "code": "[\n    {\n        \"status\": \"error\",\n        \"message\": \"El RFC no se encuentra el la lista de LCO (Lista de Contribuyentes con Obligación ante el SAT), no podrás facturar a este RFC.\"\n    }\n]",
      "language": "json",
      "name": "Respuesta error"
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