# Actualizar cliente

A continuación se explica como editar un cliente existente.  
Podemos actualizar los datos de un cliente haciendo uso de los siguientes parámetros:

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
            <td>nombre</td>
            <td>string</td>
            <td>Opcional</td>
            <td>Indica el nombre del cliente.</td>
        </tr>
        <tr>
            <td>apellidos</td>
            <td>string</td>
            <td>Opcional</td>
            <td>Indica los apellidos del cliente.</td>
        </tr>
        <tr>
            <td>email</td>
            <td>string</td>
            <td>Opcional</td>
            <td>Indica el email del cliente.</td>
        </tr>
        <tr>
            <td>email2</td>
            <td>string</td>
            <td>Opcional</td>
            <td>Indica otro email del cliente.</td>
        </tr>
        <tr>
            <td>email3</td>
            <td>string</td>
            <td>Opcional</td>
            <td>Indica otro email del cliente.</td>
        </tr>
        <tr>
            <td>telefono</td>
            <td>string</td>
            <td>Opcional</td>
            <td>Indica el numero de teléfono</td>
        </tr>
        <tr>
            <td>razons</td>
            <td>string</td>
            <td>Opcional</td>
            <td>Indica la razón social del cliente.</td>
        </tr>
        <tr>
            <td>rfc</td>
            <td>string</td>
            <td>Opcional</td>
            <td>Indica el RFC del cliente, éste debe tener min:12 y max:13 caracteres.</td>
        </tr>
        <tr>
            <td>calle</td>
            <td>string</td>
            <td>Opcional</td>
            <td>Indica la calle del domicilio fiscal.</td>
        </tr>
        <tr>
            <td>numero_exterior</td>
            <td>string</td>
            <td>Opcional</td>
            <td>Indica el número del domicilio fiscal.</td>
        </tr>
        <tr>
            <td>numero_interior</td>
            <td>string</td>
            <td>Opcional</td>
            <td>Indica el número interior del domicilio fiscal, en caso de contar con él.</td>
        </tr>
        <tr>
            <td>codpos</td>
            <td>string</td>
            <td>Opcional</td>
            <td>Indica el código postal, éste debe tener min:5 caracteres.</td>
        </tr>
        <tr>
            <td>colonia</td>
            <td>string</td>
            <td>Opcional</td>
            <td>Indica la colonia.</td>
        </tr>
        <tr>
            <td>estado</td>
            <td>string</td>
            <td>Opcional</td>
            <td>Indica la estado.</td>
        </tr>
        <tr>
            <td>ciudad</td>
            <td>string</td>
            <td>Opcional</td>
            <td>Indica la ciudad.</td>
        </tr>
        <tr>
            <td>pais</td>
            <td>string</td>
            <td>Opcional</td>
            <td>Indica la clave del país.
            [Consulta el catálogo correspondiente a paises.](https://facturaonline.com.mx/docs/pa%C3%ADs)</td>
        </tr>
        <tr>
            <td>delegacion</td>
            <td>string</td>
            <td>Requerido</td>
            <td>Indica la delegación, en caso de contar con ella.</td>
        </tr>
        <tr>
            <td>numregidtrib</td>
            <td>string</td>
            <td>Requerido</td>
            <td>Indica el número de registro de identidad fiscal del receptor del comprobante fiscal cuando éste sea residente en el extranjero.</td>
        </tr>
        <tr>
            <td>usocfdi</td>
            <td>string</td>
            <td>Requerido</td>
            <td>Indica la clave que corresponda al uso que le dará al comprobante fiscal el receptor.
            [Consulta el catálogo de claves de Uso de CFDI.](https://facturaonline.com.mx/docs/uso-de-cfdi)</td>
        </tr>
    </tbody>
</table>


#### Construcción de la URL

**Host**: https://facturaonline.com.mx  
**Endpoint**:  /api/v1/clients/client_uid/update  
**Ejemplo**:  https://facturaonline.com.mx/api/v1/clients/client_uid/update  


#### Ejemplo

```

<?php
$ch = curl_init();
$fields = [
    "nombre" => "Cliente prueba ",
    "apellidos" => "Pérez López",
    "email" => "correo@email.com",
    "email2" => "otroemail2@email.com",
    "email3" => "otroemail3@email.com",
    "telefono" => "33 3877 7741",
    "razons" => "Cliente prueba ",
    "rfc" => "XAXX010101000",
    "calle" => "Av. Juarez",
    "numero_exterior" => 1234,
    "numero_interior" => "",
    "codpos" => 44640,
    "colonia" => "Centro",
    "estado" => "Jalisco",
    "ciudad" => "Guadalajara",
    "delegacion" => ""
];

$jsonfield = json_encode($fields);

curl_setopt($ch, CURLOPT_URL, "http://devfactura.in/api/v1/clients/client_uid/update");
curl_setopt($ch, CURLOPT_RETURNTRANSFER, TRUE);
curl_setopt($ch, CURLOPT_HEADER, FALSE);
curl_setopt($ch, CURLOPT_POST, TRUE);
curl_setopt($ch, CURLOPT_POSTFIELDS, $jsonfield);

curl_setopt($ch, CURLOPT_HTTPHEADER, array(
    "Content-Type: application/json",
    "F-PLUGIN: " . '9d4095c8f7ed5785cb14c0e3b033eeb8252416ed',
    "F-Api-Key: ". 'Ingresa API KEY',
    "F-Secret-Key: " . 'Ingresa SECRET KEY'
));

$response = curl_exec($ch);

return die($response);

curl_close($ch);

?>

```


#### Recuerda

Para probar el código de ejemplo es necesario que reemplaces el texto  **Ingresa API KEY**  por el API KEY de tu cuenta, e **Ingresa SECRET KEY**  por el SECRET KEY correspondiente.  
Además es necesario reemplazar **client_uid**  por el UID del cliente en la url.


#### Respuesta exitosa

```

{
    "status": "success",
    "Data": {
        "RazonSocial": "Venta Al P\u00fablico en General",
        "RFC": "XAXX010101000",
        "Calle": "pedro loza",
        "Numero": "12349506",
        "Interior": "No Aplica",
        "Colonia": "Centro",
        "CodigoPostal": "00000",
        "Ciudad": "Guadalajara",
        "Delegacion": "Guadalajara",
        "Estado": "Jalisco",
        "Pais": "MEX",
        "Contacto": {
            "Nombre": "Publico",
            "Apellidos": "General (M\u00e9xico)",
            "Email": "paco@lightcone.com",
            "Email2": null,
            "Email3": null,
            "Telefono": "0000000000"
        },
        "UID": "55c0fdc67593d",
        "cfdis": 477,
        "cuentas_banco": [
            {
                "banco": "AMERICAN EXPRESS",
                "cuenta": "3323"
            },
            {
                "banco": "ABC CAPITAL",
                "cuenta": "8888"
            }
        ]
    }
}

```


#### Respuesta exitosa

```

{
    "status": "error",
    "message": {
        "rfc": [
        "El campo rfc es requerido"
        ]
    }
}

```

#### Sobre errores

El mensaje de error puede variar dependiendo el nodo en el que haya información incorrecta.  
Te sugerimos leer cuidadosamente el mensaje del error ya que en el mismo se indica donde es necesario corregir la información.
