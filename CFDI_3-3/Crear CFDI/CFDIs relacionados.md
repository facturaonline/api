---
title: "CFDIs relacionados"
excerpt: "Este nodo es opcional y se utiliza para especificar los CFDIs con los que se encuentra relacionado el CFDI que se está timbrando."
---
**Ejemplo**:
Si tu CFDI está sustituyendo a un CFDI timbrado y cancelado anteriormente al mismo receptor, entonces deberás indicar en este el UID y el tipo de relación que existe entre ambos.

A continuación se describen los atributos que conforman el nodo **CfdiRelacionados**:
[block:callout]
{
  "type": "info",
  "body": "El nodo CfdiRelacionados es opcional, en caso de agregarlo es necesario hacerlo dentro del objeto pincipal que se enviará en la petición.",
  "title": "Recuerda"
}
[/block]
El nodo de CfdiRelacionados se conforma de los siguientes atributos:
[block:parameters]
{
  "data": {
    "h-0": "Parámetro",
    "h-1": "Tipo",
    "h-2": "Requerido",
    "h-3": "Detalles",
    "0-0": "TipoRelacion",
    "1-0": "UUID",
    "0-1": "string",
    "1-1": "Array",
    "0-2": "Requerido",
    "1-2": "Requerido",
    "0-3": "Indicar la clave del tipo de relación correspondiente.\n\n[Revisar el listado de claves proporcionado por el SAT.](https://developers.factura.com/docs/tipo-de-relaci%C3%B3n)\n\n**Ejemplo**:\n\"TipoRelacion\": \"01\"",
    "1-3": "Indicar el o los UID de los CFDIS con los que se relaciona el actual.\n\n**Ejemplo**:\n \"UUID\": [\n      \"29c98cb2-f72a-4cbe-a297-606da335e187\",\n      \"a96f6b9a-70aa-4f2d-bc5e-d54fb7371236\"\n    ]"
  },
  "cols": 4,
  "rows": 2
}
[/block]

[block:html]
{
  "html": "<div>\n  <h1>Ejemplo:</h1>\n</div>\n<style>\n  h1{\n  \tcolor:#173457;\n    font-size: 18px;\n    font-weight:500;\n  }\n</style>"
}
[/block]

[block:code]
{
  "codes": [
    {
      "code": "\"CfdiRelacionados\": {\n    \"TipoRelacion\": \"01\",\n    \"UUID\": [\n      \"29c98cb2-f72a-4cbe-a297-606da335e187\",\n      \"a96f6b9a-70aa-4f2d-bc5e-d54fb7371236\"\n    ]\n  },",
      "language": "json",
      "name": "cfdi_relacionados.json"
    }
  ]
}
[/block]