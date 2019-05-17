---
title: "Impuestos"
excerpt: "A continuación se describen los atributos que deben incluirse en el nodo Impuestos"
---
[block:callout]
{
  "type": "info",
  "title": "Recuerda",
  "body": "El nodo **Impuestos**  debe incluirse dentro de cada concepto agregado en el nodo **Conceptos**"
}
[/block]
El nodo de impuestos  se conforma de los siguientes atributos:
[block:parameters]
{
  "data": {
    "h-0": "Parámetro",
    "h-1": "Tipo",
    "h-2": "Requerido",
    "0-0": "Traslados",
    "h-3": "Detalles",
    "0-1": "array",
    "0-2": "Requerido*\n\n*** Es requerido siempre y cuando la factura lleve el tipo de impuesto Traslado.**",
    "0-3": "Indica los impuestos trasladados que se aplican a tu concepto.\n\n[Ver listado de atributos posibles para este nodo.](https://facturaonline.com.mx/docs/impuestos#traslados-retenidos)\n\n**Ejemplo**:\n\"Traslados\": [\n          {\n            \"Base\": \"15000.00\",\n            \"Impuesto\": \"002\",\n            \"TipoFactor\": \"Tasa\",\n            \"TasaOCuota\": \"0.16\",\n            \"Importe\": \"2400.00\"\n          }\n        ],",
    "1-0": "Retenidos",
    "1-1": "array",
    "1-2": "Requerido*\n\n*** Es requerido siempre y cuando la factura lleve el tipo de impuesto Retenciones.**",
    "1-3": "Indica los impuestos retenidos que se aplican a tu concepto.\n\n[Ver listado de atributos posibles para este nodo.](https://facturaonline.com.mx/docs/impuestos#traslados-retenidos)\n\n**Ejemplo**:\n\"Retenidos\": [\n          {\n            \"Base\": \"15000.00\",\n            \"Impuesto\": \"002\",\n            \"TipoFactor\": \"Tasa\",\n            \"TasaOCuota\": \"0.16\",\n            \"Importe\": \"2400.00\"\n          }\n        ],",
    "2-0": "Locales",
    "2-1": "array",
    "2-2": "Requerido*\n\n*** Es requerido siempre y cuando la factura lleve el tipo de impuesto Locales.**",
    "2-3": "Indica los impuestos locales que se aplican a tu concepto.\n\n[Ver listado de atributos posibles para este nodo.](https://facturaonline.com.mx/docs/impuestos#locales)\n\n**Ejemplo**:\n\"Locales\": [\n          {\n            \"Impuesto\": \"ISH\",\n            \"TasaOCuota\": \"0.05\",\n          }\n        ],"
  },
  "cols": 4,
  "rows": 3
}
[/block]

[block:html]
{
  "html": "<div id=\"traslados-retenidos\">\n  <h1>Atributos de los nodos Traslados y Retenidos</h1>\n</div>\n\n<style>\n\th1{\n    color: #173457;\n  font-size: 18px;\n  font-weight: 500;\n  }\n</style>"
}
[/block]
A continuación se describen los nodos que componen cada impuesto que desees agregar a tu concepto.

Un concepto puede tener más de un traslado y más de una retención. Cada impuesto debe incluirse dentro de un objeto, que a su vez es contenido por en el arreglo del tipo de impuesto correspondiente.

Los impuestos que pueden incluirse dentro de **traslados** son: 
  * IVA
  * IEPS 

Los impuestos que pueden incluirse dentro de **retenciones** son: 
  * IVA
  * ISR
[block:parameters]
{
  "data": {
    "h-0": "Parámetro",
    "h-1": "Tipo",
    "h-2": "Requerido",
    "h-3": "Detalles",
    "0-0": "Base",
    "0-1": "float",
    "0-2": "Requerido",
    "0-3": "Indica el valor sobre el cual se calculará el impuesto.\n\n**Ejemplo**:\n\"Base\": \"15000.00\",",
    "1-0": "Impuesto",
    "1-1": "string",
    "1-2": "Requerido",
    "1-3": "Indica la clave correspondiente al impuesto que deseas agregar.\n\nConsultar el catálogo de claves de **Impuestos**.\n\n**Ejemplo**:\n\"Impuesto\": \"002\"",
    "2-0": "TipoFactor",
    "3-0": "TasaOCuota",
    "4-0": "Importe",
    "2-1": "string",
    "3-1": "float",
    "4-1": "float",
    "2-2": "Requerido",
    "3-2": "Requerido",
    "4-2": "Requerido",
    "2-3": "Indica tipo de factor correspondiente al impuesto que deseas agregar.\n\nConsultar el catálogo de **Tipo factor**.\n\n**Ejemplo**:\n\"TipoFactor\": \"Tasa\"",
    "3-3": "Indica la tasa o cuota correspondiente al impuesto que deseas agregar. \n\nConsultar el catálogo de **Tasa o cuota**.\n\n**Ejemplo**:\n\"TasaOCuota\": \"0.16\"",
    "4-3": "Indica el importe del impuesto trasladado que aplica a cada concepto. No se permiten valores negativos. \n\n\n**Ejemplo**:\n\"Importe\": \"2400.00\""
  },
  "cols": 4,
  "rows": 5
}
[/block]

[block:html]
{
  "html": "<div id=\"locales\">\n  <h1>Atributos del nodo Locales</h1>\n</div>\n\n<style>\n\th1{\n    color: #173457;\n  font-size: 18px;\n  font-weight: 500;\n  }\n</style>"
}
[/block]
A continuación se describen los nodos que componen los impuestos locales:
[block:parameters]
{
  "data": {
    "h-0": "Parámetro",
    "h-1": "Tipo",
    "h-2": "Requerido",
    "h-3": "Detalles",
    "0-0": "Impuesto",
    "0-1": "string",
    "0-2": "Requerido",
    "0-3": "Indica el impuesto que deseas agregar, éste puede ser CEDULAR o ISH\n\n**Ejemplo**:\n\"Impuesto\": \"CEDULAR\"",
    "1-0": "TasaOCuota",
    "1-1": "float",
    "1-2": "Requerido",
    "1-3": "Indica el valor de la tasa o cuota del impuesto que deseas agregar.\n\n**Ejemplo**:\n\"TasaOCuota\": \"0.05\""
  },
  "cols": 4,
  "rows": 2
}
[/block]

[block:callout]
{
  "type": "info",
  "title": "Recuerda",
  "body": "Por disposición del SAT un concepto no puede tener **ISH** e **IEPS** al mismo tiempo.\n\nPor favor valida tus conceptos para evitar errores al momento de timbrar."
}
[/block]

[block:html]
{
  "html": "<div>\n  <h1>Ejemplo</h1>\n</div>\n\n<style>\n\th1{\n    color: #173457;\n  font-size: 18px;\n  font-weight: 500;\n  }\n</style>"
}
[/block]

[block:code]
{
  "codes": [
    {
      "code": "\"Impuestos\": {\n  \"Traslados\": [\n    {\n      \"Base\": \"15000.000000\",\n      \"Impuesto\": \"002\",\n      \"TipoFactor\": \"Tasa\",\n      \"TasaOCuota\": \"0.16\",\n      \"Importe\": \"2400.000000\"\n    }\n  ],\n  \"Retenidos\": [\n  \t{\n      \"Base\": \"15000.000000\",\n      \"Impuesto\": \"002\",\n      \"TipoFactor\": \"Tasa\",\n      \"TasaOCuota\": \"0.16\",\n      \"Importe\": \"2400.000000\"\n    }\n  ],\n  \"Locales\": [\n  \t{\n      \"Impuesto\": \"CEDULAR\",\n      \"TasaOCuota\": \"0.05\",\n    }\n  ]\n},",
      "language": "json",
      "name": "impuestos.json"
    }
  ]
}
[/block]