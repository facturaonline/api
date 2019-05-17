#  Conceptos
A continuación se describen los atributos que deben incluirse en el nodo Conceptos.  
Para cada concepto es necesario incluir los siguientes atributos:

<table>
    <thead>
        <tr>
            <th>Parámetro</th>
            <th>Tipo</th>
            <th>Requerido</th>
            <th>Detalles</th>
        </tr>
    <thead>
    <tbody>
        <tr>
            <td>ClaveProdServ</td>
            <td>string</td>
            <td>Requerido</td>
            <td>Indica la clave del producto o servicio correspondiente a tu concepto. Es importante que ésta la tomes del catálogo indicado por el SAT para que sea válida.
            Ejemplo: "ClaveProdServ": "43232408"</td>
        </tr>
        <tr>
            <td>NoIdentificacion</td>
            <td>string</td>
            <td>Opcional</td>
            <td>Indica el número de identificación o SKU en caso de tenerlo.
            Ejemplo: "NoIdentificacion": "WEBDEV10"</td>
        </tr>
        <tr>
            <td>Cantidad</td>
            <td>number</td>
            <td>Requerido</td>
            <td>Indica la cantidad.
            Ejemplo: "Cantidad": 1</td>
        </tr>
        <tr>
            <td>ClaveUnidad</td>
            <td>string</td>
            <td>Requerido</td>
            <td>Indica la clave de la unidad  de medida correspondiente a tu concepto.
            Ejemplo: "ClaveUnidad": "E48"</td>
        </tr>
        <tr>
            <td>Unidad</td>
            <td>string</td>
            <td>Requerido</td>
            <td>Indica la unidad de medida. Ésta debe coincidir con la clave de la unidad ingresada en el parámetro anterior.
            Ejemplo: "Unidad": "Unidad de servicio"</td>
        </tr>
        <tr>
            <td>ValorUnitario</td>
            <td>string</td>
            <td>Requerido</td>
            <td>Indica el precio unitario sin incluir impuestos.
            Ejemplo: "ValorUnitario": "15000.00"</td>
        </tr>
        <tr>
            <td>Descripcion</td>
            <td>string</td>
            <td>Requerido</td>
            <td>Indica la descripción del concepto.
            Ejemplo: "Descripcion": "Desarrollo web a la medida"</td>
        </tr>
        <tr>
            <td>Descuento</td>
            <td>string</td>
            <td>Opcional</td>
            <td>Indica el importe del descuento, en caso de desear agregarlo.
            Ejemplo: "Descuento": "10.00"</td>
        </tr>
        <tr>
            <td>Impuestos</td>
            <td>array</td>
            <td>Opcional</td>
            <td>Indicar los impuestos (traslados, locales y retenidos) que tendrá el concepto.
            Ejemplo: "Impuestos": {
                "Traslados": [
                    {
                        "Base": "15000.000000",
                        "Impuesto": "002",
                        "TipoFactor": "Tasa",
                        "TasaOCuota": "0.16",
                        "Importe": "2400.000000"
                    }
                ],
                "Retenidos": [],
                "Locales": []
            }</td>
        </tr>
        <tr>
            <td>NumeroPedimento</td>
            <td>string</td>
            <td>Opcional</td>
            <td>Indica el número del pedimento correspondiente a la importación del bien.
            Ejemplo: "NumeroPedimento" : "15 48 3009 0001234"</td>
        </tr>
        <tr>
            <td>Predial</td>
            <td>string</td>
            <td>Opcional</td>
            <td>Indica el número de predial en caso de ser necesario.
            Ejemplo: "Predial": "56485422"</td>
        </tr>
        <tr>
            <td>Partes</td>
            <td>array</td>
            <td>Opcional</td>
            <td>Indica las partes o componentes que integran la totalidad del concepto.</td>
        </tr>
    </tbody>
</table>


#### Ejemplo

```

"Conceptos": [
    {
        "ClaveProdServ": "43232408",
        "NoIdentificacion": "WEBDEV10",
        "Cantidad": "1.000000",
        "ClaveUnidad": "E48",
        "Unidad": "Unidad de servicio",
        "Descripcion": "Desarrollo web a la medida",
        "ValorUnitario": "15000.000000",
        "Importe": "15000.000000",
        "Descuento": "0",
        "tipoDesc": "porcentaje",
        "honorarioInverso": "",
        "montoHonorario": "0",
        "Impuestos": {
            "Traslados": [
                {
                    "Base": "15000.000000",
                    "Impuesto": "002",
                    "TipoFactor": "Tasa",
                    "TasaOCuota": "0.16",
                    "Importe": "2400.000000"
                }
            ],
            "Retenidos": [],
            "Locales": []
        },
        "NumeroPedimento": "",
        "Predial": "",
        "Partes": "0",
        "Complemento": "0"
    }
]

```
