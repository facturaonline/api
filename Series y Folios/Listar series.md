# Listar series

A continuación se explica como listar las series , con un ejemplo y muestra de posibles respuestas obtenidas.  
Podemos consultar los folios de todas las series de la empresa.


#### Construcción de la URL

**Host**: https://facturaonline.com.mx  
**Endpoint**:  /api/v1/series  
**Ejemplo**:  https://facturaonline.com.mx/api/v1/series  


#### Ejemplo

```

{
    "codes": [
        {
            "code": "<?php
            $ch = curl_init();
            curl_setopt($ch, CURLOPT_URL, "http://devfactura.in/api/v1/series");
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
            ",
            "language": "php",
            "name": "listar_series.php"
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
            "code": "{
                "status": "success",
                "data": [
                {
                    "SerieID": 1247,
                    "SerieName": "CED",
                    "SerieType": "F"
                },
                {
                    "SerieID": 1098,
                    "SerieName": "CONCEPT",
                    "SerieType": "F"
                    },
                    {
                        "SerieID": 1598,
                        "SerieName": "DUPLI",
                        "SerieType": "F"
                    },
                    {
                        "SerieID": 1,
                        "SerieName": "F",
                        "SerieType": "F"
                    },
                ]
            }",
            "language": "json",
            "name": "respuesta exitosa"
        }
    ]
}

```


#### Sobre errores

El mensaje de error puede variar dependiendo el nodo en el que haya información incorrecta.  
Te sugerimos leer cuidadosamente el mensaje del error ya que en el mismo se indica donde es necesario corregir la información.
