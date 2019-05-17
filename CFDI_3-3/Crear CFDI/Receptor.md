# Receptor

A continuación se describen los atributos que deben incluirse en el nodo Receptor.


#### Importante

El receptor debe incluir los siguientes atributos:

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
            <td>UID</td>
            <td>string</td>
            <td>Requerido</td>
            <td>Indica el UID del receptor del CFDI.
            Ejemplo: "UID": "55c0fdc67593d"</td>
        </tr>
        <tr>
            <td>ResidenciaFiscal</td>
            <td>string</td>
            <td>Opcional</td>
            <td>Indicar el número de residencia fiscal cuando el receptor del comprobante sea un residente en el extranjero. Ejemplo: "ResidenciaFiscal": "5256452".</td>
        </tr>
    </tbody>
</table>


#### Ejemplo

```

"Receptor": {
    "ResidenciaFiscal": "",
    "UID": "55c0fdc67593d"
}

```
