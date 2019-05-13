---
title: "Consultar cliente"
excerpt: "A continuación se explica como consultar un cliente en específico"
---
Para consultar un cliente en específico es necesario agregar el RFC.
[block:parameters]
{
  "data": {
    "h-0": "Parámetro",
    "h-1": "Tipo",
    "h-2": "Requerido",
    "h-3": "Detalles",
    "0-0": "rfc",
    "0-1": "string",
    "0-2": "Opcional \n\n*Requerido en el caso de querer consultar solo a un cliente.",
    "0-3": "Indica el RFC del cliente, para traer todas las invoices del mismo."
  },
  "cols": 4,
  "rows": 1
}
[/block]

[block:html]
{
  "html": "<div>\n  <h1>Construcción de la URL</h1>\n</div>\n<style>\n  h1{\n  \tcolor:#173457;\n    font-size: 18px;\n    font-weight:500;\n  }\n</style>"
}
[/block]
**Host**: ** https://factura.com** (producción)     /    **http://devfactura.in** (sandbox)
**Endpoint**:  /api/v1/clients/rfc

**Ejemplo**:  https://factura.com/api/v1/clients/rfc
[block:html]
{
  "html": "<div>\n  \n  <h1>Ejemplo:</h1>\n</div>\n<style>\n  h1{\n  \tcolor:#173457;\n    font-size: 18px;\n    font-weight:500;\n  }\n</style>"
}
[/block]

[block:code]
{
  "codes": [
    {
      "code": "<?php\n$ch = curl_init();\n\ncurl_setopt($ch, CURLOPT_URL, \"https://factura.com/api/v1/clients/rfc\");\ncurl_setopt($ch, CURLOPT_RETURNTRANSFER, TRUE);\ncurl_setopt($ch, CURLOPT_HEADER, FALSE);\n\ncurl_setopt($ch, CURLOPT_HTTPHEADER, array(\n    \"Content-Type: application/json\",\n    \"F-PLUGIN: \" . '9d4095c8f7ed5785cb14c0e3b033eeb8252416ed',\n    \"F-Api-Key: \".'Ingresa API KEY',\n    \"F-Secret-Key: \" .'Ingresa SECRET KEY'\n));\n$response = curl_exec($ch);\ncurl_close($ch);\n\nvar_dump($response);",
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
  "body": "Para probar el código de ejemplo es necesario que reemplaces el texto  **Ingresa API KEY**  por el API KEY de tu cuenta, e **Ingresa SECRET KEY**  por el SECRET KEY correspondiente.\n\nAdemás de reemplazar **rfc** por el RFC del cliente que deseas consultar."
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
      "code": "[\n    {\n        \"status\": \"success o error\",\n        \"data\": [\n            {\n                \"RazonSocial\" : \"Razón Social del cliente\",\n                \"RFC\" : \"Registro Federal de Contribuyentes del cliente\",\n                \"Calle\" : \"Calle del domicilio del cliente\",\n                \"Numero\" : \"Número exterior del domicilio del cliente\",\n                \"Interior\" : \"Número interior del domicilio del cliente\",\n                \"Colonia\" : \"Colonia de domicilio del cliente\", \n                \"CodigoPosal\" : \"Código Postal del domicilio del cliente\",\n                \"Ciudad\" : \"Ciudad del domicilio del cliente\",\n                \"Delegacion\" : \"Delegación del domicilio del cliente\",\n                \"Estado\" : \"Estado del domicilio del cliente\",\n                \"NumRegIdTrib\" : \"\",\n                \"UsoCFDI\" : \"\",\n                \"Contacto\"[{\n                    \"Nombre\":\"Nombre(s) del cliente\",\n                    \"Apellidos\":\"Apellidos del cliente\",\n                    \"Email\":\"Correo electrónico del cliente\",\n                    \"Email2\":\"Correo electrónico 2 del cliente\",\n                    \"Email3\":\"Correo electrónico 3 del cliente\",\n                    \"Telefono\":\"Número de teléfono del cliente\"\n                }]\n                                }                ],\n        \"UID\": \"Id único e irrepetible asignado por Factura.com y que servirá para la gestión interna del docmento.\"\n    }\n]",
      "language": "json",
      "name": "Respues exitosa"
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