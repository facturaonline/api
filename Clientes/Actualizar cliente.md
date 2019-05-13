---
title: "Actualizar cliente"
excerpt: "A continuación se explica como editar un cliente existente"
---
Podemos actualizar los datos de un cliente haciendo uso de los siguientes parámetros:
[block:parameters]
{
  "data": {
    "h-0": "Parámetro",
    "h-1": "Tipo",
    "h-2": "Requerido",
    "h-3": "Detalles",
    "0-0": "nombre",
    "0-1": "string",
    "0-2": "Opcional",
    "0-3": "Indica el nombre del cliente.",
    "1-0": "apellidos",
    "2-0": "email",
    "3-0": "email2",
    "4-0": "email3",
    "5-0": "telefono",
    "6-0": "razons",
    "7-0": "rfc",
    "8-0": "calle",
    "9-0": "numero_exterior",
    "10-0": "numero_interior",
    "11-0": "codpos",
    "12-0": "colonia",
    "13-0": "estado",
    "14-0": "ciudad",
    "15-0": "pais",
    "16-0": "delegacion",
    "17-0": "numregidtrib",
    "18-0": "usocfdi",
    "1-1": "string",
    "2-1": "string",
    "3-1": "string",
    "4-1": "string",
    "5-1": "string",
    "6-1": "string",
    "7-1": "string",
    "8-1": "string",
    "9-1": "string",
    "10-1": "string",
    "11-1": "string",
    "12-1": "string",
    "13-1": "string",
    "14-1": "string",
    "15-1": "string",
    "16-1": "string",
    "17-1": "string",
    "18-1": "string",
    "1-2": "Opcional",
    "3-2": "Opcional",
    "4-2": "Opcional",
    "5-2": "Opcional",
    "6-2": "Opcional",
    "8-2": "Opcional",
    "9-2": "Opcional",
    "10-2": "Opcional",
    "12-2": "Opcional",
    "13-2": "Opcional",
    "14-2": "Opcional",
    "15-2": "Opcional",
    "16-2": "Opcional",
    "17-2": "Opcional",
    "18-2": "Opcional",
    "1-3": "Indica los apellidos del cliente.",
    "2-2": "Requerido",
    "7-2": "Requerido",
    "11-2": "Requerido",
    "2-3": "Indica el email del cliente.",
    "3-3": "Indica otro email del cliente.",
    "4-3": "Indica otro email del cliente.",
    "5-3": "Indica el numero de teléfono",
    "6-3": "Indica la razón social del cliente.",
    "7-3": "Indica el RFC del cliente, éste debe tener **min:12** y **max:13** caracteres.",
    "8-3": "Indica la calle del domicilio fiscal.",
    "9-3": "Indica el número del domicilio fiscal.",
    "10-3": "Indica el número interior del domicilio fiscal, en caso de contar con él.",
    "11-3": "Indica el código postal, éste debe tener **min:5 **caracteres.",
    "12-3": "Indica la colonia.",
    "13-3": "Indica la estado.",
    "14-3": "Indica la ciudad.",
    "15-3": "Indica la clave del país.\n\n[Consulta el catálogo correspondiente a paises.](https://developers.factura.com/docs/pa%C3%ADs)",
    "16-3": "Indica la delegación, en caso de contar con ella.",
    "17-3": "Indica el **número de registro de identidad fiscal del receptor** del comprobante fiscal cuando éste sea residente en el extranjero.",
    "18-3": "Indica la clave que corresponda al uso que le dará al comprobante fiscal el receptor. \n\n[Consulta el catálogo de claves de Uso de CFDI.](https://developers.factura.com/docs/uso-de-cfdi)"
  },
  "cols": 4,
  "rows": 19
}
[/block]

[block:html]
{
  "html": "<div>\n  <h1>Construcción de la URL</h1>\n</div>\n<style>\n  h1{\n  \tcolor:#173457;\n    font-size: 18px;\n    font-weight:500;\n  }\n</style>"
}
[/block]
**Host**: ** https://factura.com** (producción)     /    **http://devfactura.in** (sandbox)
**Endpoint**:  /api/v1/clients/client_uid/update

**Ejemplo**:  https://factura.com/api/v1/clients/client_uid/update
[block:html]
{
  "html": "<div>\n  \n  <h1>Ejemplo:</h1>\n</div>\n<style>\n  h1{\n  \tcolor:#173457;\n    font-size: 18px;\n    font-weight:500;\n  }\n</style>"
}
[/block]

[block:code]
{
  "codes": [
    {
      "code": "<?php\n$ch = curl_init();\n$fields = [\n \"nombre\" => \"Cliente prueba \",\n \"apellidos\" => \"Pérez López\",\n \"email\" => \"correo@email.com\",\n \"email2\" => \"otroemail2@email.com\",\n \"email3\" => \"otroemail3@email.com\",\n \"telefono\" => \"33 3877 7741\",\n \"razons\" => \"Cliente prueba \",\n \"rfc\" => \"XAXX010101000\",\n \"calle\" => \"Av. Juarez\",\n \"numero_exterior\" => 1234,\n \"numero_interior\" => \"\",\n \"codpos\" => 44640,\n \"colonia\" => \"Centro\",\n \"estado\" => \"Jalisco\",\n \"ciudad\" => \"Guadalajara\",\n \"delegacion\" => \"\"\n];\n\n$jsonfield = json_encode($fields);\n\ncurl_setopt($ch, CURLOPT_URL, \"http://devfactura.in/api/v1/clients/client_uid/update\");\ncurl_setopt($ch, CURLOPT_RETURNTRANSFER, TRUE);\ncurl_setopt($ch, CURLOPT_HEADER, FALSE);\ncurl_setopt($ch, CURLOPT_POST, TRUE);\ncurl_setopt($ch, CURLOPT_POSTFIELDS, $jsonfield);\n\ncurl_setopt($ch, CURLOPT_HTTPHEADER, array(\n    \"Content-Type: application/json\",\n    \"F-PLUGIN: \" . '9d4095c8f7ed5785cb14c0e3b033eeb8252416ed',\n    \"F-Api-Key: \". 'Ingresa API KEY',\n    \"F-Secret-Key: \" . 'Ingresa SECRET KEY'\n));\n\n$response = curl_exec($ch);\n\nreturn die($response);\n\ncurl_close($ch);\n\n?>",
      "language": "php",
      "name": "crear_cliente.php"
    }
  ]
}
[/block]

[block:callout]
{
  "type": "info",
  "title": "Recuerda",
  "body": "Para probar el código de ejemplo es necesario que reemplaces el texto  **Ingresa API KEY**  por el API KEY de tu cuenta, e **Ingresa SECRET KEY**  por el SECRET KEY correspondiente.\nAdemás es necesario reemplazar **client_uid**  por el UID del cliente en la url."
}
[/block]

[block:html]
{
  "html": "<div>\n  \n  <h1>Respuesta:</h1>\n</div>\n<style>\n  h1{\n  \tcolor:#173457;\n    font-size: 18px;\n    font-weight:500;\n  }\n</style>"
}
[/block]

[block:code]
{
  "codes": [
    {
      "code": "{\n  \"status\": \"success\",\n  \"Data\": {\n    \"RazonSocial\": \"Venta Al P\\u00fablico en General\",\n    \"RFC\": \"XAXX010101000\",\n    \"Calle\": \"pedro loza\",\n    \"Numero\": \"12349506\",\n    \"Interior\": \"No Aplica\",\n    \"Colonia\": \"Centro\",\n    \"CodigoPostal\": \"00000\",\n    \"Ciudad\": \"Guadalajara\",\n    \"Delegacion\": \"Guadalajara\",\n    \"Estado\": \"Jalisco\",\n    \"Pais\": \"MEX\",\n    \"Contacto\": {\n      \"Nombre\": \"Publico\",\n      \"Apellidos\": \"General (M\\u00e9xico)\",\n      \"Email\": \"paco@lightcone.com\",\n      \"Email2\": null,\n      \"Email3\": null,\n      \"Telefono\": \"0000000000\"\n    },\n    \"UID\": \"55c0fdc67593d\",\n    \"cfdis\": 477,\n    \"cuentas_banco\": [\n      {\n        \"banco\": \"AMERICAN EXPRESS\",\n        \"cuenta\": \"3323\"\n      },\n      {\n        \"banco\": \"ABC CAPITAL\",\n        \"cuenta\": \"8888\"\n      }\n    ]\n  }\n}",
      "language": "json",
      "name": "Respues exitosa"
    },
    {
      "code": "{\n  \"status\": \"error\",\n  \"message\": {\n    \"rfc\": [\n      \"El campo rfc es requerido\"\n    ]\n  }\n}",
      "language": "json",
      "name": "Respuesta error"
    }
  ]
}
[/block]

[block:callout]
{
  "type": "danger",
  "title": "Sobre errores",
  "body": "El mensaje de error puede variar dependiendo el nodo en el que haya información incorrecta.\n\nTe sugerimos leer cuidadosamente el mensaje del error ya que en el mismo se indica donde es necesario corregir la información."
}
[/block]