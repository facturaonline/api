# Enviroment

El API de Facturaonline.com.mx cuenta con un entorno disponible:


#### Producción

Host:  **https://facturaonline.com.mx**

Es el host para realizar el timbrado real, te recomendamos hacer pruebas en la versión **sandbox** primero, ya que los CFDIs generados en este entorno si tienen validez fiscal.


#### Composición de la URL

Independientemente del entorno en el que estés trabajando, la estructura de la url se compone de la siguiente forma:

* **Host** = producción (https://facturaonline.com.mx)
* **Version** = Versión de la API = api/v1 ó api/v3
* **End_point** = Describe el método al que se está haciendo la petición.

Por ejemplo, para traer listado de facturas en el entorno de producción la url es: (https://facturaonline.com.mx/api/v1/invoices)


#### Actualizaciones

Las **versiones 1 (v1) y 2 (v2)** de CFDI ya no se encuentran disponibles, actualmente la versión para timbrar es la **versión 3"**.
