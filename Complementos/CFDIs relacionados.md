# CFDIs relacionados

Este nodo es opcional y se utiliza para especificar cuando un complemento de pago está sustituyendo a otro.  
A continuación se describen los atributos que conforman el nodo **CfdiRelacionados**:


#### Recuerda

El nodo **CfdiRelacionados** es **opcional**, en caso de agregarlo es necesario hacerlo dentro del **objeto pincipal **que se enviará en la petición y en este caso el tipo de relación siempre debe ser:
**04** -Sustitución.  

El nodo de CfdiRelacionados se conforma de los siguientes atributos:

```

{
    "data": {
        "h-0": "Parámetro",
        "h-1": "Tipo",
        "h-2": "Requerido",
        "h-3": "Detalles",
        "0-0": "TipoRelacion",
        "1-0": "UUID",
        "0-1": "string",
        "1-1": "Array",
        "0-2": "Requerido",
        "1-2": "Requerido",
        "0-3": "Indicar la clave del tipo de relación correspondiente.
        Revisar el listado de claves proporcionado por el SAT.
        **Ejemplo**:
        "TipoRelacion": "04"",
        "1-3": "Indicar el o los UID de los CFDIS con los que se relaciona el actual.
        **Ejemplo**:
        "UUID": [
            "29c98cb2-f72a-4cbe-a297-606da335e187",
            "a96f6b9a-70aa-4f2d-bc5e-d54fb7371236"
        ]"
    },
    "cols": 4,
    "rows": 2
}

```


#### Ejemplo

```

{
    "codes": [
        {
            "code": ""CfdiRelacionados": {
                "TipoRelacion": "04",
                "UUID": [
                "29c98cb2-f72a-4cbe-a297-606da335e187",
                "a96f6b9a-70aa-4f2d-bc5e-d54fb7371236"
                ]
            },",
            "language": "json",
            "name": "cfdi_relacionados.json"
        }
    ]
}

```
