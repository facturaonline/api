# Listar productos

A continuación se explica como listar los productos, con un ejemplo y muestra de posibles respuestas obtenidas.  
Podemos consultar los productos que tenemos dados de alta, o filtrar por algunos parámetros:

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
            <td>page</td>
            <td>int</td>
            <td>Opcional</td>
            <td>Indica número de página a consultar, por default posiciona en la página 1.</td>
        </tr>
        <tr>
            <td>per_page</td>
            <td>int</td>
            <td>Opcional</td>
            <td><Indica el limite de resultados para mostrar, por default retorna 100 registros./td>
        </tr>
    </tbody>
</table>


#### Construcción de la URL

**Host**: https://facturaonline.com.mx  
**Endpoint**:  /api/v3/products/list  
**Ejemplo**:  https://facturaonline.com.mx/api/v3/products/list  


#### Ejemplo

```


<?php
$ch = curl_init();

curl_setopt($ch, CURLOPT_URL, "https://facturaonline.com.mx/api/v3/products/list");
curl_setopt($ch, CURLOPT_RETURNTRANSFER, TRUE);
curl_setopt($ch, CURLOPT_HEADER, FALSE);

curl_setopt($ch, CURLOPT_HTTPHEADER, array(
    "Content-Type: application/json",
    "F-PLUGIN: " . '9d4095c8f7ed5785cb14c0e3b033eeb8252416ed',
    "F-Api-Key: ".'Ingresa API KEY',
    "F-Secret-Key: " .'Ingresa SECRET KEY'
));

$response = curl_exec($ch);

curl_close($ch);

var_dump($response);

```


#### Recuerda

Para probar el código de ejemplo es necesario que reemplaces el texto  **Ingresa API KEY**  por el API KEY de tu cuenta, e **Ingresa SECRET KEY**  por el SECRET KEY correspondiente.


#### Respuesta exitosa

```

[
    {
        "status": "success",
        "total": 4,
        "per_page": 100,
        "current_page": 1,
        "last_page": 1,
        "from": 1,
        "to": 4,
        "data": [
            {
                "code": "59fa4f114751d",
                "name": "Servicio técnico de orientación",
                "price": 1048.95,
                "sku": "sku-003",
                "unidad": "Unidad de servicio",
                "claveprodserv": "43232107",
                "claveunidad": "E48"
            },
            {
                "code": "59ea2a6886b4e",
                "name": "SERVICIO DE HOSPEDAJE PARA ELEMENTOS DEL SERVICIO DE PROTECCION FEDERAL DEL 01 AL 09 DE OCTUBRE",
                "price": 100,
                "sku": "HOSP2",
                "unidad": "Segundo [unidad de ángulo]",
                "claveprodserv": "22101708",
                "claveunidad": "D62"
            },
            {
                "code": "59ee370e03253",
                "name": "Prubea de sin catalgo",
                "price": 123,
                "sku": "12212121",
                "unidad": "Radián",
                "claveprodserv": "0",
                "claveunidad": "C81"
            },
            {
                "code": "59ee7312578f1",
                "name": "Producto de servicio de divisas",
                "price": 8888,
                "sku": "4533",
                "unidad": "Valor monetario",
                "claveprodserv": "84121603",
                "claveunidad": "M4"
            }
        ]
    }
]

```


#### Sobre errores

El mensaje de error puede variar dependiendo el nodo en el que haya información incorrecta.  
Te sugerimos leer cuidadosamente el mensaje del error ya que en el mismo se indica donde es necesario corregir la información.
