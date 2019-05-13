---
title: "Relacionados"
excerpt: "A continuación se describen los atributos que deben incluirse en el nodo Relacionados dentro del nodo Complemento."
---
[block:callout]
{
  "type": "info",
  "title": "Recuerda",
  "body": "El nodo **Relacionados** debe incluirse dentro del nodo **Pagos** "
}
[/block]
El nodo relacionados se conforma de un arreglo de objetos, cada uno de éstos con los siguientes atributos:
[block:parameters]
{
  "data": {
    "h-0": "Parámetro",
    "h-1": "Tipo",
    "h-2": "Requerido",
    "h-3": "Detalles",
    "0-0": "IdDocumento",
    "1-0": "MonedaDR",
    "2-0": "TipoCambioDR",
    "3-0": "MetodoDePagoDR",
    "4-0": "NumParcialidad",
    "5-0": "ImpSaldoAnt",
    "6-0": "ImpPagado",
    "7-0": "ImpSaldoInsoluto",
    "0-1": "string",
    "1-1": "decimal",
    "2-1": "decimal",
    "3-1": "string",
    "4-1": "string",
    "5-1": "Number",
    "6-1": "Number",
    "7-1": "Number",
    "0-2": "Requerido",
    "1-2": "Requerido",
    "3-2": "Requerido",
    "5-2": "Requerido",
    "2-2": "Opcional",
    "4-2": "Opcional",
    "6-2": "Requerido",
    "7-2": "Requerido",
    "0-3": "Indica el folio fiscal del CFDI al que quieras agregarle un pago.\n\n\n**Ejemplo**:\n\"IdDocumento\":\t\"54feddcf-af15-4715-8a1f-80a122d1db54\"",
    "1-3": "Indica la clave de la moneda indicada en el CFDI al que deseas agregarle el pago.\n\n**Ejemplo**:\n\"MonedaDR\" : \"MXN\"",
    "2-3": "Indica el tipo de cambio si es que la moneda del CFDI es diferente de **MXN**.\n\n**Ejemplo**:\n\"TipoCambioDR\": \"19.25\"",
    "3-3": "Indica la clave correspondiente al método de pago, Éste siempre debe ser **PPD**.\n\n**Ejemplo**:\n\"MetodoDePagoDR\" :\t\"PPD\"",
    "4-3": "Indica el número de pago o abono que corresponde. En caso de ser el primer pago poner **1**.\n\n**Ejemplo**:\n\"NumParcialidad\" : \"5\"",
    "5-3": "Indica el monto del saldo pendiente de la parcialidad anterior. En el caso de que sea la primer parcialidad este campo debe contener el importe total del documento relacionado. \n\n**Ejemplo**:\n\"ImpSaldoAnt\"\t: \"1000\"",
    "6-3": "Indica el importe del abono que se está haciendo actualmente al CFDI. \n\n**Ejemplo**:\n\"ImpPagado\" : \"1000\"",
    "7-3": "Indica el monto del saldo pendiente por pagar. Es la diferencia entre el Saldo anterior y el monto de pago.\n\n**Ejemplo**:\n\"ImpSaldoInsoluto\" : \"0\""
  },
  "cols": 4,
  "rows": 8
}
[/block]

[block:code]
{
  "codes": [
    {
      "code": "\"relacionados\":[\n\t{\n  \t\"IdDocumento\" :\t\"54feddcf-af15-4715-8a1f-80a122d1db54\",\n\t\t\"ImpPagado\" :\t\"1000\",\n\t\t\"ImpSaldoAnt\" :\t\"1000\",\n\t\t\"ImpSaldoInsoluto\" : \"0\",\n\t\t\"MetodoDePagoDR\":\t\"PPD\",\n\t\t\"MonedaDR\":\t\"MXN\",\n\t\t\"NumParcialidad\":\t\"5\",\n\t\t\"TipoCambioDR\":\t\"19.25\"\n  }\n]\n\n",
      "language": "json",
      "name": "relacionados.json"
    }
  ]
}
[/block]