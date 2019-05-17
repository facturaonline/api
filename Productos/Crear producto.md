# Crear producto

A continuación se explica como dar de alta un nuevo producto.  
Podemos crear un nuevo producto haciendo uso de los siguientes parámetros:

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
            <td>code</td>
            <td>string</td>
            <td>Opcional</td>
            <td>Indica el código o SKU de tu producto.</td>
        </tr>
        <tr>
            <td>name</td>
            <td>string</td>
            <td>Requerido</td>
            <td>Indica el nombre de tu producto.
            Éste nombre se mostrará en el apartado de Conceptos de tu CFDI.</td>
        </tr>
        <tr>
            <td>price</td>
            <td>numeric</td>
            <td>Requerido</td>
            <td>Indica el precio sin IVA de tu producto o servicio.</td>
        </tr>
        <tr>
            <td>clavePS</td>
            <td>string</td>
            <td>Requerido</td>
            <td>Indica la clave del producto o servicio correspondiente a tu concepto.
            Consulta el catálogo de Clave Producto/Servicio .</td>
        </tr>
        <tr>
            <td>unity</td>
            <td>string</td>
            <td>Requerido</td>
            <td>Indica la unidad de medida, ésta debe corresponder a la clave indicada en el atributo claveUnity.</td>
        </tr>
        <tr>
            <td>claveUnity</td>
            <td>string</td>
            <td>Requerido</td>
            <td>Indica la clave de la unidad de medida, ésta debe corresponder a la unidad indicada en el atributo unity.</td>
        </tr>
    </tbody>
</table>


#### Construcción de la URL

**Host**: https://facturaonline.com.mx  
**Endpoint**:  /api/v3/products/create  
**Ejemplo**:  https://facturaonline.com.mx/api/v3/products/create  


#### Ejemplo

```

<?php
$ch = curl_init();

curl_setopt($ch, CURLOPT_URL, "https://facturaonline.com.mx/api/v3/products/create");
curl_setopt($ch, CURLOPT_RETURNTRANSFER, TRUE);
curl_setopt($ch, CURLOPT_HEADER, FALSE);

curl_setopt($ch, CURLOPT_POST, TRUE);

curl_setopt($ch, CURLOPT_POSTFIELDS, "{
    \"code\": \"K001\",
    \"name\": \"Desarrollo de banner para publicidad\",
    \"price\": 35.9,
    \"clavePS\": \"1154544511\",
    \"unity\": \"Unidad de servicio\",
    \"claveUnity\": \"E48\"
    }");

curl_setopt($ch, CURLOPT_HTTPHEADER, array(
    "Content-Type: application/json",
    "F-PLUGIN: " . '9d4095c8f7ed5785cb14c0e3b033eeb8252416ed',
    "F-Api-Key: ". 'Ingresa API KEY',
    "F-Secret-Key: " . 'Ingresa SECRET KEY'
));

$response = curl_exec($ch);

curl_close($ch);

var_dump($response);

```


#### Recuerda exitosa

Para probar el código de ejemplo es necesario que reemplaces el texto  **Ingresa API KEY**  por el API KEY de tu cuenta, e **Ingresa SECRET KEY**  por el SECRET KEY correspondiente.


#### Respuesta

```

[
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
]

```


#### Sobre errores

El mensaje de error puede variar dependiendo el nodo en el que haya información incorrecta.  
Te sugerimos leer cuidadosamente el mensaje del error ya que en el mismo se indica donde es necesario corregir la información.
