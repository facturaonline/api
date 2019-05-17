# CFDIs relacionados

Este nodo es opcional y se utiliza para especificar los CFDIs con los que se encuentra relacionado el CFDI que se está timbrando.

**Ejemplo**:
Si tu CFDI está sustituyendo a un CFDI timbrado y cancelado anteriormente al mismo receptor, entonces deberás indicar en este el UID y el tipo de relación que existe entre ambos.

A continuación se describen los atributos que conforman el nodo **CfdiRelacionados**:


#### Recuerda

El nodo CfdiRelacionados es opcional, en caso de agregarlo es necesario hacerlo dentro del objeto pincipal que se enviará en la petición.  
El nodo de CfdiRelacionados se conforma de los siguientes atributos:

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
            <td>TipoRelacion</td>
            <td>string</td>
            <td>Requerido</td>
            <td>Indicar la clave del tipo de relación correspondiente.
            [Revisar el listado de claves proporcionado por el SAT.](https://facturaonline.com.mx/docs/tipo-de-relaci%C3%B3n).
            Ejemplo:"TipoRelacion": "01"</td>
        </tr>
        <tr>
            <td>UUID</td>
            <td>Array</td>
            <td>Requerido</td>
            <td>Indicar el o los UID de los CFDIS con los que se relaciona el actual.
            Ejemplo: "UUID": [
                "29c98cb2-f72a-4cbe-a297-606da335e187",
                "a96f6b9a-70aa-4f2d-bc5e-d54fb7371236"
            ]</td>
        </tr>
    </tbody>
</table>


#### Ejemplo

```

"CfdiRelacionados": {
    "TipoRelacion": "01",
    "UUID": [
        "29c98cb2-f72a-4cbe-a297-606da335e187",
        "a96f6b9a-70aa-4f2d-bc5e-d54fb7371236"
    ]
}

```
