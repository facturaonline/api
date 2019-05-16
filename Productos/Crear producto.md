# Crear producto

A continuación se explica como dar de alta un nuevo producto.  
Podemos crear un nuevo producto haciendo uso de los siguientes parámetros:

```

{
    "data": {
        "h-0": "Parámetro",
        "h-1": "Tipo",
        "h-2": "Requerido",
        "h-3": "Detalles",
        "0-0": "code",
        "1-0": "name",
        "0-1": "string",
        "1-1": "string",
        "0-2": "Opcional",
        "1-2": "Requerido",
        "0-3": "Indica el código o SKU de tu producto.",
        "1-3": "Indica el nombre de tu producto.
        Éste nombre se mostrará en el apartado de **Conceptos** de tu CFDI.",
        "2-0": "price",
        "3-0": "clavePS",
        "4-0": "unity",
        "5-0": "claveUnity",
        "2-1": "numeric",
        "3-1": "string",
        "4-1": "string",
        "5-1": "string",
        "2-2": "Requerido",
        "3-2": "Requerido",
        "4-2": "Requerido",
        "5-2": "Requerido",
        "2-3": "Indica el  precio **sin IVA** de tu producto o servicio.",
        "3-3": "Indica la clave del producto o servicio correspondiente a tu concepto.
        Consulta el catálogo de **Clave Producto/Servicio **.",
        "4-3": "Indica la unidad de medida, ésta debe corresponder a la clave indicada en el atributo **claveUnity** .
        [Consulta el catálogo de **Clave Unidad **.](https://facturaonline.com.mx/docs/unidad)",
        "5-3": "Indica la clave de la unidad de medida, ésta debe corresponder a la unidad indicada en el atributo **unity** .
        [Consulta el catálogo de **Clave Unidad **.](https://facturaonline.com.mx/docs/unidad)"
    },
    "cols": 4,
    "rows": 6
}

```


#### Construcción de la URL

**Host**: https://facturaonline.com.mx  
**Endpoint**:  /api/v3/products/create  
**Ejemplo**:  https://facturaonline.com.mx/api/v3/products/create  


#### Ejemplo

```

{
    "codes": [
        {
            "code": "<?php
            $ch = curl_init();
            curl_setopt($ch, CURLOPT_URL, "https://facturaonline.com.mx/api/v3/products/create");
            curl_setopt($ch, CURLOPT_RETURNTRANSFER, TRUE);
            curl_setopt($ch, CURLOPT_HEADER, FALSE);
            curl_setopt($ch, CURLOPT_POST, TRUE);
            curl_setopt($ch, CURLOPT_POSTFIELDS, "{
                "code": "K001",
                "name": "Desarrollo de banner para publicidad",
                "price": 35.9,
                "clavePS": "1154544511",
                "unity": "Unidad de servicio",
                "claveUnity": "E48"
            }");
            curl_setopt($ch, CURLOPT_HTTPHEADER, array(
                "Content-Type: application/json",
                "F-PLUGIN: " . '9d4095c8f7ed5785cb14c0e3b033eeb8252416ed',
                "F-Api-Key: ". 'Ingresa API KEY',
                "F-Secret-Key: " . 'Ingresa SECRET KEY'
            ));
            $response = curl_exec($ch);
            curl_close($ch);
            var_dump($response);",
            "language": "php",
            "name": "crear_productos.php"
        }
    ]
}

```


#### Recuerda

Para probar el código de ejemplo es necesario que reemplaces el texto  **Ingresa API KEY**  por el API KEY de tu cuenta, e **Ingresa SECRET KEY**  por el SECRET KEY correspondiente.


#### Respuesta

```

{
    "codes": [
        {
            "code": "[
                {
                    "status": "success",
                    "data": [
                        {
                            "code": "Ferreteria Perez",
                            "name": "XAXX010101000",
                            "sku": "Av. Juarez",
                            "price": "1234",
                            "clavePS": "",
                            "unity": "Centro",
                            "claveUnity": "44640"
                        }
                    ]
                }
            ]",
            "language": "json",
            "name": "respuesta exitosa"
        }
    ]
}

```


#### Sobre errores

El mensaje de error puede variar dependiendo el nodo en el que haya información incorrecta.  
Te sugerimos leer cuidadosamente el mensaje del error ya que en el mismo se indica donde es necesario corregir la información.
