# Complemento de pago

A continuación se explica como crear un complemento de pago, con un ejemplo y  muestra de posibles respuestas obtenidas.  
Podemos crear un **CFDI con complemento de pago** haciendo uso de los siguientes parámetros:

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
            <td>Receptor</td>
            <td>array</td>
            <td>Requerido</td>
            <td>Indica el UID del receptor/cliente previamente creado en facturaonline.com.mx.
            Ejemplo: "Receptor": {
                "ResidenciaFiscal": "",
                "UID": "55c0fdc67593d"
            }</td>
        </tr>
        <tr>
            <td>TipoDocumento</td>
            <td>string</td>
            <td>Requerido</td>
            <td>Es necesario enviar la clave P en este campo.
            Ejemplo: "TipoCfdi": "P"</td>
        </tr>
        <tr>
            <td>Conceptos</td>
            <td>array</td>
            <td>Requerido</td>
            <td>Es un arreglo de objetos, en el que debe definirse un solo objeto con la siguiente información.
            Ejemplo: "Conceptos": [{
                "ClaveProdServ": "84111506",
                "Cantidad": "1",
                "ClaveUnidad": "ACT",
                "Descripcion": "Pago",
                "ValorUnitario": "0",
                "Importe": "0"
            }]</td>
        </tr>
        <tr>
            <td>UsoCFDI</td>
            <td>string</td>
            <td>Requerido</td>
            <td>Indica siempre la clave P01 correspondiente a Por definir.
            Ejemplo: "UsoCFDI": "P01"</td>
        </tr>
        <tr>
            <td>Serie</td>
            <td>number</td>
            <td>Requerido</td>
            <td>Indica id de la serie con la que deseas timbrar el documento.
            Ésta debe estar dada de alta en tu panel de Facturaonline.com.mx y coincidir con el tipo de CFDI que deseas timbrar.
            Para obtenerlo  Inicia sesión  y dirígete al  **Menú lateral / Configuraciones / Series y folios​**.
            Ejemplo: "Serie": 1247</td>
        </tr>
        <tr>
            <td>CfdiRelacionados</td>
            <td>array</td>
            <td>Opcional</td>
            <td>En caso que tu complemento sustituya a otro envía un arreglo con el/los UUID's con los que está relacionado.
            Ejemplo: "CfdiRelacionados": {
                "TipoRelacion": "04",
                "UUID": [
                    "29c98cb2-f72a-4cbe-a297-606da335e187",
                    "a96f6b9a-70aa-4f2d-bc5e-d54fb7371236"
                ]
            }</td>
        </tr>
        <tr>
            <td>Moneda</td>
            <td>string</td>
            <td>Requerido</td>
            <td>Se debe registrar siempre el valor "XXX".
            Ejemplo: "Moneda": "XXX"</td>
        </tr>
        <tr>
            <td>NumOrder</td>
            <td>number</td>
            <td>Opcional</td>
            <td>Indica el número de orden o pedido.
            Este dato es solo para control interno.
            Ejemplo: "NumOrder": "85abf36"</td>
        </tr>
        <tr>
            <td>Fecha</td>
            <td>string</td>
            <td>Opcional</td>
            <td>Indica una fecha con formato (Y-m-d\\TH: m :s).
            Es posible enviar hasta 72 horas de atraso a la fecha actual, sin embargo no están permitidas las fechas futuras.
            Ejemplo: "Fecha": "2018/12/04"</td>
        </tr>
        <tr>
            <td>EnviarCorreo</td>
            <td>bolean</td>
            <td>Opcional</td>
            <td>Indica si deseas que el CFDI se envíe a tu cliente por correo electrónico. Por default esta opción es true.
            Ejemplo: "EnviarCorreo": "true"</td>
        </tr>
        <tr>
            <td>Pagos</td>
            <td>Array</td>
            <td>Requerido</td>
            <td>Indica los datos del complemento de pago.</td>
        </tr>
    </tbody>
</table>


#### Importante

Es necesario que envíes los valores (precios, cálculo de impuestos, subtotales, etc) de acuerdo a tus necesidades. Esto incluye número de decimales y redondeos.


#### Nodo: Pagos

Es el nodo en el que se ingresa la información correspondiente complemento de pagos.  
A continuación se presentan los atibutos que debe incluir el nodo **Pagos**:


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
            <td>typeComplement</td>
            <td>string</td>
            <td>Requerido</td>
            <td>Indica el tipo de complemento, en este caso es pagos.
            Ejemplo: "typeComplement": "pagos"</td>
        </tr>
        <tr>
            <td>FechaPago</td>
            <td>Number</td>
            <td>Requerido</td>
            <td>Indica la fecha y hora en la que el beneficiario recibe el pago, debe estar expresada en el siguiente formato:  aaaa-mm-ddThh:mm:ss.
            Ejemplo: "FechaPago": "2018-12-01T12:00:00"</td>
        </tr>
        <tr>
            <td>FormaDePagoP</td>
            <td>array</td>
            <td>Requerido</td>
            <td>Indica la clave de la forma de pago.
            Nota: debe ser distinta a la clave 99 - Por definir.
            Ejemplo: "FormaPago": "01"</td>
        </tr>
        <tr>
            <td>MonedaP</td>
            <td>string</td>
            <td>Requerido</td>
            <td>Indica la clave de la moneda del pago.
            Ejemplo: "Moneda": "MXN"</td>
        </tr>
        <tr>
            <td>TipoCambioP</td>
            <td>string</td>
            <td>Requerido</td>
            <td>Indica el tipo de cambio vigente al momento de recibir el pago.
            Ejemplo: "TipoCambio": "19.85"</td>
        </tr>
        <tr>
            <td>Monto</td>
            <td>string</td>
            <td>Requerido</td>
            <td>Indica el importe del pago, éste debe ser mayor a 0.
            Ejemplo: "Monto": "1000.00"</td>
        </tr>
        <tr>
            <td>NumOperacion</td>
            <td>string</td>
            <td>Opcional</td>
            <td>Indica el número de orden o pedido.
            Este dato es solo para control interno.
            Ejemplo: "NumOrder": "85abf36"</td>
        </tr>
        <tr>
            <td>RfcEmisorCtaOrd</td>
            <td>string</td>
            <td>Opcional</td>
            <td>Si lo deseas, indica el RFC del banco de la cuenta de origen de la  transferencia.
            Ejemplo: "RfcEmisorCtaOrd": "BSM970519DU8"</td>
        </tr>
        <tr>
            <td>NomBancoOrdExt</td>
            <td>string</td>
            <td>Opcional</td>
            <td>Si lo deseas, indica el nombre del banco de la cuenta ordenante.
            Ejemplo: "NomBancoOrdExt": "BANCO SANTANDER (MEXICO) S.A."</td>
        </tr>
        <tr>
            <td>CtaOrdenante</td>
            <td>string</td>
            <td>Opcional</td>
            <td>Si lo deseas, indica el número de la cuenta con la que se realizó el pago, o la CLABE interbancaria de la cuenta desde donde se hizo la transferencia.
            Ejemplo: "CtaOrdenante": "15478952364"</td>
        </tr>
        <tr>
            <td>RfcEmisorCtaBen</td>
            <td>string</td>
            <td>Opcional</td>
            <td>Si lo deseas, indica el RFC del banco de la cuenta de destino de la  transferencia.
            Ejemplo: "RfcEmisorCtaOrd": "BNM840515VB1"</td>
        </tr>
        <tr>
            <td>CtaBeneficiario</td>
            <td>string</td>
            <td>Opcional</td>
            <td>Si lo deseas, indica el número de la cuenta o la CLABE interbancaria de la cuenta desde donde se recibió el pago.
            Ejemplo: "CtaOrdenante": "15478952364"</td>
        </tr>
        <tr>
            <td>TipoCadPago</td>
            <td>string</td>
            <td>Opcional</td>
            <td>Indica la clave del tipo de cadena de pago.</td>
        </tr>
        <tr>
            <td>relacionados</td>
            <td>string</td>
            <td>Opcional</td>
            <td>Indica al menos un documento relacionado para tu complemento de pago.</td>
        </tr>
    </tbody>
</table>


#### Construcción de la URL

**Host**: https://facturaonline.com.mx  
**Endpoint**:  api/v3/cfdi33/complemento/pagos/create  
**Ejemplo**:  https://facturaonline.com.mx/api/v3/cfdi33/complemento/pagos/create  


#### Ejemplo

```

<?php
$ch = curl_init();

curl_setopt($ch, CURLOPT_URL, "https://facturaonline.com.mx/api/v3/cfdi33/complemento/pagos/create");
curl_setopt($ch, CURLOPT_RETURNTRANSFER, TRUE);
curl_setopt($ch, CURLOPT_HEADER, FALSE);

curl_setopt($ch, CURLOPT_POST, TRUE);

curl_setopt($ch, CURLOPT_POSTFIELDS, "{
  \"TipoDocumento\": \"pago\",
  \"NumOrder\": \"\",
  \"EnviarCorreo\": true,
  \"Version\": \"3.3\",
  \"Serie\": 865,
  \"Fecha\": \"2018/12/12\",
  \"Subtotal\": 0,
  \"Total\": 0,
  \"Moneda\": \"XXX\",
  \"UsoCFDI\": \"P01\",
  \"Receptor\": {
    \"ResidenciaFiscal\": \"\",
    \"NumRegIdTrib\": \"\",
    \"UID\": \"55c1010a47XXX\"
  },
  \"Conceptos\": [
    {
      \"ClaveProdServ\": \"84111506\",
      \"Cantidad\": 1,
      \"ClaveUnidad\": \"ACT\",
      \"Descripcion\": \"Pago\",
      \"ValorUnitario\": 0,
      \"Importe\": 0,
      \"Complemento\": [
        {
          \"typeComplement\": \"pagos\",
          \"FechaPago\": \"2018-12-12T12:00:00\",
          \"FormaDePagoP\": \"01\",
          \"MonedaP\": \"MXN\",
          \"TipoCambioP\": 0,
          \"Monto\": \"500\",
          \"NumOperacion\": \"0987654234567\",
          \"RfcEmisorCtaOrd\": \"\",
          \"CtaOrdenante\": \"\",
          \"NomBancoOrdExt\": \"\",
          \"RfcEmisorCtaBen\": \"\",
          \"CtaBeneficiario\": \"\",
          \"relacionados\": [
            {
              \"IdDocumento\": \"042233a5-fdb1-4217-8474-1688db68fXXX\",
              \"MonedaDR\": \"MXN\",
              \"TipoCambioDR\": 0,
              \"MetodoDePagoDR\": \"PPD\",
              \"NumParcialidad\": \"1\",
              \"ImpSaldoAnt\": \"1000\",
              \"ImpPagado\": \"500\",
              \"ImpSaldoInsoluto\": \"500\"
            }
          ]
        }
      ]
    }
  ]
}");

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


#### Recuerda que

Para probar el código de ejemplo es necesario que reemplaces el texto  **Ingresa API KEY**  por el API KEY de tu cuenta, e **Ingresa SECRET KEY**  por el SECRET KEY correspondiente.  
Así como cambiar los UID de los CFDIs relacionados y de receptor.


#### Respuesta exitosa

```

{
    "response": "success",
    "message": "Facturacreadayenviadasatisfactoriamente",
    "UUID": "11299a64-db3f-4dfd-8ccb-5013ba034fXX",
    "uid": "5c11578d2f71d",
    "SAT": {
        "UUID": "11299a64-db3f-4dfd-8ccb-5013ba034fXXX",
        "FechaTimbrado": "2018-12-12T12: 46: 40",
        "NoCertificadoSAT": "20001000000300022323",
        "Version": "1.1",
        "SelloSAT": "On\/VuLDaF13cXUnMV79lKkvaKMW4IGkTd7QvBK+G9c4hmsYGWRfAGfYfUoh2Ab2IhRhw6VSP2IJAij8Ad0oSThW5+FOWRVax6jX0SHXFUWC8IXN5xuK2t6qVqQ5iRZt8ZVjTovz6Q8nP09cGBB46ikwWb9W9LTALl+ZtF2K6fQ0NnNXJy8a+GeMTKe\/UpVnoPoLC179gkHTJZCJzYGUCcOlccSCE5Bxz6MzJQxGTGqmJi9vNuEpcH2tYwO9VzSOXL4foPt+oa5Jqc5r4c++gah97+1+NGuMUvaQX6kMq8PFUq5YXKo83sO2Flj54Ux68XsCLDv3Twc1h1FI4yCVXXXX==",
        "SelloCFD": "X5rm9\/shEu3u6oNT0TOdjOMfKD3kob9RBoB+FdHcD3wQhCp4ksA\/YtgwW+dTF10ezyxsEQnc6V9XteNRe4sHyzUcedERUh1XWp+JTM247Rg2NHrGBecAYHPOFgB218ERSrCavaD949uPBR1GamXnNAdkL5YLxgbfjPLfMzE6sli0NdgsBuCES2hrvsU9FA0wLTenTP6c6B7kZd7kGVbKBRFixkB+MYvWtML1D2WK+XXXXX+IviFoJtSTd3OAFEBspy90t779l8Tgk4J+zs2Ug=="
    },
    "INV": {
        "Serie": "PA",
        "Folio": 71
    },
    "invoice_uid": "5c11578d2f7XX"
}

```

#### Respuesta error

```

{
    "response": "error",
    "message": {
        "message": "401 - El rango de la fecha de generaci\u00f3n no debe de ser mayor a 72 horas para la emisi\u00f3n del timbre.",
        "messageDetail": "Comprobante.Fecha: Fecha de emisi\u00f3n: 2018-05-16T13:04:20 Fecha del Servidor: 2018-12-12T13:02:24 La fecha de emision no se encuentra en el rango permitido: 2018-12-09T13:02:24 - 2018-12-12T14:07:24",
        "data": null,
        "status": "error"
    },
    "xmlerror": "\n<\/cfdi:Conceptos><\/pago10:Pago><\/pago10:Pagos><\/cfdi:Complemento><\/cfdi:Comprobante>\n"
}

```

#### Sobre errores

El mensaje de error puede variar dependiendo el nodo en el que haya información incorrecta.  
Te sugerimos leer cuidadosamente el mensaje del error ya que en el mismo se indica donde es necesario corregir la información.
