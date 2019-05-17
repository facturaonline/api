Para hacer uso del API de Facturaonline.com.mx es necesario hacer uso del formato **JSON** .
Todas las respuestas, exitosas o de error, están en formato **JSON**.
Es necesario incluir en las cabeceras el token de acceso llamado **API KEY** y **SECRET KEY**

<h1>Obtener API KEY y SECRET KEY</h1>
Para obtener tus llaves de acceso deber seguir los siguientes pasos:
  * Iniciar sesión en https://Facturaonline.com.mx.
  * En el menú lateral dirígete a **Configuraciones** - **API** - **Datos de acceso **.
  * Haz clic en el botón que se encuentra junto a cada token de acceso para copiarlo.

<h1>Agregar a la cabecera</h1>
Dentro de las cabeceras de la petición es necesario agregar las llaves para poder acceder al API.

Es necesario incluir una cabecera  **F-PLUGIN** cuyo valor siempre será: **9d4095c8f7ed5785cb14c0e3b033eeb8252416ed**.

A continuación se muestra un ejemplo:

```

"Content-Type: application/json",
"F-PLUGIN: " . '9d4095c8f7ed5785cb14c0e3b033eeb8252416ed',
"F-Api-Key: ". JDJ5JDEwJGRuT1Y3cUM3WnJEMUNaaXRwVW5UUmVMS3RLUHhHMjlYZndaeWxyRXVpUjBLVmwxOHBPWFXX,
"F-Secret-Key: " . JDJ5JDEwJDZaTjRhWDVVRXh3ejZIRmxEU1pjeE9GMVRHakh4OGY0MG5lRS5DclhISGFoeUFmaThxaUXX

```
