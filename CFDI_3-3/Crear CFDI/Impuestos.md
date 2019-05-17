# Impuestos
A continuación se describen los atributos que deben incluirse en el nodo Impuestos.


#### Recuerda

El nodo **Impuestos**  debe incluirse dentro de cada concepto agregado en el nodo **Conceptos**.  
El nodo de impuestos  se conforma de los siguientes atributos:

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
            <td>Traslados</td>
            <td>array</td>
            <td>Requerido  Es requerido siempre y cuando la factura lleve el tipo de impuesto Traslado.</td>
            <td>Indica los impuestos trasladados que se aplican a tu concepto.
            Ejemplo: "Traslados": [
                {
                    "Base": "15000.00",
                    "Impuesto": "002",
                    "TipoFactor": "Tasa",
                    "TasaOCuota": "0.16",
                    "Importe": "2400.00"
                }
            ],</td>
        </tr>
        <tr>
            <td>Retenidos</td>
            <td>array</td>
            <td>Requerido  Es requerido siempre y cuando la factura lleve el tipo de impuesto Retenciones.</td>
            <td>Indica los impuestos retenidos que se aplican a tu concepto.
            Ejemplo: "Retenidos": [
                {
                    "Base": "15000.00",
                    "Impuesto": "002",
                    "TipoFactor": "Tasa",
                    "TasaOCuota": "0.16",
                    "Importe": "2400.00"
                }
            ],</td>
        </tr>
        <tr>
            <td>Locales</td>
            <td>array</td>
            <td>Requerido  Es requerido siempre y cuando la factura lleve el tipo de impuesto Locales.</td>
            <td>Indica los impuestos locales que se aplican a tu concepto.
            Ejemplo: "Locales": [
                {
                    "Impuesto": "ISH",
                    "TasaOCuota": "0.05"
                }
            ]</td>
        </tr>
    </tbody>
</table>


#### Atributos de los nodos Traslados y Retenidos

A continuación se describen los nodos que componen cada impuesto que desees agregar a tu concepto.  
Un concepto puede tener más de un traslado y más de una retención. Cada impuesto debe incluirse dentro de un objeto, que a su vez es contenido por en el arreglo del tipo de impuesto correspondiente.

Los impuestos que pueden incluirse dentro de **traslados** son:

* IVA
* IEPS

Los impuestos que pueden incluirse dentro de **retenciones** son:
* IVA
* ISR


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
            <td>Base</td>
            <td>float</td>
            <td>Requerido</td>
            <td>Indica el valor sobre el cual se calculará el impuesto.
            Ejemplo: "Base": "15000.00"</td>
        </tr>
        <tr>
            <td>Impuesto</td>
            <td>string</td>
            <td>Requerido</td>
            <td>Indica la clave correspondiente al impuesto que deseas agregar. Consultar el catálogo de claves de Impuestos.
            Ejemplo: "Impuesto": "002"</td>
        </tr>
        <tr>
            <td>TipoFactor</td>
            <td>string</td>
            <td>Requerido</td>
            <td>Indica tipo de factor correspondiente al impuesto que deseas agregar. Consultar el catálogo de Tipo factor.
            Ejemplo: "TipoFactor": "Tasa"</td>
        </tr>
        <tr>
            <td>TasaOCuota</td>
            <td>float</td>
            <td>Requerido</td>
            <td>Indica la tasa o cuota correspondiente al impuesto que deseas agregar.  Consultar el catálogo de Tasa o cuota.
            Ejemplo: "TasaOCuota": "0.16"</td>
        </tr>
        <tr>
            <td>Importe</td>
            <td>float</td>
            <td>Requerido</td>
            <td>Indica el importe del impuesto trasladado que aplica a cada concepto. No se permiten valores negativos.
            Ejemplo: "Importe": "2400.00"</td>
        </tr>
    </tbody>
</table>


#### Atributos del nodo Locales

A continuación se describen los nodos que componen los impuestos locales:

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
            <td>Impuesto</td>
            <td>string</td>
            <td>Requerido</td>
            <td>Indica el impuesto que deseas agregar, éste puede ser CEDULAR o ISH.
            Ejemplo: "Impuesto": "CEDULAR</td>
        </tr>
        <tr>
            <td>TasaOCuota</td>
            <td>float</td>
            <td>Requerido</td>
            <td>Indica el valor de la tasa o cuota del impuesto que deseas agregar.
            Ejemplo: "TasaOCuota": "0.05"</td>
        </tr>
    </tbody>
</table>


#### Recuerda

Por disposición del SAT un concepto no puede tener **ISH** e **IEPS** al mismo tiempo. Por favor valida tus conceptos para evitar errores al momento de timbrar.


#### Ejemplo

```

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
    "Retenidos": [
        {
            "Base": "15000.000000",
            "Impuesto": "002",
            "TipoFactor": "Tasa",
            "TasaOCuota": "0.16",
            "Importe": "2400.000000"
        }
    ],
    "Locales": [
        {
            "Impuesto": "CEDULAR",
            "TasaOCuota": "0.05",
        }
    ]
}

```
