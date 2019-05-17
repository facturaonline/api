# Listar CFDI's

A continuación se explica como listar los CFDI's , con un ejemplo y  muestra de posibles respuestas obtenidas.
Podemos consultar los CFDI's filtrando por los siguientes parámetros:

<table>
    <thead>
        <tr>
            <th>Parámetro</th>
            <th>Tipo</th>
            <th>Requerido</th>
            <th>Detalles</th>
        </tr>
    </thead>
    <body>
        <tr>
            <td>month</td>
            <td>number</td>
            <td>Opcional</td>
            <td>Induca el número de mes que deseas consultar. Éste debe estar escrito en 2 dígitos.  
            Ejemplo: Enero = 01, Diciembre = 12, etc.</td>
        </tr>
    </body>
</table>


#### Construcción de la URL

**Host**: https://facturaonline.com.mx
**Endpoint**:  /api/v3/cfdi33/list
**Ejemplo**:  https://facturaonline.com.mx/api/v3/cfdi33/list


#### Ejemplo

```

<?php
$ch = curl_init();

curl_setopt($ch, CURLOPT_URL, "http://devfactura.in/api/v3/cfdi33/list");
curl_setopt($ch, CURLOPT_RETURNTRANSFER, TRUE);
curl_setopt($ch, CURLOPT_HEADER, FALSE);

curl_setopt($ch, CURLOPT_HTTPHEADER, array(
    "Content-Type: application/json",
    "F-PLUGIN: " . '9d4095c8f7ed5785cb14c0e3b033eeb8252416ed',
    "F-Api-Key: ".'Ingresa API KEY',
    "F-Secret-Key: " .'Ingresa SECRET KEY'
));

$response = curl_exec($ch);

return die($response);

curl_close($ch);

?>


```


#### Recuerda que

Para probar el código de ejemplo es necesario que reemplaces el texto  **Ingresa API KEY**  por el API KEY de tu cuenta, e **Ingresa SECRET KEY**  por el SECRET KEY correspondiente.


#### Respuesta exitosa

```

{
  "status": "success",
  "response": "success",
  "total": 2479,
  "per_page": 100,
  "current_page": 1,
  "last_page": 25,
  "from": 1,
  "to": 100,
  "data": [
    {
      "RazonSocialReceptor": "Venta Al Público en General",
      "Folio": "F 01",
      "UID": "5c04c662exxxx",
      "UUID": "1750d757-577d-xxxx-xxxx-518b87b24a87",
      "Subtotal": "5.000000",
      "Descuento": null,
      "Total": "5.800000",
      "ReferenceClient": 0,
      "NumOrder": null,
      "Receptor": "XAXX010101000",
      "FechaTimbrado": "2018-12-03",
      "Status": "enviada",
      "Version": "3.3"
    },
    {
      "RazonSocialReceptor": "Cliente ejemplo",
      "Folio": "F 160",
      "UID": "5c033ca2e4xxx",
      "UUID": "c25c6c99-xxx-xxx-810e-e5ae7e12eb15",
      "Subtotal": "10000.000000",
      "Descuento": null,
      "Total": "11600.000000",
      "ReferenceClient": 15,
      "NumOrder": null,
      "Receptor": "XAXX010101000",
      "FechaTimbrado": "2018-12-01",
      "Status": "enviada",
      "Version": "3.3"
    }
  ]
}

```


#### Respuesta error

```

{
  "status": "error",
  "message": "La cuenta que intenta autenticarse no existe",
  "Data": "$2y$10$dnOV7qC7ZrD1CZitpUnTReLKtKPxG29XfwZylrEuiR0KVl18pOXXX",
  "Secret": "$2y$10$6ZN4aX5UExwz6HFlDSZcxOF1TGjHx8f40neE.CrXHHahyAfi8qiXXX"
}

```
