---
title: "Crear CFDI"
excerpt: "A continuación se explica como crear un CFDI, con un ejemplo y  muestra de posibles respuestas obtenidas."
---
Podemos crear un CFDI haciendo uso de los siguientes parámetros:
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
    "1-0": "TipoCfdi",
    "1-1": "string",
    "1-2": "Requerido",
    "1-3": "Indica la clave del tipo de documento que deseas timbrar.\n\n[Ver listado de tipos de documentos.](https://developers.factura.com/v3.0/docs/cat%C3%A1logos)\n\n**Ejemplo**:\n \"TipoCfdi\": \"factura\"",
    "2-0": "Conceptos",
    "2-1": "array",
    "2-2": "Requerido",
    "2-3": "Es un arreglo de objetos, en el que cada objeto corresponde a un concepto con sus atibutos para agregar al CFDI.\n\n[Ver listado de atributos posibles para este nodo.](https://developers.factura.com/docs/conceptos)\n\n**Ejemplo**:    \n  \"Conceptos\": [\n    {\n      \"ClaveProdServ\": \"43232408\",\n      \"NoIdentificacion\": \"0021\",\n      \"Cantidad\": \"1.000000\",\n      \"ClaveUnidad\": \"E48\",\n      \"Unidad\": \"Unidad de servicio\",\n      \"Descripcion\": \"Desarrollo web a la medida\",\n      \"ValorUnitario\": \"15000.000000\",\n      \"Importe\": \"15000.000000\",\n      \"Descuento\": \"0\",\n      \"Impuestos\": {\n        \"Traslados\": [\n          {\n            \"Base\": \"15000.000000\",\n            \"Impuesto\": \"002\",\n            \"TipoFactor\": \"Tasa\",\n            \"TasaOCuota\": \"0.16\",\n            \"Importe\": \"2400.000000\"\n          }\n        ],\n        \"Retenidos\": [],\n        \"Locales\": []\n      },\n    }\n  ]",
    "3-0": "UsoCFDI",
    "3-1": "string",
    "3-2": "Requerido",
    "3-3": "Indica la clave del Uso de CFDI, ésta debe ser válida para el SAT.\n\n[Ver catálogo de claves de **uso de cfdi**.](https://developers.factura.com/docs/uso-de-cfdi)\n\n**Ejemplo**: \n\"UsoCFDI\": \"G01\"",
    "4-0": "Serie",
    "4-1": "number",
    "4-2": "Requerido",
    "4-3": "Indica id de la serie con la que deseas timbrar el documento. \n\nÉsta debe estar dada de alta en tu panel de Factura.com y coincidir con el tipo de CFDI que deseas timbrar. Para obtenerlo  **Inicia sesión**  y dirígete al  **Menú latera**l  - **Configuraciones**  -  **Series y folios​** \n\n\n**Ejemplo**:  \n\"Serie\": 1247",
    "5-0": "FormaPago",
    "5-1": "string",
    "5-2": "Requerido",
    "5-3": "Indica la clave de la forma de pago. \n\n[Ésta puedes consultarla en el  **Catálogo de formas de pago**](https://developers.factura.com/docs/forma-de-pago)\n\n**Ejemplo**: \n \"FormaPago\": \"01\"",
    "6-0": "MetodoPago",
    "6-1": "string",
    "6-2": "Requerido",
    "6-3": "Indica la clave del método de pago\n\n[Ésta puedes consultarla en el  **Catálogo de métodos de pago**](https://developers.factura.com/docs/m%C3%A9todos-de-pago)\n\n**Ejemplo**:  \n\"MetodoPago\": \"PUE\",",
    "7-0": "CondicionesDePago",
    "7-1": "string",
    "7-2": "Opcional",
    "7-3": "Indica las condiciones de pago del CFDI, éstas deben tener una longitud *minima de 1 y máxima de 1000* caracteres.\n\n**Ejemplo**:     \"CondicionesDePago\": \"Pago en 9 meses\",",
    "8-0": "CfdiRelacionados",
    "8-1": "array",
    "8-2": "Opcional",
    "8-3": "En caso que tu CFDI vaya relacionado con otro(s), envía un arreglo con el/los UUID's con los que está relacionado.\n\n[Ver listado de atributos posibles para este nodo.](https://developers.factura.com/docs/cfdis-relacionados)\n\n**Ejemplo**:       \"CfdiRelacionados\": {\n    \"TipoRelacion\": \"01\",\n    \"UUID\": [\n      \"29c98cb2-f72a-4cbe-a297-606da335e187\",\n      \"a96f6b9a-70aa-4f2d-bc5e-d54fb7371236\"\n    ]\n  }",
    "9-0": "Moneda",
    "9-1": "string",
    "9-2": "Requerido",
    "9-3": "Indica la clave de la moneda del CFDI.\n\n[Ésta puedes consultarla en el  **Catálogo de monedas**](https://developers.factura.com/docs/moneda)\n\n**Ejemplo:**\n\"Moneda\": \"MXN\"",
    "10-0": "TipoCambio",
    "10-1": "string",
    "10-2": "Opcional /\nRequerido en caso que el atributo *Moneda*  sea diferente de *MXN*",
    "10-3": "Indicar el tipo de cambio vigente al momento de crear el CFDI.\n\n**Ejemplo**:\n  \"TipoCambio\": \"19.85\"",
    "11-0": "NumOrder",
    "11-1": "number",
    "11-2": "Opcional",
    "11-3": "Indica el número de orden o pedido.\n\nEste dato es solo para control interno.\n\n**Ejemplo**:\n  \"NumOrder\": \"85abf36\"",
    "12-0": "Fecha",
    "12-1": "string",
    "12-2": "Opcional",
    "12-3": "Indica una fecha con formato (Y-m-d\\TH: m :s).\n\nEs posible enviar hasta 72 horas de atraso a la fecha actual, sin embargo no están permitidas las fechas futuras.\n\n**Ejemplo**:\n\"Fecha\": \"2018/12/04\"",
    "13-0": "Comentarios",
    "13-1": "string",
    "13-2": "Opcional",
    "13-3": "Indica si deseas que aparezcan comentarios en el PDF de tu CFDI.\n\n\n**Ejemplo**:\n\"Comentarios\": \"El pedido aún no es entregado\"",
    "14-0": "Cuenta",
    "14-1": "string",
    "14-2": "Opcional",
    "14-3": "En caso de desearlo, indica  los últimos 4 dígitos de la tarjeta o cuenta bancaria del cliente.\n\n**Ejemplo**:\n\"Cuenta\": \"0025\"",
    "15-0": "EnviarCorreo",
    "15-1": "bolean",
    "15-2": "Opcional",
    "15-3": "Indica si deseas que el CFDI se envíe a tu cliente por correo electrónico. Por default esta opción es *true*.\n\n**Ejemplo**:\n\"EnviarCorreo\": \"true\"",
    "16-0": "LugarExpedicion",
    "16-1": "string",
    "16-2": "Opcional",
    "16-3": "Indica el Código postal del lugar de expedición del CFDI.\n\nÉste debe tener* 5 caracteres*.\n\n\n**Ejemplo**:\n\"LugarExpedicion\": \"44650\""
  },
  "cols": 4,
  "rows": 17
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
  "html": "<div>\n  <h1>Construcción de la URL</h1>\n</div>\n<style>\n  h1{\n  \tcolor:#173457;\n    font-size: 18px;\n    font-weight:500;\n  }\n</style>"
}
[/block]
**Host**: ** https://factura.com** (producción)     /    **http://devfactura.in** (sandbox)
**Endpoint**:  /api/v3/cfdi33/create

**Ejemplo**:  https://factura.com/api/v3/cfdi33/create
[block:html]
{
  "html": "<div>\n  \n  <h1>Ejemplo:</h1>\n</div>\n<style>\n  h1{\n  \tcolor:#173457;\n    font-size: 18px;\n    font-weight:500;\n  }\n</style>"
}
[/block]

[block:code]
{
  "codes": [
    {
      "code": "<?php\n\n\nfor ($x = 1; $x <= 1; $x++) {\n    $Conceptos[] = [\n        'ClaveProdServ' => '81112107',\n        'Cantidad' => '1',\n        'ClaveUnidad' => 'E48',\n        'Unidad' => 'Unidad de servicio',\n        'ValorUnitario' => '100',\n        'Descripcion' => 'Desarrollo a la medida',\n        'Descuento' => '0',\n        'Impuestos' => [\n            'Traslados' => [\n                ['Base' => '100', 'Impuesto' => '002', 'TipoFactor' => 'Tasa', 'TasaOCuota' => '0.160000', 'Importe' => '16'],\n            ]\n        ],\n    ];\n}\n\n$ch = curl_init();\n$fields = [\n    \"Receptor\" => [\"UID\" => \"55c0fdc675XXX\"],\n    \"TipoDocumento\" => \"factura\",\n    \"UsoCFDI\" => \"P01\",\n    \"Redondeo\" => 2,\n    \"Conceptos\" => $Conceptos,\n    \"FormaPago\" => \"01\",\n    \"MetodoPago\" => 'PUE',\n    \"Moneda\" => \"MXN\",\n    \"CondicionesDePago\" => \"Pago en una sola exhibición\",\n    \"Serie\" => 1,\n    \"EnviarCorreo\" => 'true',\n    \"InvoiceComments\" => \"\"\n];\n\n$jsonfield = json_encode($fields);\n\n\ncurl_setopt($ch, CURLOPT_URL, \"http://devfactura.in/api/v3/cfdi33/create\");\ncurl_setopt($ch, CURLOPT_RETURNTRANSFER, TRUE);\ncurl_setopt($ch, CURLOPT_HEADER, FALSE);\ncurl_setopt($ch, CURLOPT_POST, TRUE);\ncurl_setopt($ch, CURLOPT_POSTFIELDS, $jsonfield);\n\ncurl_setopt($ch, CURLOPT_HTTPHEADER, array(\n    \"Content-Type: application/json\",\n    \"F-PLUGIN: \" . '9d4095c8f7ed5785cb14c0e3b033eeb8252416ed',\n    \"F-Api-Key: \". 'Ingresa API KEY',\n    \"F-Secret-Key: \" . 'Ingresa SECRET KEY'\n));\n\n$response = curl_exec($ch);\n\nreturn die($response);\n\ncurl_close($ch);\n\n?>\n",
      "language": "php",
      "name": "crear_cfdi.php"
    }
  ]
}
[/block]

[block:callout]
{
  "type": "info",
  "title": "Recuerda que",
  "body": "Para probar el código de ejemplo es necesario que reemplaces el texto  **Ingresa API KEY**  por el API KEY de tu cuenta, e **Ingresa SECRET KEY**  por el SECRET KEY correspondiente."
}
[/block]

[block:callout]
{
  "type": "warning",
  "title": "Importante",
  "body": "Por disposición del SAT los valores de traslados, descuentos, precios, etc, deberán tener **hasta 6 decimales**.\n\nEl redondeo debe ser a **2 decimales**  y aplica solamente a subtotales, suma de traslados y suma de retenidos."
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
      "code": "{\n  \"response\": \"success\",\n  \"message\": \"Factura creada y enviada satisfactoriamente\",\n  \"UUID\": \"8ff503a2-c6b7-4a25-XXX-a25610e6b488\",\n  \"uid\": \"5c06fa8b3bbe6\",\n  \"SAT\": {\n    \"UUID\": \"8ff503a2-c6b7-XXX-92c7-a25610e6b488\",\n    \"FechaTimbrado\": \"2018-12-04T16:07:08\",\n    \"NoCertificadoSAT\": \"20001000000300022323\",\n    \"Version\": \"1.1\",\n    \"SelloSAT\": \"lzlv2bEVsjx8XkiJHJvlfCjr7xJ/laxZnvSmGSKF3C/HI9WFDYFFk4NfGyILBj8ll7m1VoCqlkSLvu9dRex4jSSGfPJOPGDrx7w/4AOj/scHPU23uIPhztnaHIYHKg9UxP4L9rgX814msJ8V86IXZ1nY7akr77Cpf2c2yAnHaO1fm81oQIe32obIs2GrOey6JG9oxQNrcUawSXXXXXXXX\",\n    \"SelloCFD\": \"NJQH6WT8eLxAeti7pUWhB7F6C6xrdSqkFfORf3+SeGkhu+5E0cZZUQjgaSZLpPcgk01aQUf0Jayw2GewYou5MjD4OLzZnZuizPwy3cSfQXzgX6sJTtAsI00VyhQewxLYDSMqFUrPpniNQG8Nl/eEg1kx72kkmqih2KX2Z+URkhx14W7CMG2aMJnhDyZuyliF+cy3utjXwzxQMl+28A/mgnlfUXzZd/3IunTtxM/p4bpqbYinK+7Bd/n+90Z6axsFBs6N7wxUX6aK9YL58owhgVGXXXXXXXX\"\n  },\n  \"INV\": {\n    \"Serie\": \"F\",\n    \"Folio\": 1433\n  },\n  \"invoice_uid\": \"5c06fa8b3bXXX\"\n}",
      "language": "json",
      "name": "Respuesta exitosa"
    },
    {
      "code": "{\n  \"response\": \"error\",\n  \"message\": {\n    \"message\": \"CFDI33161 - El valor del campo Importe o que corresponde a Traslado no se encuentra entre el limite inferior y superior permitido.\",\n    \"messageDetail\": \"Comprobante:Concepto:Impuestos:Traslado:Importe: El Importe es mayor o menor al limite superior/inferior calculado. LimiteSuperiorCalculado: 17 LimiteInferiorCalculado: 15 Comprobante:Concepto:Impuestos:Traslado:Importe: 19\",\n    \"data\": null,\n    \"status\": \"error\"\n  },\n  \"xmlerror\": \"\\n</cfdi:Traslados></cfdi:Impuestos></cfdi:Concepto></cfdi:Conceptos></cfdi:Traslados></cfdi:Impuestos></cfdi:Comprobante>\\n\"\n}",
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