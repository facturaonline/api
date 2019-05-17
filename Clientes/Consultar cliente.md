# Consultar cliente

A continuación se explica como consultar un cliente en específico.  
Para consultar un cliente en específico es necesario agregar el RFC.

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
            <td>rfc</td>
            <td>string</td>
            <td>Opcional Requerido en el caso de querer consultar solo a un cliente.</td>
            <td>Indica el RFC del cliente, para traer todas las invoices del mismo.</td>
        </tr>
    </tbody>
</table>


#### Construcción de la URL

**Host**: https://facturaonline.com.mx  
**Endpoint**:  /api/v1/clients/rfc  
**Ejemplo**:  https://facturaonline.com.mx/api/v1/clients/rfc  


#### Ejemplo

```

<?php
$ch = curl_init();

curl_setopt($ch, CURLOPT_URL, "https://facturaonline.com.mx/api/v1/clients/rfc");
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
Además de reemplazar **rfc** por el RFC del cliente que deseas consultar.


#### Respuesta

```

[
    {
        "status": "success o error",
        "data": [
            {
                "RazonSocial" : "Razón Social del cliente",
                "RFC" : "Registro Federal de Contribuyentes del cliente",
                "Calle" : "Calle del domicilio del cliente",
                "Numero" : "Número exterior del domicilio del cliente",
                "Interior" : "Número interior del domicilio del cliente",
                "Colonia" : "Colonia de domicilio del cliente",
                "CodigoPosal" : "Código Postal del domicilio del cliente",
                "Ciudad" : "Ciudad del domicilio del cliente",
                "Delegacion" : "Delegación del domicilio del cliente",
                "Estado" : "Estado del domicilio del cliente",
                "NumRegIdTrib" : "",
                "UsoCFDI" : "",
                "Contacto"[{
                    "Nombre":"Nombre(s) del cliente",
                    "Apellidos":"Apellidos del cliente",
                    "Email":"Correo electrónico del cliente",
                    "Email2":"Correo electrónico 2 del cliente",
                    "Email3":"Correo electrónico 3 del cliente",
                    "Telefono":"Número de teléfono del cliente"
                }]
            }
        ],
        "UID": "Id único e irrepetible asignado por facturaonline.com.mx y que servirá para la gestión interna del docmento."
    }
]

```


#### Sobre errores

El mensaje de error puede variar dependiendo el nodo en el que haya información incorrecta.  
Te sugerimos leer cuidadosamente el mensaje del error ya que en el mismo se indica donde es necesario corregir la información.
