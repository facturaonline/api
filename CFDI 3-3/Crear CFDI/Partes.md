---
title: "Partes"
excerpt: "Este nodo es opcional y se utiliza para especificar los componentes de un concepto."
---
**Ejemplo**:
Si tu concepto es un *kit de herramientas*,  en el nodo partes puedes especificar los elementos que conforman ese kit como: martillo, desarmador, pienzas,etc.

A continuación se describen los atributos que conforman el nodo Partes:
[block:callout]
{
  "type": "info",
  "title": "Recuerda",
  "body": "El nodo **Partes** es opcional, en caso de agregarlo es necesario hacerlo dentro de uno (o varios) conceptos en el nodo  **Conceptos**"
}
[/block]
El nodo de Partes se conforma de los siguientes atributos:
[block:parameters]
{
  "data": {
    "h-0": "Parámetro",
    "h-1": "Tipo",
    "h-2": "Requerido",
    "h-3": "Detalles",
    "0-0": "ClaveProdServ",
    "1-0": "NoIdentificacion",
    "2-0": "Cantidad",
    "3-0": "ClaveUnidad",
    "4-0": "Unidad",
    "5-0": "ValorUnitario",
    "6-0": "Descripcion",
    "0-1": "string",
    "1-1": "string",
    "3-1": "string",
    "4-1": "string",
    "6-1": "string",
    "2-1": "number",
    "5-1": "float",
    "0-2": "Requerido",
    "2-2": "Requerido",
    "3-2": "Requerido",
    "4-2": "Requerido",
    "5-2": "Requerido",
    "6-2": "Requerido",
    "1-2": "Opcional",
    "0-3": "Indica la clave del producto o servicio correspondiente a tu concepto.\n\n Es importante que ésta la tomes del catálogo proveído por el SAT para que sea válida.\n\n**Ejemplo**:\n\"ClaveProdServ\": \"43232408\"",
    "1-3": "Indica el número de identificación o SKU en caso de tenerlo.\n\n**Ejemplo**:\n \"NoIdentificacion\": \"WEBDEV10\"",
    "2-3": "Indica la cantidad.\n\n**Ejemplo**:\n'Cantidad' : '1'",
    "3-3": "Indica la clave de la unidad  de medida correspondiente a tu concepto.\n\n[Consulta el listado de claves válidas para el SAT.](https://developers.factura.com/docs/unidad)\n\n**Ejemplo**:\n\"ClaveUnidad\": \"E48\"",
    "4-3": "Indica la unidad de medida. Ésta debe coincidir con la clave de la unidad ingresada en el parámetro anterior.\n\n[Consulta el listado de claves válidas para el SAT.](https://developers.factura.com/docs/unidad)\n\n**Ejemplo**:\n \"Unidad\": \"Unidad de servicio\"",
    "5-3": "Indica el precio unitario sin incluir impuestos.\n\n**Ejemplo**:\n \"ValorUnitario\": \"15000.00\"",
    "6-3": "Indica la descripción del concepto.\n\n**Ejemplo**:\n\"Descripcion\": \"Desarrollo web a la medida\""
  },
  "cols": 4,
  "rows": 7
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
      "code": "\"Partes\":[\n\t{ \n  \t\"ClaveProdServ\": \"43232408\",\n \t\t\"NoIdentificacion\":\"WEBDEV10\",\n    \"Cantidad\":\"1\",\n    \"ClaveUnidad\": \"E48\",\n    \"Unidad\": \"Unidad de servicio\",\n    \"ValorUnitario\": \"15000.00\",\n    \"Descripcion\": \"Desarrollo web a la medida\"\n  }\n]",
      "language": "json",
      "name": "partes.json"
    }
  ]
}
[/block]