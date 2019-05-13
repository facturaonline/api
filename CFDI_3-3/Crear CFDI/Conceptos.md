---
title: "Conceptos"
excerpt: "A continuación se describen los atributos que deben incluirse en el nodo Conceptos"
---
Para cada concepto es necesario incluir los siguientes atributos:
[block:parameters]
{
  "data": {
    "h-0": "Parámetro",
    "h-1": "Tipo",
    "h-2": "Requerido",
    "h-3": "Detalles",
    "0-0": "ClaveProdServ",
    "0-1": "string",
    "0-2": "Requerido",
    "0-3": "Indica la clave del producto o servicio correspondiente a tu concepto.\n\n Es importante que ésta la tomes del catálogo indicado por el SAT para que sea válida.\n\n**Ejemplo**:\n\"ClaveProdServ\": \"43232408\"",
    "1-0": "NoIdentificacion",
    "1-1": "string",
    "1-2": "Opcional",
    "1-3": "Indica el número de identificación o SKU en caso de tenerlo.\n\n**Ejemplo**:\n \"NoIdentificacion\": \"WEBDEV10\"",
    "2-0": "Cantidad",
    "2-1": "number",
    "2-2": "Requerido",
    "2-3": "Indica la cantidad.\n\n**Ejemplo**:\n'Cantidad' : '1'",
    "3-0": "ClaveUnidad",
    "3-1": "string",
    "4-0": "Unidad",
    "4-1": "string",
    "5-0": "ValorUnitario",
    "5-1": "string",
    "6-0": "Descripcion",
    "6-1": "string",
    "7-0": "Descuento",
    "7-1": "string",
    "8-0": "Impuestos",
    "9-0": "NumeroPedimento",
    "10-0": "Predial",
    "11-0": "Partes",
    "11-1": "array",
    "10-1": "string",
    "9-1": "string",
    "8-1": "array",
    "3-2": "Requerido",
    "4-2": "Requerido",
    "5-2": "Requerido",
    "6-2": "Requerido",
    "7-2": "Opcional",
    "8-2": "Opcional",
    "9-2": "Opcional",
    "10-2": "Opcional",
    "11-2": "Opcional",
    "3-3": "Indica la clave de la unidad  de medida correspondiente a tu concepto.\n\n[Consulta el listado de claves válidas para el SAT.](https://developers.factura.com/docs/unidad)\n\n**Ejemplo**:\n\"ClaveUnidad\": \"E48\"",
    "4-3": "Indica la unidad de medida. Ésta debe coincidir con la clave de la unidad ingresada en el parámetro anterior.\n\n[Consulta el listado de claves válidas para el SAT.](https://developers.factura.com/docs/unidad)\n\n**Ejemplo**:\n \"Unidad\": \"Unidad de servicio\"",
    "5-3": "Indica el precio unitario sin incluir impuestos.\n\n**Ejemplo**:\n \"ValorUnitario\": \"15000.00\"",
    "6-3": "Indica la descripción del concepto.\n\n**Ejemplo**:\n\"Descripcion\": \"Desarrollo web a la medida\"",
    "7-3": "Indica el importe del descuento, en caso de desear agregarlo.\n\n**Ejemplo**:\n\"Descuento\": \"10.00\"",
    "8-3": "Indicar los impuestos (traslados, locales y retenidos) que tendrá el concepto.\n\n[Consulta los parámetros que debe contener.](https://developers.factura.com/docs/impuestos)\n\n**Ejemplo**:\n      \"Impuestos\": {\n        \"Traslados\": [\n          {\n            \"Base\": \"15000.000000\",\n            \"Impuesto\": \"002\",\n            \"TipoFactor\": \"Tasa\",\n            \"TasaOCuota\": \"0.16\",\n            \"Importe\": \"2400.000000\"\n          }\n        ],\n        \"Retenidos\": [],\n        \"Locales\": []\n      }",
    "9-3": "Indica el número del pedimento correspondiente a la importación del bien.\n\n**Ejemplo**:\n \"NumeroPedimento\" : \"15 48 3009 0001234\"",
    "10-3": "Indica el número de predial en caso de ser necesario.\n\n**Ejemplo**:\n \"Predial\": \"56485422\",",
    "11-3": "Indica las partes o componentes que integran la totalidad del concepto.\n[\nVer los atributos que puede contener](https://developers.factura.com/docs/partes)."
  },
  "cols": 4,
  "rows": 12
}
[/block]

[block:html]
{
  "html": "<div>\n  \n  <h1>Ejemplo:</h1>\n</div>\n<style>\n  h1{\n  \tcolor:#173457;\n    font-size: 18px;\n    font-weight:500;\n  }\n</style>"
}
[/block]

[block:code]
{
  "codes": [
    {
      "code": "  \"Conceptos\": [\n    {\n      \"ClaveProdServ\": \"43232408\",\n      \"NoIdentificacion\": \"WEBDEV10\",\n      \"Cantidad\": \"1.000000\",\n      \"ClaveUnidad\": \"E48\",\n      \"Unidad\": \"Unidad de servicio\",\n      \"Descripcion\": \"Desarrollo web a la medida\",\n      \"ValorUnitario\": \"15000.000000\",\n      \"Importe\": \"15000.000000\",\n      \"Descuento\": \"0\",\n      \"tipoDesc\": \"porcentaje\",\n      \"honorarioInverso\": \"\",\n      \"montoHonorario\": \"0\",\n      \"Impuestos\": {\n        \"Traslados\": [\n          {\n            \"Base\": \"15000.000000\",\n            \"Impuesto\": \"002\",\n            \"TipoFactor\": \"Tasa\",\n            \"TasaOCuota\": \"0.16\",\n            \"Importe\": \"2400.000000\"\n          }\n        ],\n        \"Retenidos\": [],\n        \"Locales\": []\n      },\n      \"NumeroPedimento\": \"\",\n      \"Predial\": \"\",\n      \"Partes\": \"0\",\n      \"Complemento\": \"0\"\n    }\n  ],",
      "language": "json",
      "name": "conceptos.json"
    }
  ]
}
[/block]