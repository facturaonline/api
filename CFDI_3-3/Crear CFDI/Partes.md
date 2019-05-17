# Partes

Este nodo es opcional y se utiliza para especificar los componentes de un concepto.

**Ejemplo**:
Si tu concepto es un *kit de herramientas*,  en el nodo partes puedes especificar los elementos que conforman ese kit como: martillo, desarmador, pienzas,etc.

A continuación se describen los atributos que conforman el nodo Partes:


#### Recuerda

El nodo **Partes** es opcional, en caso de agregarlo es necesario hacerlo dentro de uno (o varios) conceptos en el nodo  **Conceptos**.  
El nodo de Partes se conforma de los siguientes atributos:

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
            <td>Indica la clave del producto o servicio correspondiente a tu concepto. Es importante que ésta la tomes del catálogo proveído por el SAT para que sea válida.
            Ejemplo:"ClaveProdServ": "43232408"</td>
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
            <td>Indica la cantidad.Ejemplo:'Cantidad' : 1</td>
        </tr>
        <tr>
            <td>ClaveUnidad</td>
            <td>string</td>
            <td>Requerido</td>
            <td>Indica la clave de la unidad  de medida correspondiente a tu concepto.
            [Consulta el listado de claves válidas para el SAT.](https://facturaonline.com.mx/docs/unidad).
            Ejemplo:"ClaveUnidad": "E48"</td>
        </tr>
        <tr>
            <td>Unidad</td>
            <td>string</td>
            <td>Requerido</td>
            <td>Indica la unidad de medida. Ésta debe coincidir con la clave de la unidad ingresada en el parámetro anterior.
            [Consulta el listado de claves válidas para el SAT.](https://facturaonline.com.mx/docs/unidad).
            Ejemplo: "Unidad": "Unidad de servicio"</td>
        </tr>
        <tr>
            <td>ValorUnitario</td>
            <td>float</td>
            <td>Requerido</td>
            <td>Indica el precio unitario sin incluir impuestos.Ejemplo: "ValorUnitario": "15000.00"</td>
        </tr>
        <tr>
            <td>Descripcion</td>
            <td>string</td>
            <td>Requerido</td>
            <td>Indica la descripción del concepto.Ejemplo:"Descripcion": "Desarrollo web a la medida"</td>
        </tr>
    </tbody>
</table>


#### Ejemplo

```

"Partes":[
    {
        "ClaveProdServ": "43232408",
        "NoIdentificacion":"WEBDEV10",
        "Cantidad":"1",
        "ClaveUnidad": "E48",
        "Unidad": "Unidad de servicio",
        "ValorUnitario": "15000.00",
        "Descripcion": "Desarrollo web a la medida"
    }
]

```
