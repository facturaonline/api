# Actualizar empresa

A continuación se explica como actualizar los datos de una empresa dada de alta en Facturaonline.com.mx.  
Para actualizar la información de una empresa es necesario enviar los siguientes parámetros:

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
            <td>razons</td>
            <td>string</td>
            <td>Requerido</td>
            <td>Indica la Razón social de la empresa.</td>
        </tr>
        <tr>
            <td>rfc</td>
            <td>string</td>
            <td>Requerido</td>
            <td>Indica el RFC de la empresa con min:12 y max:13  caracteres.</td>
        </tr>
        <tr>
            <td>regimen</td>
            <td>string</td>
            <td>Opcional</td>
            <td>Indica el código del régimen fiscal al que pertenece tu empresa.
            [Consulta las claves de Régimen fiscal válidas](https://facturaonline.com.mx/docs/r%C3%A9gimen-fiscal).</td>
        </tr>
        <tr>
            <td>calle</td>
            <td>string</td>
            <td>Requerido</td>
            <td>Indica el domicilio fiscal.</td>
        </tr>
        <tr>
            <td>numero_exterior</td>
            <td>int</td>
            <td>Requerido</td>
            <td>Indica el número exterior.</td>
        </tr>
        <tr>
            <td>numero_interior</td>
            <td>int</td>
            <td>Opcional</td>
            <td>Indica el número interior.</td>
        </tr>
        <tr>
            <td>codpos</td>
            <td>numeric</td>
            <td>Requerido</td>
            <td>Indica el código postal. Éste debe ser de 5 caracteres.</td>
        </tr>
        <tr>
            <td>colonia</td>
            <td>string</td>
            <td>Requerido</td>
            <td>Indica la colonia.</td>
        </tr>
        <tr>
            <td>estado</td>
            <td>string</td>
            <td>Requerido</td>
            <td>Indica el estado.</td>
        </tr>
        <tr>
            <td>ciudad</td>
            <td>string</td>
            <td>Requerido</td>
            <td>Indica la ciudad.</td>
        </tr>
        <tr>
            <td>delegacion</td>
            <td>string</td>
            <td>Opcional</td>
            <td>Indica la delegación en caso de contar con ella.</td>
        </tr>
        <tr>
            <td>email</td>
            <td>string</td>
            <td>Requerido</td>
            <td>Indica el Email.</td>
        </tr>
    </tbody>
</table>


#### Construcción de la URL

**Host**: https://facturaonline.com.mx  
**Endpoint**:  /api/v1/account/client_uid/update  
**Ejemplo**:  https://facturaonline.com.mx/api/v1/account/client_uid/update  


#### Ejemplo

```

<?php
$ch = curl_init();

curl_setopt($ch, CURLOPT_URL, "https://factura.com/api/v1/account/client_uid/update");
curl_setopt($ch, CURLOPT_RETURNTRANSFER, TRUE);
curl_setopt($ch, CURLOPT_HEADER, FALSE);

curl_setopt($ch, CURLOPT_POST, TRUE);

curl_setopt($ch, CURLOPT_POSTFIELDS, "{
    \"razons\": \"Ferreteria Perez\",
    \"rfc\": \"XAXX010101000\",
    \"regimen\": \"611\",
    \"calle\": \"Av. Juarez\",
    \"numero_exterior\": 1234,
    \"numero_interior\": \"4\",
    \"codpos\": 44640,
    \"colonia\": \"Centro\",
    \"estado\": \"Jalisco\",
    \"ciudad\": \"Guadalajara\",
    \"delegaion\": \"\",
    \"email\": \"josepe@email.com\"
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


#### Recuerda

Para probar el código de ejemplo es necesario que reemplaces el texto  **Ingresa API KEY**  por el API KEY de tu cuenta, e **Ingresa SECRET KEY**  por el SECRET KEY correspondiente.  
Además reemplazar el **client_uid**  en la URL.


#### Respuesta exitosa

```

[
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
