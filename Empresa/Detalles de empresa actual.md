# Detalles de empresa actual

A continuación se explica como obtener los detalles de la empresa actual con la que se está trabajando.

#### Construcción de la URL

**Host**: https://facturaonline.com.mx  
**Endpoint**:  /api/v1/current/account  
**Ejemplo**:  https://facturaonline.com.mx/api/v1/current/account  


#### Ejemplo

```

<?php
$ch = curl_init();

curl_setopt($ch, CURLOPT_URL, "http://devfactura.in/api/v1/current/account");
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

{
    "status": "success",
    "data": {
        "uid": "55c0fdc651XXX",
        "razon_social": "EMPRESA DEMO",
        "rfc": "LAN7008XXXX",
        "regimen_fiscal": "GeneraldeLeyPersonasMorales",
        "calle": "Lopez Mateos",
        "exterior": "400",
        "interior": "",
        "colonia": "LadróndeGuevara",
        "codpos": "44650",
        "ciudad": "Guadalajara",
        "estado": "Jalisco",
        "email": "correo@correo.com"
    }
}

```


#### Respuesta error

```

{
    "status": "error",
    "message": "La cuenta que intenta autenticarse no existe",
    "Data": "$2y$10$dnOV7qC7ZrD1CZitpUnTReLKtKPxG29XfwZylrEuiR0KVl18pOXXX",
    "Secret": "$2y$10$6ZN4aX5UExwz6HFlDSZcxOF1TGjHx8f40neE.CrXHHahyAfi8XXX."
}

```


#### Sobre errores

El mensaje de error puede variar dependiendo el nodo en el que haya información incorrecta.  
Te sugerimos leer cuidadosamente el mensaje del error ya que en el mismo se indica donde es necesario corregir la información.
