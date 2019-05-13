---
title: "Actualizar empresa"
excerpt: "A continuación se explica como actualizar los datos de una empresa dada de alta en Factura.com"
---
Para actualizar la información de una empresa es necesario enviar los siguientes parámetros:
[block:parameters]
{
  "data": {
    "h-0": "Parámetro",
    "h-1": "Tipo",
    "h-2": "Requerido",
    "0-3": "Indica la Razón social de la empresa.",
    "0-0": "razons",
    "0-1": "string",
    "0-2": "Requerido",
    "1-0": "rfc",
    "2-0": "regimen",
    "3-0": "calle",
    "4-0": "numero_exterior",
    "5-0": "numero_interior",
    "6-0": "codpos",
    "7-0": "colonia",
    "8-0": "estado",
    "9-0": "ciudad",
    "10-0": "delegacion",
    "11-0": "email",
    "1-1": "string",
    "2-1": "string",
    "3-1": "string",
    "7-1": "string",
    "8-1": "string",
    "9-1": "string",
    "10-1": "string",
    "11-1": "string",
    "4-1": "int",
    "5-1": "int",
    "6-1": "numeric",
    "1-2": "Requerido",
    "3-2": "Requerido",
    "4-2": "Requerido",
    "6-2": "Requerido",
    "7-2": "Requerido",
    "8-2": "Requerido",
    "9-2": "Requerido",
    "11-2": "Requerido",
    "2-2": "Opcional",
    "5-2": "Opcional",
    "10-2": "Opcional",
    "1-3": "Indica el **RFC** de la empresa con **min:12** y **max:13**  caracteres.",
    "2-3": "Indica el código del régimen fiscal al que pertenece tu empresa\n\n[Consulta las claves de Régimen fiscal válidas](https://developers.factura.com/docs/r%C3%A9gimen-fiscal).",
    "3-3": "Indica el domicilio fiscal.",
    "4-3": "Indica el número exterior.",
    "5-3": "Indica el número interior.",
    "6-3": "Indica el código postal. \nÉste debe ser de 5 caracteres.",
    "7-3": "Indica la colonia.",
    "8-3": "Indica el estado.",
    "9-3": "Indica la ciudad.",
    "10-3": "Indica la delegación en caso de contar con ella.",
    "11-3": "Indica el Email."
  },
  "cols": 4,
  "rows": 12
}
[/block]

[block:html]
{
  "html": "<div>\n  <h1>Construcción de la URL</h1>\n</div>\n<style>\n  h1{\n  \tcolor:#173457;\n    font-size: 18px;\n    font-weight:500;\n  }\n</style>"
}
[/block]
**Host**: ** https://factura.com** (producción)     /    **http://devfactura.in** (sandbox)
**Endpoint**:  /api/v1/account/client_uid/update

**Ejemplo**:  https://factura.com/api/v1/account/client_uid/update
[block:html]
{
  "html": "<div>\n  \n  <h1>Ejemplo:</h1>\n</div>\n<style>\n  h1{\n  \tcolor:#173457;\n    font-size: 18px;\n    font-weight:500;\n  }\n</style>"
}
[/block]

[block:code]
{
  "codes": [
    {
      "code": "<?php\n$ch = curl_init();\n\ncurl_setopt($ch, CURLOPT_URL, \"https://factura.com/api/v1/account/client_uid/update\");\ncurl_setopt($ch, CURLOPT_RETURNTRANSFER, TRUE);\ncurl_setopt($ch, CURLOPT_HEADER, FALSE);\n\ncurl_setopt($ch, CURLOPT_POST, TRUE);\n\ncurl_setopt($ch, CURLOPT_POSTFIELDS, \"{\n  \\\"razons\\\": \\\"Ferreteria Perez\\\",\n  \\\"rfc\\\": \\\"XAXX010101000\\\",\n  \\\"regimen\\\": \\\"611\\\",\n  \\\"calle\\\": \\\"Av. Juarez\\\",\n  \\\"numero_exterior\\\": 1234,\n  \\\"numero_interior\\\": \\\"4\\\",\n  \\\"codpos\\\": 44640,\n  \\\"colonia\\\": \\\"Centro\\\",\n  \\\"estado\\\": \\\"Jalisco\\\",\n  \\\"ciudad\\\": \\\"Guadalajara\\\",\n  \\\"delegaion\\\": \\\"\\\",\n  \\\"email\\\": \\\"josepe@email.com\\\"\n}\");\n\ncurl_setopt($ch, CURLOPT_HTTPHEADER, array(\n \"Content-Type: application/json\",\n    \"F-PLUGIN: \" . '9d4095c8f7ed5785cb14c0e3b033eeb8252416ed',\n    \"F-Api-Key: \". 'Ingresa API KEY',\n    \"F-Secret-Key: \" . 'Ingresa SECRET KEY'\n));\n\n$response = curl_exec($ch);\ncurl_close($ch);\n\nvar_dump($response);\n",
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
  "body": "Para probar el código de ejemplo es necesario que reemplaces el texto  **Ingresa API KEY**  por el API KEY de tu cuenta, e **Ingresa SECRET KEY**  por el SECRET KEY correspondiente.\n\nAdemás reemplazar el **client_uid**  en la URL."
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
      "code": "[\n    {\n        \"status\": \"success\",\n        \"data\": {\n                    \"uid\": \"5670a524cfc65\",\n                    \"razon_social\": \"EMPRESA DEMOSTRACION\",\n                    \"rfc\": \"XAXX010101000\",\n                    \"regimen_fiscal\": \"611\",\n                    \"calle\": \"Av. Ficticia\",\n                    \"exterior\": \"4587\",\n                    \"interior\": 7,\n                    \"colonia\": \"Centro\",\n                    \"codpos\": \"44987\",\n                    \"ciudad\": \"Guadalajara\",\n                    \"estado\": \"Jalisco\",\n                    \"email\": \"email@tucorreo.com\",\n                }\n    }\n]",
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