# Consultar RFC repetido con diferente información

A continuación se explica como consultar un RFC dado de alta más de una vez pero con distintas razones sociales o distintos datos.  
Para consultar un RFC en específico es necesario enviarlo en la petición.

```

{
    "data": {
        "h-0": "Parámetro",
        "h-1": "Tipo",
        "h-2": "Requerido",
        "h-3": "Detalles",
        "0-0": "rfc",
        "0-1": "string",
        "0-2": "Opcional
        Requerido en el caso de querer consultar solo a un cliente.",
        "0-3": "Indica el RFC a buscar, para traer toda la información de los clientes registrados con el mismo."
    },
    "cols": 4,
    "rows": 1
}

```


#### Construcción de la URL

**Host**: https://facturaonline.com.mx
**Endpoint**:  /api/v1/clients/rfc/el_rfc
**Ejemplo**:  https://facturaonline.com.mx/api/v1/clients/rfc/el_rfc


#### Ejemplo

```

{
    "codes": [
        {
            "code": "<?php
            $ch = curl_init();
            curl_setopt($ch, CURLOPT_URL, "https://facturaonline.com.mx/api/v1/clients/rfc/el_rfc");
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
            var_dump($response);",
            "language": "php",
            "name": "listar_clientes.php"
        }
    ]
}

```


#### Recuerda

Para probar el código de ejemplo es necesario que reemplaces el texto  **Ingresa API KEY**  por el API KEY de tu cuenta, e **Ingresa SECRET KEY**  por el SECRET KEY correspondiente.  
Además de reemplazar **el_rfc** por el RFC  que deseas consultar.


#### Importante

En caso de tener más de un cliente registrado con el mismo RFC, la respuesta a esta petición incluirá a todos los clientes dados de alta cuyo RFC coincida con el solicitado, de este modo podrás elegir de entre los resultados el cliente que requieres.


#### Respuesta

```

{
    "codes": [
        {
            "code": "[
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
                    "UID": "Id único e irrepetible asignado por Factura.com y que servirá para la gestión interna del docmento."
                },
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
            "UID": "Id único e irrepetible asignado por Factura.com y que servirá para la gestión interna del docmento."
        },
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
    "UID": "Id único e irrepetible asignado por Factura.com y que servirá para la gestión interna del docmento."
}

]",
"language": "json",
"name": "Respuesta exitosa mismo RFC distintas razones sociales."
}
]
}
```

#### Sobre errores

El mensaje de error puede variar dependiendo el nodo en el que haya información incorrecta.  
Te sugerimos leer cuidadosamente el mensaje del error ya que en el mismo se indica donde es necesario corregir la información.
