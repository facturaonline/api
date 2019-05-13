---
title: "Receptor"
excerpt: "A continuación se describen los atributos que deben incluirse en el nodo Receptor"
---
[block:callout]
{
  "type": "warning",
  "title": "Importante",
  "body": "El receptor debe estar previamente registrado en el sistema para poder obtener el UID del mismo."
}
[/block]
El receptor debe incluir los siguientes atributos:
[block:parameters]
{
  "data": {
    "h-0": "Parámetro",
    "h-1": "Tipo",
    "h-2": "Requerido",
    "h-3": "Detalles",
    "0-0": "UID",
    "0-1": "string",
    "0-2": "Requerido",
    "0-3": "Indica el UID del receptor del CFDI.\n\n**Ejemplo**:\n\"UID\": \"55c0fdc67593d\"",
    "1-0": "ResidenciaFiscal",
    "1-1": "string",
    "1-2": "Opcional",
    "1-3": "Indicar el número de residencia fiscal cuando el receptor del comprobante sea un residente en el extranjero.\n\n**Ejemplo**:\n\"ResidenciaFiscal\": \"5256452\""
  },
  "cols": 4,
  "rows": 2
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
      "code": "  \"Receptor\": {\n    \"ResidenciaFiscal\": \"\",\n    \"UID\": \"55c0fdc67593d\"\n  },",
      "language": "json",
      "name": "receptor.json"
    }
  ]
}
[/block]