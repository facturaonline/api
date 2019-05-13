---
title: "Crear producto"
excerpt: "A continuación se explica como dar de alta un nuevo producto."
---
Podemos crear un nuevo producto haciendo uso de los siguientes parámetros:
[block:parameters]
{
  "data": {
    "h-0": "Parámetro",
    "h-1": "Tipo",
    "h-2": "Requerido",
    "h-3": "Detalles",
    "0-0": "code",
    "1-0": "name",
    "0-1": "string",
    "1-1": "string",
    "0-2": "Opcional",
    "1-2": "Requerido",
    "0-3": "Indica el código o SKU de tu producto.",
    "1-3": "Indica el nombre de tu producto.\n\nÉste nombre se mostrará en el apartado de **Conceptos** de tu CFDI.",
    "2-0": "price",
    "3-0": "clavePS",
    "4-0": "unity",
    "5-0": "claveUnity",
    "2-1": "numeric",
    "3-1": "string",
    "4-1": "string",
    "5-1": "string",
    "2-2": "Requerido",
    "3-2": "Requerido",
    "4-2": "Requerido",
    "5-2": "Requerido",
    "2-3": "Indica el  precio **sin IVA** de tu producto o servicio.",
    "3-3": "Indica la clave del producto o servicio correspondiente a tu concepto.\n\nConsulta el catálogo de **Clave Producto/Servicio **.",
    "4-3": "Indica la unidad de medida, ésta debe corresponder a la clave indicada en el atributo **claveUnity** .\n\n[Consulta el catálogo de **Clave Unidad **.](https://developers.factura.com/docs/unidad)",
    "5-3": "Indica la clave de la unidad de medida, ésta debe corresponder a la unidad indicada en el atributo **unity** .\n\n[Consulta el catálogo de **Clave Unidad **.](https://developers.factura.com/docs/unidad)"
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
**Endpoint**:  /api/v3/products/create

**Ejemplo**:  https://factura.com/api/v3/products/create
[block:html]
{
  "html": "<div>\n  \n  <h1>Ejemplo:</h1>\n</div>\n<style>\n  h1{\n  \tcolor:#173457;\n    font-size: 18px;\n    font-weight:500;\n  }\n</style>"
}
[/block]

[block:code]
{
  "codes": [
    {
      "code": "<?php\n$ch = curl_init();\n\ncurl_setopt($ch, CURLOPT_URL, \"https://factura.com/api/v3/products/create\");\ncurl_setopt($ch, CURLOPT_RETURNTRANSFER, TRUE);\ncurl_setopt($ch, CURLOPT_HEADER, FALSE);\n\ncurl_setopt($ch, CURLOPT_POST, TRUE);\n\ncurl_setopt($ch, CURLOPT_POSTFIELDS, \"{\n  \\\"code\\\": \\\"K001\\\",\n  \\\"name\\\": \\\"Desarrollo de banner para publicidad\\\",\n  \\\"price\\\": 35.9,\n  \\\"clavePS\\\": \\\"1154544511\\\",\n  \\\"unity\\\": \\\"Unidad de servicio\\\",\n  \\\"claveUnity\\\": \\\"E48\\\"\n}\");\n\ncurl_setopt($ch, CURLOPT_HTTPHEADER, array(\n   \"Content-Type: application/json\",\n    \"F-PLUGIN: \" . '9d4095c8f7ed5785cb14c0e3b033eeb8252416ed',\n    \"F-Api-Key: \". 'Ingresa API KEY',\n    \"F-Secret-Key: \" . 'Ingresa SECRET KEY'\n));\n\n$response = curl_exec($ch);\ncurl_close($ch);\n\nvar_dump($response);",
      "language": "php",
      "name": "crear_productos.php"
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
      "code": "[\n  {\n    \"status\": \"success\",\n    \"data\": [\n      {\n        \"code\": \"Ferreteria Perez\",\n        \"name\": \"XAXX010101000\",\n        \"sku\": \"Av. Juarez\",\n        \"price\": \"1234\",\n        \"clavePS\": \"\",\n        \"unity\": \"Centro\",\n        \"claveUnity\": \"44640\"\n      }\n    ]\n  }\n]",
      "language": "json",
      "name": "respuesta exitosa"
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