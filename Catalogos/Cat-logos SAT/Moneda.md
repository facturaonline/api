
# Moneda"

Consulta el catálogo de monedas"

[block:html]
{
  "html": "<div>\n  <h1>Construcción de la URL</h1>\n</div>\n\n<style>\n  h1{\n  \tcolor:#173457;\n    font-size: 18px;\n    font-weight: 500;\n  }\n  \n</style>"
}
[/block]
**Host**: ** https://facturaonline.com.mx** (producción)     /    **http://facturaonline.com.mx** (sandbox)
**Endpoint**:  /api/v3/catalogo/Moneda

**URL completa**:  https://facturaonline.com.mx/api/v3/catalogo/Moneda
[block:html]
{
  "html": "<div>\n  <h1>Ejemplo</h1>\n</div>\n\n<style>\n  h1{\n  \tcolor:#173457;\n    font-size: 18px;\n    font-weight: 500;\n  }\n  \n</style>"
}
[/block]

[block:code]
{
  "codes": [
    {
      "code": "<?php\n$ch = curl_init();\n\ncurl_setopt($ch, CURLOPT_URL, \"https://facturaonline.com.mx/api/v3/catalogo/Moneda\");\ncurl_setopt($ch, CURLOPT_RETURNTRANSFER, TRUE);\ncurl_setopt($ch, CURLOPT_HEADER, FALSE);\n\ncurl_setopt($ch, CURLOPT_HTTPHEADER, array(\n   \"Content-Type: application/json\",\n    \"F-PLUGIN: \" . '9d4095c8f7ed5785cb14c0e3b033eeb8252416ed',\n    \"F-Api-Key: \". 'Ingresa API KEY',\n    \"F-Secret-Key: \" . 'Ingresa SECRET KEY'\n));\n\n$response = curl_exec($ch);\ncurl_close($ch);\n\nvar_dump($response);\n",
      "language": "php",
      "name": "consulta_metodo.php"
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
      "code": "{\n  \"response\": \"success\",\n  \"data\": [\n    {\n      \"key\": \"AED\",\n      \"name\": \"Dirham de EAU\"\n    },\n    {\n      \"key\": \"AFN\",\n      \"name\": \"Afghani\"\n    },\n    {\n      \"key\": \"ALL\",\n      \"name\": \"Lek\"\n    },\n    {\n      \"key\": \"AMD\",\n      \"name\": \"Dram armenio\"\n    },\n    {\n      \"key\": \"ANG\",\n      \"name\": \"Florín antillano neerlandés\"\n    },\n    .\n    .\n    .\n  ]\n}",
      "language": "json",
      "name": "Respuesta exitosa"
    }
  ]
}
[/block]