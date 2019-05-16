# Crear cliente

A continuación se explica como dar de alta un nuevo cliente.  
Podemos crear un nuevo cliente haciendo uso de los siguientes parámetros:

```

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
        "15-3": "Indica la clave del país.
        [Consulta el catálogo correspondiente a paises.](https://developers.facturaonline.com.mx/docs/pa%C3%ADs)",
        "16-3": "Indica la delegación, en caso de contar con ella.",
        "17-3": "Indica el **número de registro de identidad fiscal del receptor** del comprobante fiscal cuando éste sea residente en el extranjero.",
        "18-3": "Indica la clave que corresponda al uso que le dará al comprobante fiscal el receptor.
        [Consulta el catálogo de claves de Uso de CFDI.](https://developers.facturaonline.com.mx/docs/uso-de-cfdi)"
    },
    "cols": 4,
    "rows": 19
}

```


#### Construcción de la URL

**Host**: https://facturaonline.com.mx  
**Endpoint**:  /api/v1/clients/create  
**Ejemplo**:  https://facturaonline.com.mx/api/v1/clients/create  


#### Ejemplo

```

{
    "codes": [
        {
            "code": "<?php
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
            curl_setopt($ch, CURLOPT_URL, "http://devfactura.in/api/v1/clients/create");
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
            ?>",
            "language": "php",
            "name": "crear_cliente.php"
        }
    ]
}

```

#### Recuerda

Para probar el código de ejemplo es necesario que reemplaces el texto  **Ingresa API KEY**  por el API KEY de tu cuenta, e **Ingresa SECRET KEY**  por el SECRET KEY correspondiente.


#### Respuesta

```

{
    "codes": [
        {
            "code": "{
                "status": "success",
                "Data": {
                    "RazonSocial": "Venta Al P\\u00fablico en General",
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
                        "Apellidos": "General (M\\u00e9xico)",
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
            }",
            "language": "json",
            "name": "Respues exitosa"
        },
        {
            "code": "{
                "status": "error",
                "message": {
                    "rfc": [
                        "El campo rfc es requerido"
                    ]
                }
            }",
            "language": "json",
            "name": "Respuesta error"
        }
    ]
}

```


#### Sobre errores

El mensaje de error puede variar dependiendo el nodo en el que haya información incorrecta.  
Te sugerimos leer cuidadosamente el mensaje del error ya que en el mismo se indica donde es necesario corregir la información.
