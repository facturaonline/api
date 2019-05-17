# Listar CFDI's

A continuación se explica como listar los CFDI's , con un ejemplo y  muestra de posibles respuestas obtenidas.
Podemos consultar los CFDI's filtrando por los siguientes parámetros:

<table>
  <tr>
    <td>Parámetro</td>
    <td>Tipo</td>
    <td>Requerido</td>
    <td>Detalles</td>
  </tr>
  <tr>
    <td>month</td>
    <td>number</td>
    <td>Opcional</td>
    <td>Induca el número de mes que deseas consultar. Éste debe estar escrito en 2 dígitos.  
    Ejemplo: Enero = 01, Diciembre = 12, etc.</td>
  </tr>
</table>


```

{
    "data": {
        "h-0": "Parámetro",
        "h-1": "Tipo",
        "h-2": "Requerido",
        "h-3": "Detalles",
        "0-0": "month",
        "1-0": "year",
        "2-0": "rfc",
        "3-0": "type_document",
        "4-0": "page",
        "5-0": "per_page",
        "0-1": "number",
        "1-1": "number",
        "2-1": "string",
        "3-1": "string",
        "4-1": "int",
        "5-1": "int",
        "0-2": "Opcional",
        "1-2": "Opcional",
        "2-2": "Opcional",
        "3-2": "Opcional",
        "4-2": "Opcional",
        "5-2": "Opcional",
        "0-3": "Induca el número de mes que deseas consultar. Éste debe estar escrito en 2 dígitos.
        **Ejemplo**: Enero = 01, Diciembre = 12, etc.",
        "1-3": "Indica el año que deseas consultar. Éste debe estar escrito en 4 dígitos.
        **Ejemplo**: 2017.",
        "2-3": "Indica un RFC para traer todos los CFDI's timbrados al mismo.
        **Ejemplo**: XAXX010101000.",
        "3-3": "Indica un tipo de CFDI para  listar solo los CFDI's de ese tipo. Para ello enviar la clave indicada en el catálogo de **Tipos de CFDI**.
        **Ejemplo**: factura Consulta el catálogo de tipos de CFDIs.",
        "4-3": "Indica número de página a consultar, por default posiciona en la página 1.",
        "5-3": "Indica el limite de resultados para mostrar, por default retorna 100 registros."
      },
      "cols": 4,
      "rows": 6
}

```


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
