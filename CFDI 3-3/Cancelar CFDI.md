---
title: "Cancelar CFDI"
excerpt: "A continuación se explica como crear un CFDI con un ejemplo de com hacerlo."
---
Podemos cancelar un CFDI haciendo uso del siguiente parámetro:
[block:parameters]
{
  "data": {
    "h-0": "Parámetro",
    "h-1": "Tipo",
    "h-2": "Requerido",
    "h-3": "Detalles",
    "0-0": "cfdi_uid",
    "0-1": "string",
    "0-2": "Requerido",
    "0-3": "Indica el UID o UUID del CFDI que deseas cancelar.\n\n**Ejemplo**:\n55c0fdc67593d"
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
**Endpoint**:  /api/v3/cfdi33/cfdi_uid/cancel

**Ejemplo**:  https://factura.com/api/v3/cfdi33/55c0fdc67593d/cancel
[block:html]
{
  "html": "<div>\n  <h1>Ejemplo:</h1>\n</div>\n<style>\n  h1{\n  \tcolor:#173457;\n    font-size: 18px;\n    font-weight:500;\n  }\n</style>"
}
[/block]

[block:code]
{
  "codes": [
    {
      "code": "<?php\n$ch = curl_init();\n\ncurl_setopt($ch, CURLOPT_URL, \"https://factura.com/api/v3/cfdi33/cfdi_uid/cancel\");\ncurl_setopt($ch, CURLOPT_RETURNTRANSFER, TRUE);\ncurl_setopt($ch, CURLOPT_HEADER, FALSE);\n\ncurl_setopt($ch, CURLOPT_HTTPHEADER, array(\n   \"Content-Type: application/json\",\n    \"F-PLUGIN: \" . '9d4095c8f7ed5785cb14c0e3b033eeb8252416ed',\n    \"F-Api-Key: \". 'Ingresa API KEY',\n    \"F-Secret-Key: \" . 'Ingresa SECRET KEY'\n));\n\n$response = curl_exec($ch);\ncurl_close($ch);\n\nvar_dump($response);",
      "language": "php",
      "name": "cancelar_cfdi.php"
    }
  ]
}
[/block]

[block:callout]
{
  "type": "info",
  "title": "Recuerda",
  "body": "Para probar el código de ejemplo es necesario que reemplaces el texto  **Ingresa API KEY**  por el API KEY de tu cuenta, e **Ingresa SECRET KEY**  por el SECRET KEY correspondiente.\n\nAdemás de reemplazar **cfdi_uid**  por el UID del CFDI que deseas cancelar."
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
      "code": "{\n   \"response\": \"success\",\n   \"message\": \"Estimado cliente tu CFDI CED274(10bc80fd-2881-4559-b98f-009cc6f6d28c) se canceló exitosamente\",\n   \"respuestaapi\": {\n      \"response\": \"success\",\n      \"acuse\": \"10BC80FD-2881-4559-B98F-009CC6F6D28C<\\/UUID>201<\\/EstatusUUID><\\/Folios>not(ancestor-or-self::*[local-name()='Signature'])<\\/XPath><\\/Transform><\\/Transforms>5p+cQwZ7vlmQ17braGY0x5Fd8KZI65Iif0S8FKsjeOfgT5Jxv5MAjmJRqxTTSaiNerizKFr3WCq9MdmS9V2lgg==<\\/DigestValue><\\/Reference><\\/SignedInfo>Mj7oysYQmbHCiZWMOd8bUMXHPBgPSCJxulvF4xHwM8CqSawNl7WP3F5/7GrDRGndR8covbSqNY+Qg8sP2kKL9w==<\\/SignatureValue>00001088888800000031<\\/KeyName>ujwIJaMKWWmawqDpHx/OS10pXzEh2SQhY02y64v9Q0+I+0dGlIrjFJeGrsHqAT3JoYnh38Dxwta98t/7++dh2hOgiZEwRignWRIlOgM1MefBHEyY+hi4vHpZgPKq/hJVfHf9nOvlb5UgIHMTCEwrDp3qk9O5XtTEycnWwiqleG0c1J9sfbRxC0gYBHsNTH85OEtSXYMkiWNYNnFbIc7B0sgp2y18jUxUCNFBMMTV0tz2sxRF+V4hblaPjI75RWmvs9E4lD7MVmW3z7LIlSajuSL8eOqoerSkQhPBABIeQenEPQwRTt3ej3XpVaBsOmagIPZZI3RvOVh+5mcXDE5txQ==<\\/Modulus>AQAB<\\/Exponent><\\/RSAKeyValue><\\/KeyValue><\\/KeyInfo><\\/Signature><\\/Acuse>\"\n   }\n}\n\n",
      "language": "json",
      "name": "Respuesta exitosa"
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