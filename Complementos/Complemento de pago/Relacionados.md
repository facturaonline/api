# Relacionados

A continuación se describen los atributos que deben incluirse en el nodo Relacionados dentro del nodo Complemento.


#### Recuerda

El nodo **Relacionados** debe incluirse dentro del nodo **Pagos**.  
El nodo relacionados se conforma de un arreglo de objetos, cada uno de éstos con los siguientes atributos:

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
            <td>IdDocumento</td>
            <td>string</td>
            <td>Requerido</td>
            <td>Indica el folio fiscal del CFDI al que quieras agregarle un pago.
            Ejemplo:"IdDocumento": "54feddcf-af15-4715-8a1f-80a122d1db54"</td>
        </tr>
        <tr>
            <td>MonedaDR</td>
            <td>decimal</td>
            <td>Requerido</td>
            <td>Indica la clave de la moneda indicada en el CFDI al que deseas agregarle el pago.
            Ejemplo:"MonedaDR": "MXN"</td>
        </tr>
        <tr>
            <td>TipoCambioDR</td>
            <td>decimal</td>
            <td>Opcional</td>
            <td>Indica el tipo de cambio si es que la moneda del CFDI es diferente de MXN.
            Ejemplo:"TipoCambioDR": "19.25"</td>
        </tr>
        <tr>
            <td>MetodoDePagoDR</td>
            <td>string</td>
            <td>Requerido</td>
            <td>Indica la clave correspondiente al método de pago, Éste siempre debe ser PPD.
            Ejemplo:"MetodoDePagoDR": "PPD"</td>
        </tr>
        <tr>
            <td>NumParcialidad</td>
            <td>string</td>
            <td>Opcional</td>
            <td>Indica el número de pago o abono que corresponde. En caso de ser el primer pago poner 1.
            Ejemplo:"NumParcialidad": 5</td>
        </tr>
        <tr>
            <td>ImpSaldoAnt</td>
            <td>Number</td>
            <td>Requerido</td>
            <td>Indica el monto del saldo pendiente de la parcialidad anterior. En el caso de que sea la primer parcialidad este campo debe contener el importe total del documento relacionado.
            Ejemplo:"ImpSaldoAnt": 1000</td>
        </tr>
        <tr>
            <td>ImpPagado</td>
            <td>Number</td>
            <td>Requerido</td>
            <td>Indica el importe del abono que se está haciendo actualmente al CFDI.
            Ejemplo:"ImpPagado": 1000</td>
        </tr>
        <tr>
            <td>ImpSaldoInsoluto</td>
            <td>Number</td>
            <td>Requerido</td>
            <td>Indica el monto del saldo pendiente por pagar. Es la diferencia entre el Saldo anterior y el monto de pago.
            Ejemplo:"ImpSaldoInsoluto": 0</td>
        </tr>
    </tbody>
</table>

```

"relacionados":[
    {
        "IdDocumento" :	"54feddcf-af15-4715-8a1f-80a122d1db54",
        "ImpPagado" :	"1000",
        "ImpSaldoAnt" :	"1000",
        "ImpSaldoInsoluto" : "0",
        "MetodoDePagoDR":	"PPD",
        "MonedaDR":	"MXN",
        "NumParcialidad":	"5",
        "TipoCambioDR":	"19.25"
    }
]

```
