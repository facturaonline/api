---
title: "Complemento de pago"
excerpt: "A continuación se explica como crear un complemento de pago, con un ejemplo y  muestra de posibles respuestas obtenidas."
---
Podemos crear un **CFDI con complemento de pago** haciendo uso de los siguientes parámetros:
[block:parameters]
{
  "data": {
    "h-0": "Parámetro",
    "h-1": "Tipo",
    "h-2": "Requerido",
    "h-3": "Detalles",
    "0-0": "Receptor",
    "0-1": "array",
    "0-2": "Requerido",
    "0-3": "Indica el UID del receptor/cliente previamente creado en factura.com.\n\n\n[Ver listado de atributos posibles para este nodo.](https://developers.factura.com/docs/receptor)\n\n**Ejemplo**:   \n\"Receptor\": {\n    \"ResidenciaFiscal\": \"\",\n    \"UID\": \"55c0fdc67593d\"\n  }",
    "1-0": "TipoDocumento",
    "1-1": "string",
    "1-2": "Requerido",
    "1-3": "Es necesario enviar la clave **P** en este campo.\n\n**Ejemplo**:\n \"TipoCfdi\": \"P\"",
    "2-0": "Conceptos",
    "2-1": "array",
    "2-2": "Requerido",
    "2-3": "Es un arreglo de objetos, en el que debe definirse un solo objeto con la siguiente información.\n\n**Ejemplo**:    \n  \"Conceptos\": [\n    {\n      \"ClaveProdServ\": \"84111506\",\n      \"Cantidad\": \"1\",\n      \"ClaveUnidad\": \"ACT\",\n      \"Descripcion\": \"Pago\",\n      \"ValorUnitario\": \"0\",\n      \"Importe\": \"0\"\n    }\n  ]",
    "3-0": "UsoCFDI",
    "3-1": "string",
    "3-2": "Requerido",
    "3-3": "Indica siempre la clave **P01** correspondiente a** Por definir**. \n\n**Ejemplo**: \n\"UsoCFDI\": \"P01\"",
    "4-0": "Serie",
    "4-1": "number",
    "4-2": "Requerido",
    "4-3": "Indica id de la serie con la que deseas timbrar el documento. \n\nÉsta debe estar dada de alta en tu panel de Factura.com y coincidir con el tipo de CFDI que deseas timbrar.\n\nPara obtenerlo  **Inicia sesión**  y dirígete al  **Menú latera**l  - **Configuraciones**  -  **Series y folios​** \n\n\n**Ejemplo**:  \n\"Serie\": 1247",
    "5-0": "CfdiRelacionados",
    "5-1": "array",
    "5-2": "Opcional",
    "5-3": "En caso que tu complemento sustituya a otro envía un arreglo con el/los UUID's con los que está relacionado.\n\n[Ver listado de atributos posibles para este nodo.](https://developers.factura.com/docs/cfdis-relacionados-1)\n\n**Ejemplo**:       \"CfdiRelacionados\": {\n    \"TipoRelacion\": \"04\",\n    \"UUID\": [\n      \"29c98cb2-f72a-4cbe-a297-606da335e187\",\n      \"a96f6b9a-70aa-4f2d-bc5e-d54fb7371236\"\n    ]\n  }",
    "6-0": "Moneda",
    "6-1": "string",
    "6-2": "Requerido",
    "6-3": "Se debe registrar siempre el valor \"XXX\".\n\n**Ejemplo:**\n\"Moneda\": \"XXX\"",
    "7-0": "NumOrder",
    "7-1": "number",
    "7-2": "Opcional",
    "7-3": "Indica el número de orden o pedido.\n\nEste dato es solo para control interno.\n\n**Ejemplo**:\n  \"NumOrder\": \"85abf36\"",
    "8-0": "Fecha",
    "8-1": "string",
    "8-2": "Opcional",
    "8-3": "Indica una fecha con formato (Y-m-d\\TH: m :s).\n\nEs posible enviar hasta 72 horas de atraso a la fecha actual, sin embargo no están permitidas las fechas futuras.\n\n**Ejemplo**:\n\"Fecha\": \"2018/12/04\"",
    "9-0": "EnviarCorreo",
    "9-1": "bolean",
    "9-2": "Opcional",
    "9-3": "Indica si deseas que el CFDI se envíe a tu cliente por correo electrónico. Por default esta opción es *true*.\n\n**Ejemplo**:\n\"EnviarCorreo\": \"true\"",
    "10-0": "Pagos",
    "10-1": "Array",
    "10-2": "Requerido",
    "10-3": "Indica los datos del complemento de pago.\n\n[Ver lista de atributos requeridos para este nodo.](https://developers.factura.com/docs/complemento-de-pago#pagos)"
  },
  "cols": 4,
  "rows": 11
}
[/block]

[block:callout]
{
  "type": "warning",
  "title": "Importante",
  "body": "Es necesario que envíes los valores (precios, cálculo de impuestos, subtotales, etc) de acuerdo a tus necesidades. Esto incluye número de decimales y redondeos."
}
[/block]

[block:html]
{
  "html": "<div id=\"pagos\">\n  <h1>Nodo: Pagos</h1>\n</div>\n<style>\n  h1{\n  \tcolor:#173457;\n    font-size: 18px;\n    font-weight:500;\n  }\n</style>"
}
[/block]
Es el nodo en el que se ingresa la información correspondiente complemento de pagos.

 A continuación se presentan los atibutos que debe incluir el nodo **Pagos**:
[block:parameters]
{
  "data": {
    "h-0": "Parámetro",
    "h-1": "Tipo",
    "h-2": "Requerido",
    "h-3": "Detalles",
    "0-0": "typeComplement",
    "0-1": "string",
    "0-2": "Requerido",
    "0-3": "Indica el tipo de complemento, en este caso es **pagos**.\n\n**Ejemplo**:\n\"typeComplement\": \"pagos\"",
    "1-0": "FechaPago",
    "2-0": "FormaDePagoP",
    "3-0": "MonedaP",
    "4-0": "TipoCambioP",
    "5-0": "Monto",
    "6-0": "NumOperacion",
    "7-0": "RfcEmisorCtaOrd",
    "8-0": "NomBancoOrdExt",
    "9-0": "CtaOrdenante",
    "10-0": "RfcEmisorCtaBen",
    "11-0": "CtaBeneficiario",
    "12-0": "TipoCadPago",
    "13-0": "relacionados",
    "5-1": "Number",
    "13-1": "array",
    "1-1": "string",
    "2-1": "string",
    "3-1": "string",
    "4-1": "string",
    "6-1": "string",
    "7-1": "string",
    "8-1": "string",
    "9-1": "string",
    "10-1": "string",
    "11-1": "string",
    "12-1": "string",
    "1-2": "Requerido",
    "2-2": "Requerido",
    "3-2": "Requerido",
    "1-3": "Indica la fecha y hora en la que el beneficiario recibe el pago, debe estar expresada en el siguiente formato: ** aaaa-mm-ddThh:mm:ss.** \n\n**Ejemplo**:\n\"FechaPago\": \"2018-12-01T12:00:00\"",
    "2-3": "Indica la clave de la forma de pago. \n\n[Ésta puedes consultarla en el  **Catálogo de formas de pago**. ](https://developers.factura.com/docs/forma-de-pago)\n\n**Nota**: debe ser distinta a la clave **99 - Por definir**.\n\n**Ejemplo**: \n \"FormaPago\": \"01\"",
    "5-2": "Requerido",
    "13-2": "Requerido",
    "4-2": "Opcional",
    "6-2": "Opcional",
    "7-2": "Opcional",
    "8-2": "Opcional",
    "9-2": "Opcional",
    "10-2": "Opcional",
    "11-2": "Opcional",
    "12-2": "Opcional",
    "3-3": "Indica la clave de la moneda del pago.\n\n[Ésta puedes consultarla en el  **Catálogo de monedas**](https://developers.factura.com/docs/moneda)\n\n**Ejemplo:**\n\"Moneda\": \"MXN\"",
    "4-3": "Indica el tipo de cambio vigente al momento de recibir el pago.\n\n**Ejemplo**:\n  \"TipoCambio\": \"19.85\"",
    "5-3": "Indica el importe del pago, éste debe ser mayor a 0.\n\n**Ejemplo**:\n  \"Monto\": \"1000.00\"",
    "6-3": "Indica el número de orden o pedido.\n\nEste dato es solo para control interno.\n\n**Ejemplo**:\n  \"NumOrder\": \"85abf36\"",
    "7-3": "Si lo deseas, indica el RFC del banco de la cuenta de origen de la  transferencia. \n\n\n**Ejemplo**:\n  \"RfcEmisorCtaOrd\": \"BSM970519DU8\"",
    "8-3": "Si lo deseas, indica el nombre del banco de la cuenta ordenante.\n\n**Ejemplo**:\n  \"NomBancoOrdExt\": \"BANCO SANTANDER (MEXICO) S.A.\"",
    "9-3": "Si lo deseas, indica el número de la cuenta con la que se realizó el pago, o la CLABE interbancaria de la cuenta desde donde se hizo la transferencia. \n\n**Ejemplo**:\n  \"CtaOrdenante\": \"15478952364\"",
    "10-3": "Si lo deseas, indica el RFC del banco de la cuenta de destino de la  transferencia. \n\n\n**Ejemplo**:\n  \"RfcEmisorCtaOrd\": \"BNM840515VB1\"",
    "11-3": "Si lo deseas, indica el número de la cuenta o la CLABE interbancaria de la cuenta desde donde se recibió el pago. \n\n**Ejemplo**:\n  \"CtaOrdenante\": \"15478952364\"",
    "12-3": "Indica la clave del tipo de cadena de pago.\n\n[Consulta las claves correspondientes a** Forma de pago** válidas.](https://developers.factura.com/docs/forma-de-pago)",
    "13-3": "Indica al menos un documento relacionado para tu complemento de pago.\n\n[Revisa los atributos que debe llevar este nodo.](https://developers.factura.com/docs/relacionados)"
  },
  "cols": 4,
  "rows": 14
}
[/block]

[block:html]
{
  "html": "<div>\n  <h1>Construcción de la URL</h1>\n</div>\n<style>\n  h1{\n  \tcolor:#173457;\n    font-size: 18px;\n    font-weight:500;\n  }\n</style>"
}
[/block]
**Host**: ** https://factura.com** (producción)     /    **http://devfactura.in** (sandbox)
**Endpoint**:  api/v3/cfdi33/complemento/pagos/create

**Ejemplo**:  https://factura.com/api/v3/cfdi33/complemento/pagos/create
[block:html]
{
  "html": "<div>\n  \n  <h1>Ejemplo:</h1>\n</div>\n<style>\n  h1{\n  \tcolor:#173457;\n    font-size: 18px;\n    font-weight:500;\n  }\n</style>"
}
[/block]

[block:code]
{
  "codes": [
    {
      "code": "<?php\n$ch = curl_init();\n\ncurl_setopt($ch, CURLOPT_URL, \"https://factura.com/api/v3/cfdi33/complemento/pagos/create\");\ncurl_setopt($ch, CURLOPT_RETURNTRANSFER, TRUE);\ncurl_setopt($ch, CURLOPT_HEADER, FALSE);\n\ncurl_setopt($ch, CURLOPT_POST, TRUE);\n\ncurl_setopt($ch, CURLOPT_POSTFIELDS, \"{\n  \\\"TipoDocumento\\\": \\\"pago\\\",\n  \\\"NumOrder\\\": \\\"\\\",\n  \\\"EnviarCorreo\\\": true,\n  \\\"Version\\\": \\\"3.3\\\",\n  \\\"Serie\\\": 865,\n  \\\"Fecha\\\": \\\"2018/12/12\\\",\n  \\\"Subtotal\\\": 0,\n  \\\"Total\\\": 0,\n  \\\"Moneda\\\": \\\"XXX\\\",\n  \\\"UsoCFDI\\\": \\\"P01\\\",\n  \\\"Receptor\\\": {\n    \\\"ResidenciaFiscal\\\": \\\"\\\",\n    \\\"NumRegIdTrib\\\": \\\"\\\",\n    \\\"UID\\\": \\\"55c1010a47XXX\\\"\n  },\n  \\\"Conceptos\\\": [\n    {\n      \\\"ClaveProdServ\\\": \\\"84111506\\\",\n      \\\"Cantidad\\\": 1,\n      \\\"ClaveUnidad\\\": \\\"ACT\\\",\n      \\\"Descripcion\\\": \\\"Pago\\\",\n      \\\"ValorUnitario\\\": 0,\n      \\\"Importe\\\": 0,\n      \\\"Complemento\\\": [\n        {\n          \\\"typeComplement\\\": \\\"pagos\\\",\n          \\\"FechaPago\\\": \\\"2018-12-12T12:00:00\\\",\n          \\\"FormaDePagoP\\\": \\\"01\\\",\n          \\\"MonedaP\\\": \\\"MXN\\\",\n          \\\"TipoCambioP\\\": 0,\n          \\\"Monto\\\": \\\"500\\\",\n          \\\"NumOperacion\\\": \\\"0987654234567\\\",\n          \\\"RfcEmisorCtaOrd\\\": \\\"\\\",\n          \\\"CtaOrdenante\\\": \\\"\\\",\n          \\\"NomBancoOrdExt\\\": \\\"\\\",\n          \\\"RfcEmisorCtaBen\\\": \\\"\\\",\n          \\\"CtaBeneficiario\\\": \\\"\\\",\n          \\\"relacionados\\\": [\n            {\n              \\\"IdDocumento\\\": \\\"042233a5-fdb1-4217-8474-1688db68fXXX\\\",\n              \\\"MonedaDR\\\": \\\"MXN\\\",\n              \\\"TipoCambioDR\\\": 0,\n              \\\"MetodoDePagoDR\\\": \\\"PPD\\\",\n              \\\"NumParcialidad\\\": \\\"1\\\",\n              \\\"ImpSaldoAnt\\\": \\\"1000\\\",\n              \\\"ImpPagado\\\": \\\"500\\\",\n              \\\"ImpSaldoInsoluto\\\": \\\"500\\\"\n            }\n          ]\n        }\n      ]\n    }\n  ]\n}\");\n\ncurl_setopt($ch, CURLOPT_HTTPHEADER, array(\n   \"Content-Type: application/json\",\n    \"F-PLUGIN: \" . '9d4095c8f7ed5785cb14c0e3b033eeb8252416ed',\n    \"F-Api-Key: \". 'Ingresa API KEY',\n    \"F-Secret-Key: \" . 'Ingresa SECRET KEY'\n));\n\n$response = curl_exec($ch);\ncurl_close($ch);\n\nvar_dump($response);\n\n",
      "language": "php",
      "name": "crear_complemento_pagos.php"
    }
  ]
}
[/block]

[block:callout]
{
  "type": "info",
  "title": "Recuerda que",
  "body": "Para probar el código de ejemplo es necesario que reemplaces el texto  **Ingresa API KEY**  por el API KEY de tu cuenta, e **Ingresa SECRET KEY**  por el SECRET KEY correspondiente.\nAsí como cambiar los UID de los CFDIs relacionados y de receptor."
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
      "code": "{\n  \"response\": \"success\",\n  \"message\": \"Facturacreadayenviadasatisfactoriamente\",\n  \"UUID\": \"11299a64-db3f-4dfd-8ccb-5013ba034fXX\",\n  \"uid\": \"5c11578d2f71d\",\n  \"SAT\": {\n    \"UUID\": \"11299a64-db3f-4dfd-8ccb-5013ba034fXXX\",\n    \"FechaTimbrado\": \"2018-12-12T12: 46: 40\",\n    \"NoCertificadoSAT\": \"20001000000300022323\",\n    \"Version\": \"1.1\",\n    \"SelloSAT\": \"On\\/VuLDaF13cXUnMV79lKkvaKMW4IGkTd7QvBK+G9c4hmsYGWRfAGfYfUoh2Ab2IhRhw6VSP2IJAij8Ad0oSThW5+FOWRVax6jX0SHXFUWC8IXN5xuK2t6qVqQ5iRZt8ZVjTovz6Q8nP09cGBB46ikwWb9W9LTALl+ZtF2K6fQ0NnNXJy8a+GeMTKe\\/UpVnoPoLC179gkHTJZCJzYGUCcOlccSCE5Bxz6MzJQxGTGqmJi9vNuEpcH2tYwO9VzSOXL4foPt+oa5Jqc5r4c++gah97+1+NGuMUvaQX6kMq8PFUq5YXKo83sO2Flj54Ux68XsCLDv3Twc1h1FI4yCVXXXX==\",\n    \"SelloCFD\": \"X5rm9\\/shEu3u6oNT0TOdjOMfKD3kob9RBoB+FdHcD3wQhCp4ksA\\/YtgwW+dTF10ezyxsEQnc6V9XteNRe4sHyzUcedERUh1XWp+JTM247Rg2NHrGBecAYHPOFgB218ERSrCavaD949uPBR1GamXnNAdkL5YLxgbfjPLfMzE6sli0NdgsBuCES2hrvsU9FA0wLTenTP6c6B7kZd7kGVbKBRFixkB+MYvWtML1D2WK+XXXXX+IviFoJtSTd3OAFEBspy90t779l8Tgk4J+zs2Ug==\"\n  },\n  \"INV\": {\n    \"Serie\": \"PA\",\n    \"Folio\": 71\n  },\n  \"invoice_uid\": \"5c11578d2f7XX\"\n}",
      "language": "json",
      "name": "Respuesta exitosa"
    },
    {
      "code": "{\n  \"response\": \"error\",\n  \"message\": {\n    \"message\": \"401 - El rango de la fecha de generaci\\u00f3n no debe de ser mayor a 72 horas para la emisi\\u00f3n del timbre.\",\n    \"messageDetail\": \"Comprobante.Fecha: Fecha de emisi\\u00f3n: 2018-05-16T13:04:20 Fecha del Servidor: 2018-12-12T13:02:24 La fecha de emision no se encuentra en el rango permitido: 2018-12-09T13:02:24 - 2018-12-12T14:07:24\",\n    \"data\": null,\n    \"status\": \"error\"\n  },\n  \"xmlerror\": \"\\n<\\/cfdi:Conceptos><\\/pago10:Pago><\\/pago10:Pagos><\\/cfdi:Complemento><\\/cfdi:Comprobante>\\n\"\n}",
      "language": "json",
      "name": "Respuesta error "
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