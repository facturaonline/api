# Cancelar CFDI

A continuación se explica como crear un CFDI con un ejemplo de com hacerlo.
Podemos cancelar un CFDI haciendo uso del siguiente parámetro:

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
            <td>cfdi_uid"</td>
            <td>string"</td>
            <td>Requerido"</td>
            <td>Indica el UID o UUID del CFDI que deseas cancelar.
            Ejemplo: "55c0fdc67593d</td>
        </tr>
    </tbody>
</table>


#### Construcción de la URL

**Host**: (https://Facturaonline.com.mx)  
**Endpoint**:  /api/v3/cfdi33/cfdi_uid/cancel  
**Ejemplo**:  (https://Facturaonline.com.mx/api/v3/cfdi33/55c0fdc67593d/cancel)  


#### Ejemplo

```

<?php
$ch = curl_init();

curl_setopt($ch, CURLOPT_URL, "https://factura.com/api/v3/cfdi33/cfdi_uid/cancel");
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

Para probar el código de ejemplo es necesario que reemplaces el texto  **Ingresa API KEY**  por el API KEY de tu cuenta, e **Ingresa SECRET KEY**  por el SECRET KEY correspondiente.
Además de reemplazar **cfdi_uid**  por el UID del CFDI que deseas cancelar.


#### Respuesta exitosa

```

{
    "response": "success",
    "message": "Estimado cliente tu CFDI CED274(10bc80fd-2881-4559-b98f-009cc6f6d28c) se canceló exitosamente",
    "respuestaapi": {
        "response": "success",
        "acuse": "10BC80FD-2881-4559-B98F-009CC6F6D28C<\/UUID>201<\/EstatusUUID><\/Folios>not(ancestor-or-self::*[local-name()='Signature'])<\/XPath><\/Transform><\/Transforms>5p+cQwZ7vlmQ17braGY0x5Fd8KZI65Iif0S8FKsjeOfgT5Jxv5MAjmJRqxTTSaiNerizKFr3WCq9MdmS9V2lgg==<\/DigestValue><\/Reference><\/SignedInfo>Mj7oysYQmbHCiZWMOd8bUMXHPBgPSCJxulvF4xHwM8CqSawNl7WP3F5/7GrDRGndR8covbSqNY+Qg8sP2kKL9w==<\/SignatureValue>00001088888800000031<\/KeyName>ujwIJaMKWWmawqDpHx/OS10pXzEh2SQhY02y64v9Q0+I+0dGlIrjFJeGrsHqAT3JoYnh38Dxwta98t/7++dh2hOgiZEwRignWRIlOgM1MefBHEyY+hi4vHpZgPKq/hJVfHf9nOvlb5UgIHMTCEwrDp3qk9O5XtTEycnWwiqleG0c1J9sfbRxC0gYBHsNTH85OEtSXYMkiWNYNnFbIc7B0sgp2y18jUxUCNFBMMTV0tz2sxRF+V4hblaPjI75RWmvs9E4lD7MVmW3z7LIlSajuSL8eOqoerSkQhPBABIeQenEPQwRTt3ej3XpVaBsOmagIPZZI3RvOVh+5mcXDE5txQ==<\/Modulus>AQAB<\/Exponent><\/RSAKeyValue><\/KeyValue><\/KeyInfo><\/Signature><\/Acuse>"
    }
}

```


#### Sobre errores

El mensaje de error puede variar dependiendo el nodo en el que haya información incorrecta.
Te sugerimos leer cuidadosamente el mensaje del error ya que en el mismo se indica donde es necesario corregir la información.
