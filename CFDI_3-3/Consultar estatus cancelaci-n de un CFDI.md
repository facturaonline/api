# Consultar estatus cancelación de un CFDI

A continuación se explica como consultar el estatus de la cancelación de un CFDI con un ejemplo de como hacerlo.  
Podemos consultar el estatus CFDI haciendo uso del siguiente parámetro:

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
            <td>uid</td>
            <td>string</td>
            <td>Requerido</td>
            <td>Indica el UID o UUID del CFDI que deseas consultar.
            Ejemplo: "55c0fdc67593d"</td>
        </tr>
    </tbody>
</table>


#### Construcción de la URL

**Host**: https://facturaonline.com.mx  
**Endpoint**:  /api/v3/cfdi33/uid/cancel_status  
**Ejemplo**:  https://facturaonline.com.mx/api/v3/cfdi33/c55df8b4-37b3-47cf-9e35-efdb4c3261b4/cancel_status  
**Ejemplo**:  https://facturaonline.com.mx/api/v3/cfdi33/c55df8b4/cancel_status  


#### Ejemplo

```

<?php
$ch = curl_init();

curl_setopt($ch, CURLOPT_URL, "https://factura.com/api/v3/cfdi33/uid/cancel");
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
Además de reemplazar **uid**  por el UID o UUID del CFDI que deseas consultar.


#### Estatus vigente cancelable

```

{
    "response": "success",
    "data": {
        "CodigoEstatus": "S - Comprobante obtenido satisfactoriamente.",
        "Estado": "Vigente",
        "EsCancelable": "Cancelable sin aceptación",
        "EstatusCancelacion": []
    }
}

```


#### Estatus cancelado

```

{
    "response": "success",
    "data": {
        "CodigoEstatus": "S - Comprobante obtenido satisfactoriamente.",
        "Estado": "Cancelado",
        "EsCancelable": "Cancelable sin aceptación",
        "EstatusCancelacion": "Cancelado sin aceptación"
    }
}

```


#### Estatus vigente no cancelable

```

{
    "response": "success",
    "data": {
        "CodigoEstatus": "S - Comprobante obtenido satisfactoriamente.",
        "Estado": "Vigente",
        "EsCancelable": "No Cancelable",
        "EstatusCancelacion": []
    }
}

```


#### Sobre los mensajes

El mensaje de respuesta puede variar dependiendo de el estatus en el que se encuentre el CFDI.  
Es importante mencionar que, a pesar de que el nuevo método de cancelación entró en vigor el día 1 de noviembre de 2018, el SAT continúa presentando problemas con el servicio de consulta. Debido a esto, es posible que al consultar un CFDI cancelado, su estatus aparezca como vigente por un tiempo.
