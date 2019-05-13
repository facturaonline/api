---
title: "Detalles de empresa actual"
excerpt: "A continuación se explica como obtener los detalles de la empresa actual con la que se está trabajando."
---
[block:html]
{
  "html": "<div>\n  <h1>Construcción de la URL</h1>\n</div>\n<style>\n  h1{\n  \tcolor:#173457;\n    font-size: 18px;\n    font-weight:500;\n  }\n</style>"
}
[/block]
**Host**: ** https://factura.com** (producción)     /    **http://devfactura.in** (sandbox)
**Endpoint**:  /api/v1/current/account

**Ejemplo**:  https://factura.com/api/v1/current/account
[block:html]
{
  "html": "<div>\n  \n  <h1>Ejemplo:</h1>\n</div>\n<style>\n  h1{\n  \tcolor:#173457;\n    font-size: 18px;\n    font-weight:500;\n  }\n</style>"
}
[/block]

[block:code]
{
  "codes": [
    {
      "code": "<?php\n$ch = curl_init();\n\ncurl_setopt($ch, CURLOPT_URL, \"http://devfactura.in/api/v1/current/account\");\ncurl_setopt($ch, CURLOPT_RETURNTRANSFER, TRUE);\ncurl_setopt($ch, CURLOPT_HEADER, FALSE);\n\ncurl_setopt($ch, CURLOPT_HTTPHEADER, array(\n    \"Content-Type: application/json\",\n    \"F-PLUGIN: \" . '9d4095c8f7ed5785cb14c0e3b033eeb8252416ed',\n    \"F-Api-Key: \".'Ingresa API KEY',\n    \"F-Secret-Key: \" .'Ingresa SECRET KEY'\n));\n\n$response = curl_exec($ch);\ncurl_close($ch);\n\nvar_dump($response);\n",
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
      "code": "{\n  \"status\": \"success\",\n  \"data\": {\n    \"uid\": \"55c0fdc651XXX\",\n    \"razon_social\": \"EMPRESA DEMO\",\n    \"rfc\": \"LAN7008XXXX\",\n    \"regimen_fiscal\": \"GeneraldeLeyPersonasMorales\",\n    \"calle\": \"Lopez Mateos\",\n    \"exterior\": \"400\",\n    \"interior\": \"\",\n    \"colonia\": \"LadróndeGuevara\",\n    \"codpos\": \"44650\",\n    \"ciudad\": \"Guadalajara\",\n    \"estado\": \"Jalisco\",\n    \"email\": \"correo@correo.com\"\n  }\n}",
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