# Crear CFDI

A continuación se explica como crear un CFDI, con un ejemplo y  muestra de posibles respuestas obtenidas.
Podemos crear un CFDI haciendo uso de los siguientes parámetros:

```

{
    "data": {
        "h-0": "Parámetro",
        "h-1": "Tipo",
        "h-2": "Requerido",
        "h-3": "Detalles",
        "0-0": "Receptor",
        "0-1": "array",
        "0-2": "Requerido",
        "0-3": "Indica el UID del receptor/cliente previamente creado en facturaonline.com.mx.
        [Ver listado de atributos posibles para este nodo.](https://facturaonline.com.mx/docs/receptor).
        **Ejemplo**:   "Receptor": {
            "ResidenciaFiscal": "",
            "UID": "55c0fdc67593d"
        }",
        "1-0": "TipoCfdi",
        "1-1": "string",
        "1-2": "Requerido",
        "1-3": "Indica la clave del tipo de documento que deseas timbrar.
        [Ver listado de tipos de documentos.](https://facturaonline.com.mx/v3.0/docs/cat%C3%A1logos).
        **Ejemplo**: "TipoCfdi": "factura",
        "2-0": "Conceptos",
        "2-1": "array",
        "2-2": "Requerido",
        "2-3": "Es un arreglo de objetos, en el que cada objeto corresponde a un concepto con sus atibutos para agregar al CFDI.
        [Ver listado de atributos posibles para este nodo.](https://facturaonline.com.mx/docs/conceptos).
        **Ejemplo**: "Conceptos": [{
            "ClaveProdServ": "43232408",
            "NoIdentificacion": "0021",
            "Cantidad": "1.000000",
            "ClaveUnidad": "E48",
            "Unidad": "Unidad de servicio",
            "Descripcion": "Desarrollo web a la medida",
            "ValorUnitario": "15000.000000",
            "Importe": "15000.000000",
            "Descuento": "0",
            "Impuestos": {
                "Traslados": [{
                    "Base": "15000.000000",
                    "Impuesto":  "002",
                    "TipoFactor": "Tasa",
                    "TasaOCuota": "0.16",
                    "Importe": "2400.000000"
                }],
                "Retenidos": [],
                "Locales": []
            },
        }],
        "3-0": "UsoCFDI",
        "3-1": "string",
        "3-2": "Requerido",
        "3-3": "Indica la clave del Uso de CFDI, ésta debe ser válida para el SAT.
        [Ver catálogo de claves de **uso de cfdi**.](https://facturaonline.com.mx/docs/uso-de-cfdi).
        **Ejemplo**: "UsoCFDI": "G01",
        "4-0": "Serie",
        "4-1": "number",
        "4-2": "Requerido",
        "4-3": "Indica id de la serie con la que deseas timbrar el documento. Ésta debe estar dada de alta en tu panel de Facturaonline.com.mx y coincidir con el tipo de CFDI que deseas timbrar.
        Para obtenerlo  **Inicia sesión**  y dirígete al  **Menú latera / Configuraciones / Series y folios​** **Ejemplo**:  "Serie": "1247",
        "5-0": "FormaPago",
        "5-1": "string",
        "5-2": "Requerido",
        "5-3": "Indica la clave de la forma de pago.
        [Ésta puedes consultarla en el  **Catálogo de formas de pago**](https://facturaonline.com.mx/docs/forma-de-pago).
        **Ejemplo**: "FormaPago": "01",
        "6-0": "MetodoPago",
        "6-1": "string",
        "6-2": "Requerido",
        "6-3": "Indica la clave del método de pago.
        [Ésta puedes consultarla en el  **Catálogo de métodos de pago**](https://facturaonline.com.mx/docs/m%C3%A9todos-de-pago).
        **Ejemplo**:  "MetodoPago": "PUE",
        "7-0": "CondicionesDePago",
        "7-1": "string",
        "7-2": "Opcional",
        "7-3": "Indica las condiciones de pago del CFDI, éstas deben tener una longitud **mínima de 1 y máxima de 1000* caracteres**.
        **Ejemplo**: "CondicionesDePago": "Pago en 9 meses",
        "8-0": "CfdiRelacionados",
        "8-1": "array",
        "8-2": "Opcional",
        "8-3": "En caso que tu CFDI vaya relacionado con otro(s), envía un arreglo con el/los UUID's con los que está relacionado.
        [Ver listado de atributos posibles para este nodo.](https://facturaonline.com.mx/docs/cfdis-relacionados).
        **Ejemplo**: "CfdiRelacionados": {
            "TipoRelacion": "01",
            "UUID": [
                "29c98cb2-f72a-4cbe-a297-606da335e187",
                "a96f6b9a-70aa-4f2d-bc5e-d54fb7371236"
            ]
        },
        "9-0": "Moneda",
        "9-1": "string",
        "9-2": "Requerido",
        "9-3": "Indica la clave de la moneda del CFDI.
        [Ésta puedes consultarla en el  **Catálogo de monedas**](https://facturaonline.com.mx/docs/moneda).
        **Ejemplo:** "Moneda": "MXN",
        "10-0": "TipoCambio",
        "10-1": "string",
        "10-2": "Opcional/Requerido en caso que el atributo *Moneda*  sea diferente de **MXN**",
        "10-3": "Indicar el tipo de cambio vigente al momento de crear el CFDI.
        **Ejemplo**: "TipoCambio": "19.85",
        "11-0": "NumOrder",
        "11-1": "number",
        "11-2": "Opcional",
        "11-3": "Indica el número de orden o pedido. Este dato es solo para control interno.
        **Ejemplo**: "NumOrder": "85abf36",
        "12-0": "Fecha",
        "12-1": "string",
        "12-2": "Opcional",
        "12-3": "Indica una fecha con formato (Y-m-d\\TH: m :s). Es posible enviar hasta 72 horas de atraso a la fecha actual, sin embargo no están permitidas las fechas futuras.
        **Ejemplo**: "Fecha": "2018/12/04",
        "13-0": "Comentarios",
        "13-1": "string",
        "13-2": "Opcional",
        "13-3": "Indica si deseas que aparezcan comentarios en el PDF de tu CFDI.
        **Ejemplo**: "Comentarios": "El pedido aún no es entregado",
        "14-0": "Cuenta",
        "14-1": "string",
        "14-2": "Opcional",
        "14-3": "En caso de desearlo, indica  los últimos 4 dígitos de la tarjeta o cuenta bancaria del cliente.
        **Ejemplo**: "Cuenta": "0025",
        "15-0": "EnviarCorreo",
        "15-1": "bolean",
        "15-2": "Opcional",
        "15-3": "Indica si deseas que el CFDI se envíe a tu cliente por correo electrónico. Por default esta opción es *true*.
        **Ejemplo**: "EnviarCorreo": "true",
        "16-0": "LugarExpedicion",
        "16-1": "string",
        "16-2": "Opcional",
        "16-3": "Indica el Código postal del lugar de expedición del CFDI. Éste debe tener* 5 caracteres*.
        **Ejemplo**: "LugarExpedicion": "44650"
    },
    "cols": 4,
    "rows": 17
}

```


#### Importante

Es necesario que envíes los valores (precios, cálculo de impuestos, subtotales, etc) de acuerdo a tus necesidades. Esto incluye número de decimales y redondeos.


#### Construcción de la URL

**Host**: https://facturaonline.com.mx
**Endpoint**:  /api/v3/cfdi33/create
**Ejemplo**:  https://factura.com/api/v3/cfdi33/create


#### Ejemplo

```

{
    "codes": [{
        "code": "<?php for ($x = 1; $x <= 1; $x++) {
            $Conceptos[] = [
                'ClaveProdServ' => '81112107',
                'Cantidad' => '1',
                'ClaveUnidad' => 'E48',
                'Unidad' => 'Unidad de servicio',
                'ValorUnitario' => '100',
                'Descripcion' => 'Desarrollo a la medida',
                'Descuento' => '0',
                'Impuestos' => [
                    'Traslados' => [[
                        'Base' => '100',
                        'Impuesto' => '002',
                        'TipoFactor' => 'Tasa',
                        'TasaOCuota' => '0.160000',
                        'Importe' => '16'
                    ],]
                ],
            ];
        }

        $ch = curl_init();
        $fields = [
            "Receptor" => ["UID" => "55c0fdc675XXX"],
            "TipoDocumento" => "factura",
            "UsoCFDI" => "P01",
            "Redondeo" => 2,
            "Conceptos" => $Conceptos,
            "FormaPago" => "01",
            "MetodoPago" => 'PUE',
            "Moneda" => "MXN",
            "CondicionesDePago" => "Pago en una sola exhibición",
            "Serie" => 1,
            "EnviarCorreo" => 'true',
            "InvoiceComments" => ""
        ];

        $jsonfield = json_encode($fields);
        curl_setopt($ch, CURLOPT_URL, "http://devfactura.in/api/v3/cfdi33/create");
        curl_setopt($ch, CURLOPT_RETURNTRANSFER, TRUE);
        curl_setopt($ch, CURLOPT_HEADER, FALSE);
        curl_setopt($ch, CURLOPT_POST, TRUE);
        curl_setopt($ch, CURLOPT_POSTFIELDS, $jsonfield);
        curl_setopt($ch, CURLOPT_HTTPHEADER, array(
            "Content-Type: application/json",
            "F-PLUGIN":  '9d4095c8f7ed5785cb14c0e3b033eeb8252416ed',
            "F-Api-Key": 'Ingresa API KEY',
            "F-Secret-Key": 'Ingresa SECRET KEY'
        ));
        $response = curl_exec($ch);
        return die($response);
        curl_close($ch); ?>",
        "language": "php",
        "name": "crear_cfdi.php"
    }]
}

```


#### Recuerda que

Para probar el código de ejemplo es necesario que reemplaces el texto  **Ingresa API KEY**  por el API KEY de tu cuenta, e **Ingresa SECRET KEY**  por el SECRET KEY correspondiente.


#### Importante

Por disposición del SAT los valores de traslados, descuentos, precios, etc, deberán tener **hasta 6 decimales**. El redondeo debe ser a **2 decimales**  y aplica solamente a subtotales, suma de traslados y suma de retenidos.


#### Respuesta

```

{
    "codes": [
        {
            "code": {
                "response": "success",
                "message": "Factura creada y enviada satisfactoriamente",
                "UUID": "8ff503a2-c6b7-4a25-XXX-a25610e6b488",
                "uid": "5c06fa8b3bbe6",
                "SAT": {
                    "UUID": "8ff503a2-c6b7-XXX-92c7-a25610e6b488",
                    "FechaTimbrado": "2018-12-04T16:07:08",
                    "NoCertificadoSAT": "20001000000300022323"
                    ,"Version": "1.1",
                    "SelloSAT": "lzlv2bEVsjx8XkiJHJvlfCjr7xJ/laxZnvSmGSKF3C/HI9WFDYFFk4NfGyILBj8ll7m1VoCqlkSLvu9dRex4jSSGfPJOPGDrx7w/4AOj/scHPU23uIPhztnaHIYHKg9UxP4L9rgX814msJ8V86IXZ1nY7akr77Cpf2c2yAnHaO1fm81oQIe32obIs2GrOey6JG9oxQNrcUawSXXXXXXXX",
                    "SelloCFD": "NJQH6WT8eLxAeti7pUWhB7F6C6xrdSqkFfORf3+SeGkhu+5E0cZZUQjgaSZLpPcgk01aQUf0Jayw2GewYou5MjD4OLzZnZuizPwy3cSfQXzgX6sJTtAsI00VyhQewxLYDSMqFUrPpniNQG8Nl/eEg1kx72kkmqih2KX2Z+URkhx14W7CMG2aMJnhDyZuyliF+cy3utjXwzxQMl+28A/mgnlfUXzZd/3IunTtxM/p4bpqbYinK+7Bd/n+90Z6axsFBs6N7wxUX6aK9YL58owhgVGXXXXXXXX"
                },
                "INV": {
                    "Serie": "F",
                    "Folio": 1433
                },
                "invoice_uid": "5c06fa8b3bXXX"
            },
            "language": "json",
            "name": "Respuesta exitosa"
        },
        {
            "code": {
                "response": "error",
                "message": {
                    "message": "CFDI33161 - El valor del campo Importe o que corresponde a Traslado no se encuentra entre el limite inferior y superior permitido.",
                    "messageDetail": "Comprobante:Concepto:Impuestos:Traslado:Importe: El Importe es mayor o menor al limite superior/inferior calculado. LimiteSuperiorCalculado: 17 LimiteInferiorCalculado: 15 Comprobante:Concepto:Impuestos:Traslado:Importe: 19",
                    "data": null,
                    "status": "error"
                },
                "xmlerror":"<cfdi:Traslados><cfdi:Impuestos><cfdi:Concepto><cfdi:Conceptos><cfdi:Traslados><cfdi:Impuestos><cfdi:Comprobante>"
            },
            "language": "json",
            "name": "Respuesta error "
        }
    ]
}

```

#### Sobre errores

El mensaje de error puede variar dependiendo el nodo en el que haya información incorrecta. Te sugerimos leer cuidadosamente el mensaje del error ya que en el mismo se indica donde es necesario corregir la información.
