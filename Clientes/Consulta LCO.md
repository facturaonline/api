# Consulta LCO

A continuación se explica como consultar el RFC de tu cliente en la lista de la LCO (Lista de Contribuyentes con Obligación ante el SAT), con un ejemplo y muestra de posibles respuestas obtenidas.  
Servicio para identificar que los RFC (emisores y receptores) que intervienen en el proceso sean válidos, es decir que estén en la LCO (Lista de Contribuyentes con Obligación ante el SAT).


#### Construcción de la URL

**Host**: https://facturaonline.com.mx  
**Endpoint**:  /api/v1/clients/lco/{RFC}  
**Ejemplo**:  https://facturaonline.com.mx/api/v1/clients/lco/{RFC}  


#### Ejemplo

```

<?php
$ch = curl_init();

curl_setopt($ch, CURLOPT_URL, "https://facturaonline.com.mx/api/v1/clients/lco/XAXX010101000");
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
        "message": "El RFC se encuentra el la lista de LCO (Lista de Contribuyentes con Obligación ante el SAT)."
    }
]

```


#### Respuesta error

```

[
    {
        "status": "error",
        "message": "El RFC no se encuentra el la lista de LCO (Lista de Contribuyentes con Obligación ante el SAT), no podrás facturar a este RFC."
    }
]

```


#### Sobre errores

El mensaje de error puede variar dependiendo el nodo en el que haya información incorrecta.  
Te sugerimos leer cuidadosamente el mensaje del error ya que en el mismo se indica donde es necesario corregir la información.
