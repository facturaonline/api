# Descargar CFDI

A continuación se explica como descargar un CFDI.
Cada CFDI puede ser descargado a través de nuestra API en dos tipos de archivo distintos:
* PDF.
* XML.

Para obtener uno u otro solo es necesario cambiar el endpoint al que estamos apuntando:
* /pdf
* /xml

Podemos descargar un CFDI haciendo uso del siguiente parámetro:

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
            <td>Indica el UID o UUID del CFDI que deseas descargar.
            Ejemplo: "n55c0fdc67593d</td>
        </tr>
        <tr>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
    </tbody>
</table>


#### Construcción de la URL

**Host**: https://facturaonline.com.mx  
**Endpoint PDF**:  /api/v3/cfdi33/cfdi_uid/pdf  
**Endpoint XML**:  /api/v3/cfdi33/cfdi_uid/xml  
**Ejemplo**:  https://facturaonline.com.mx/api/v3/cfdi33/55c0fdc67593d/pdf  


#### Ejemplo

```

<?php
$ch = curl_init();

curl_setopt($ch, CURLOPT_URL, "https://facturaonline.com.mx/api/v3/cfdi33/cfdi_uid/pdf");
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
Además de reemplazar **cfdi_uid**  por el UID del CFDI que deseas descargar.
