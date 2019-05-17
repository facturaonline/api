# Consultar detalle empresa

A continuación se explica como obtener los detalles de cualquier empresa que tengamos registrada en Facturaonline.com.mx.  
Para consultar una empresa es necesario enviar el **UID** de la misma.

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
            <td>UID</td>
            <td>string</td>
            <td>Requerido</td>
            <td>Envía el UID de la empresa registrada en facturaonline.com.mx.
            Ejemplo: 5670a524cfc65</td>
        </tr>
    </tbody>
</table>


#### Construcción de la URL

**Host**: https://facturaonline.com.mx  
**Endpoint**:  /api/v1/account/UID  
**Ejemplo**:  https://facturaonline.com.mx/api/v1/account/UID  


#### Ejemplo

```

<?php
$ch = curl_init();

curl_setopt($ch, CURLOPT_URL, "http://devfactura.in/api/v1/account/UID");
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
Además reemplazar el **UID**  en la URL.


#### Respuesta exitosa

```

[
    {
        "status": "success o error",
        "data": {
            "uid": "5670a524cfc65",
            "razon_social": "EMPRESA DEMOSTRACION",
            "rfc": "XAXX010101000",
            "regimen_fiscal": "Persona Física con Actividad Empresarial",
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
]

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
