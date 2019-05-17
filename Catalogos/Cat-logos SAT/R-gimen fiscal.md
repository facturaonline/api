# Régimen fiscal

Consulta el catálogo de régimen fiscal.


#### Construcción de la URL

**Host**: https://facturaonline.com.mx  
**Endpoint**:  /api/v3/catalogo/RegimenFiscal  
**URL completa**:  https://facturaonline.com.mx/api/v3/catalogo/RegimenFiscal  


#### Ejemplo

```

<?php
$ch = curl_init();

curl_setopt($ch, CURLOPT_URL, "https://factura.com/api/v3/catalogo/RegimenFiscal");
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
            "key": "601",
            "name": "General de Ley Personas Morales"
        },
        {
            "key": "603",
            "name": "Personas Morales con Fines no Lucrativos"
            },
        {
            "key": "605",
            "name": "Sueldos y Salarios e Ingresos Asimilados a Salarios"
        },
        {
            "key": "606",
            "name": "Arrendamiento"
        },
        {
            "key": "608",
            "name": "Demás ingresos"
        }
        ...
    ]
}

```
