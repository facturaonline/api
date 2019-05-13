---
title: "Consultar detalle empresa"
excerpt: "A continuación se explica como obtener los detalles de cualquier empresa que tengamos registrada en Factura.com"
---
Para consultar una empresa es necesario enviar el **UID** de la misma.
[block:parameters]
{
  "data": {
    "h-0": "Parámetro",
    "h-1": "Tipo",
    "h-2": "Rquerido",
    "0-3": "Envía el UID de la empresa registrada en factura.com.\n\n**Ejemplo**:\n5670a524cfc65",
    "0-0": "UID",
    "0-1": "string",
    "0-2": "Requerido"
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
**Endpoint**:  /api/v1/account/UID

**Ejemplo**:  https://factura.com/api/v1/account/UID
[block:html]
{
  "html": "<div>\n  \n  <h1>Ejemplo:</h1>\n</div>\n<style>\n  h1{\n  \tcolor:#173457;\n    font-size: 18px;\n    font-weight:500;\n  }\n</style>"
}
[/block]

[block:code]
{
  "codes": [
    {
      "code": "<?php\n$ch = curl_init();\n\ncurl_setopt($ch, CURLOPT_URL, \"http://devfactura.in/api/v1/account/UID\");\ncurl_setopt($ch, CURLOPT_RETURNTRANSFER, TRUE);\ncurl_setopt($ch, CURLOPT_HEADER, FALSE);\n\ncurl_setopt($ch, CURLOPT_HTTPHEADER, array(\n    \"Content-Type: application/json\",\n    \"F-PLUGIN: \" . '9d4095c8f7ed5785cb14c0e3b033eeb8252416ed',\n    \"F-Api-Key: \".'Ingresa API KEY',\n    \"F-Secret-Key: \" .'Ingresa SECRET KEY'\n));\n\n$response = curl_exec($ch);\ncurl_close($ch);\n\nvar_dump($response);\n",
      "language": "php",
      "name": "detalles_empresa.php"
    }
  ]
}
[/block]

[block:callout]
{
  "type": "info",
  "title": "Recuerda",
  "body": "Para probar el código de ejemplo es necesario que reemplaces el texto  **Ingresa API KEY**  por el API KEY de tu cuenta, e **Ingresa SECRET KEY**  por el SECRET KEY correspondiente.\n\nAdemás reemplazar el **UID**  en la URL."
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
      "code": "[\n    {\n        \"status\": \"success o error\",\n        \"data\": {\n                    \"uid\": \"5670a524cfc65\",\n                    \"razon_social\": \"EMPRESA DEMOSTRACION\",\n                    \"rfc\": \"XAXX010101000\",\n                    \"regimen_fiscal\": \"Persona Física con Actividad Empresarial\",\n                    \"calle\": \"Av. Ficticia\",\n                    \"exterior\": \"4587\",\n                    \"interior\": 7,\n                    \"colonia\": \"Centro\",\n                    \"codpos\": \"44987\",\n                    \"ciudad\": \"Guadalajara\",\n                    \"estado\": \"Jalisco\",\n                    \"email\": \"email@tucorreo.com\",\n                }\n    }\n]",
      "language": "json",
      "name": "Respuesta exitosa"
    },
    {
      "code": "{\n  \"status\": \"error\",\n  \"message\": \"La cuenta que intenta autenticarse no existe\",\n  \"Data\": \"$2y$10$dnOV7qC7ZrD1CZitpUnTReLKtKPxG29XfwZylrEuiR0KVl18pOXXX\",\n  \"Secret\": \"$2y$10$6ZN4aX5UExwz6HFlDSZcxOF1TGjHx8f40neE.CrXHHahyAfi8XXX.\"\n}",
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