---
title: "Aduana"
excerpt: "Consulta el catálogo de Aduanas"
---
[block:html]
{
  "html": "<div>\n  <h1>Construcción de la URL</h1>\n</div>\n\n<style>\n  h1{\n  \tcolor:#173457;\n    font-size: 18px;\n    font-weight: 500;\n  }\n  \n</style>"
}
[/block]
**Host**: ** https://facturaonline.com.mx** (producción)     /    **http://facturaonline.com.mx** (sandbox)
**Endpoint**:  /api/v3/catalogo/Aduana

**URL completa**:  https://facturaonline.com.mx/api/v3/catalogo/Aduana
[block:html]
{
  "html": "<div>\n  <h1>Ejemplo</h1>\n</div>\n\n<style>\n  h1{\n  \tcolor:#173457;\n    font-size: 18px;\n    font-weight: 500;\n  }\n  \n</style>"
}
[/block]

[block:code]
{
  "codes": [
    {
      "code": "<?php\n$ch = curl_init();\n\ncurl_setopt($ch, CURLOPT_URL, \"https://facturaonline.com.mx/api/v3/catalogo/Aduana\");\ncurl_setopt($ch, CURLOPT_RETURNTRANSFER, TRUE);\ncurl_setopt($ch, CURLOPT_HEADER, FALSE);\n\ncurl_setopt($ch, CURLOPT_HTTPHEADER, array(\n   \"Content-Type: application/json\",\n    \"F-PLUGIN: \" . '9d4095c8f7ed5785cb14c0e3b033eeb8252416ed',\n    \"F-Api-Key: \". 'Ingresa API KEY',\n    \"F-Secret-Key: \" . 'Ingresa SECRET KEY'\n));\n\n$response = curl_exec($ch);\ncurl_close($ch);\n\nvar_dump($response);\n",
      "language": "php",
      "name": "consulta_aduana.php"
    }
  ]
}
[/block]

[block:callout]
{
  "type": "info",
  "title": "Recuerda",
  "body": "Para probar el código de ejemplo es necesario que reemplaces el texto** Ingresa API KEY** por el **API KEY** de tu cuenta, e **Ingresa SECRET KEY** por el **SECRET KEY **correspondiente."
}
[/block]

[block:html]
{
  "html": "<div>\n  <h1>Respuesta</h1>\n</div>\n\n<style>\n  h1{\n  \tcolor:#173457;\n    font-size: 18px;\n    font-weight: 500;\n  }\n  \n</style>"
}
[/block]

[block:code]
{
  "codes": [
    {
      "code": "{\n  \"response\": \"success\",\n  \"data\": [\n    {\n      \"key\": \"01\",\n      \"name\": \"ACAPULCO, ACAPULCO DE JUAREZ, GUERRERO\"\n    },\n    {\n      \"key\": \"02\",\n      \"name\": \"AGUA PRIETA, AGUA PRIETA, SONORA\"\n    },\n    {\n      \"key\": \"05\",\n      \"name\": \"SUBTENIENTE LOPEZ, SUBTENIENTE LOPEZ, QUINTANA ROO\"\n    },\n    {\n      \"key\": \"06\",\n      \"name\": \"CIUDAD DEL CARMEN, CIUDAD DEL CARMEN, CAMPECHE\"\n    },\n    {\n      \"key\": \"07\",\n      \"name\": \"CIUDAD JUAREZ, CIUDAD JUAREZ, CHIHUAHUA\"\n    },\n    {\n      \"key\": \"08\",\n      \"name\": \"COATZACOALCOS, COATZACOALCOS, VERACRUZ\"\n    },\n    {\n      \"key\": \"11\",\n      \"name\": \"ENSENADA, ENSENADA, BAJA CALIFORNIA\"\n    },\n\t\t.\n    .\n    .\n    \n  ]\n}",
      "language": "json",
      "name": "Respuesta exitosa"
    }
  ]
}
[/block]