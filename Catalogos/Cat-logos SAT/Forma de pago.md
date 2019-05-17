# Forma de pago

Consulta el catálogo de formas de pago.


#### Construcción de la URL

**Host**: https://facturaonline.com.mx  
**Endpoint**:  /api/v3/catalogo/FormaPago  
**URL completa**:  https://facturaonline.com.mx/api/v3/catalogo/FormaPago  


#### Ejemplo

```

<?php
$ch = curl_init();

curl_setopt($ch, CURLOPT_URL, "https://factura.com/api/v3/catalogo/FormaPago");
curl_setopt($ch, CURLOPT_RETURNTRANSFER, TRUE);
curl_setopt($ch, CURLOPT_HEADER, FALSE);

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


#### Recuerda

Para probar el código de ejemplo es necesario que reemplaces el texto** Ingresa API KEY** por el **API KEY** de tu cuenta, e **Ingresa SECRET KEY** por el **SECRET KEY** correspondiente.


#### Respuesta

```

{
    "response": "success",
    "data": [
        {
            "key": "01",
            "name": "Efectivo"
        },
        {
            "key": "02",
            "name": "Cheque nominativo"
        },
        {
            "key": "03",
            "name": "Transferencia electrónica de fondos"
        },
        {
            "key": "04",
            "name": "Tarjeta de crédito"
        },
        {
            "key": "05",
            "name": "Monedero electrónico"
        }
        ...        
    ]
}

```
