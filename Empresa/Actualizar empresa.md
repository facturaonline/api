# Actualizar empresa

A continuación se explica como actualizar los datos de una empresa dada de alta en Facturaonline.com.mx.  
Para actualizar la información de una empresa es necesario enviar los siguientes parámetros:

```

{
    "data": {
        "h-0": "Parámetro",
        "h-1": "Tipo",
        "h-2": "Requerido",
        "0-3": "Indica la Razón social de la empresa.",
        "0-0": "razons",
        "0-1": "string",
        "0-2": "Requerido",
        "1-0": "rfc",
        "2-0": "regimen",
        "3-0": "calle",
        "4-0": "numero_exterior",
        "5-0": "numero_interior",
        "6-0": "codpos",
        "7-0": "colonia",
        "8-0": "estado",
        "9-0": "ciudad",
        "10-0": "delegacion",
        "11-0": "email",
        "1-1": "string",
        "2-1": "string",
        "3-1": "string",
        "7-1": "string",
        "8-1": "string",
        "9-1": "string",
        "10-1": "string",
        "11-1": "string",
        "4-1": "int",
        "5-1": "int",
        "6-1": "numeric",
        "1-2": "Requerido",
        "3-2": "Requerido",
        "4-2": "Requerido",
        "6-2": "Requerido",
        "7-2": "Requerido",
        "8-2": "Requerido",
        "9-2": "Requerido",
        "11-2": "Requerido",
        "2-2": "Opcional",
        "5-2": "Opcional",
        "10-2": "Opcional",
        "1-3": "Indica el **RFC** de la empresa con **min:12** y **max:13**  caracteres.",
        "2-3": "Indica el código del régimen fiscal al que pertenece tu empresa
        [Consulta las claves de Régimen fiscal válidas](https://developers.facturaonline.com.mx/docs/r%C3%A9gimen-fiscal).",
        "3-3": "Indica el domicilio fiscal.",
        "4-3": "Indica el número exterior.",
        "5-3": "Indica el número interior.",
        "6-3": "Indica el código postal.
        Éste debe ser de 5 caracteres.",
        "7-3": "Indica la colonia.",
        "8-3": "Indica el estado.",
        "9-3": "Indica la ciudad.",
        "10-3": "Indica la delegación en caso de contar con ella.",
        "11-3": "Indica el Email."
    },
    "cols": 4,
    "rows": 12
}

```


#### Construcción de la URL

**Host**: https://facturaonline.com.mx  
**Endpoint**:  /api/v1/account/client_uid/update  
**Ejemplo**:  https://facturaonline.com.mx/api/v1/account/client_uid/update  


#### Ejemplo

```

{
    "codes": [
        {
            "code": "<?php
            $ch = curl_init();
            curl_setopt($ch, CURLOPT_URL, "https://facturaonline.com.mx/api/v1/account/client_uid/update");
            curl_setopt($ch, CURLOPT_RETURNTRANSFER, TRUE);
            curl_setopt($ch, CURLOPT_HEADER, FALSE);
            curl_setopt($ch, CURLOPT_POST, TRUE);
            curl_setopt($ch, CURLOPT_POSTFIELDS, "{
                "razons": "Ferreteria Perez",
                "rfc": "XAXX010101000",
                "regimen": "611",
                "calle": "Av. Juarez",
                "numero_exterior": 1234,
                "numero_interior": "4",
                "codpos": 44640,
                "colonia": "Centro",
                "estado": "Jalisco",
                "ciudad": "Guadalajara",
                "delegaion": "",
                "email": "josepe@email.com"
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
            ",
            "language": "php",
            "name": "detalles_empresa.php"
        }
    ]
}

```


#### Recuerda

Para probar el código de ejemplo es necesario que reemplaces el texto  **Ingresa API KEY**  por el API KEY de tu cuenta, e **Ingresa SECRET KEY**  por el SECRET KEY correspondiente.  
Además reemplazar el **client_uid**  en la URL.


#### Respuesta

```

{
    "codes": [
        {
            "code": "[
                {
                    "status": "success",
                    "data": {
                        "uid": "5670a524cfc65",
                        "razon_social": "EMPRESA DEMOSTRACION",
                        "rfc": "XAXX010101000",
                        "regimen_fiscal": "611",
                        "calle": "Av. Ficticia",
                        "exterior": "4587",
                        "interior": 7,
                        "colonia": "Centro",
                        "codpos": "44987",
                        "ciudad": "Guadalajara",
                        "estado": "Jalisco",
                        "email": "email@tucorreo.com",
                    }
                }
            ]",
            "language": "json",
            "name": "Respuesta exitosa"
        },
        {
            "code": "{
                "status": "error",
                "message": "La cuenta que intenta autenticarse no existe",
                "Data": "$2y$10$dnOV7qC7ZrD1CZitpUnTReLKtKPxG29XfwZylrEuiR0KVl18pOXXX",
                "Secret": "$2y$10$6ZN4aX5UExwz6HFlDSZcxOF1TGjHx8f40neE.CrXHHahyAfi8XXX."
            }",
            "language": "json",
            "name": "Respuesta error"
        }
    ]
}


```


#### Sobre errores

El mensaje de error puede variar dependiendo el nodo en el que haya información incorrecta.  
Te sugerimos leer cuidadosamente el mensaje del error ya que en el mismo se indica donde es necesario corregir la información.
