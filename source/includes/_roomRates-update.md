# RoomRatesUpdate

> Ejemplo RoomRatesUpdateRequest dónde únicamente se actualiza inventario
&nbsp;&nbsp;<span class="postman-button">[![Run in Postman](https://run.pstmn.io/button.svg)](https://app.getpostman.com/run-collection/495ff7995b655b745365)</span>

````xml
<?xml version="1.0" encoding="UTF-8"?>
<RoomRatesUpdateRequest>   
    <credentials>
        <vendorCode>FOO</vendorCode>
        <user>BAR</user>
        <password>FOOBAR</password>
    </credentials>   
    <hotelCode>1234</hotelCode>
    <roomRate rateCode="BASE" roomCode="SGL#STD">
        <dateFrom>01/01/2016</dateFrom>
        <dateTo>02/01/2016</dateTo>
        <availableQuota>9</availableQuota>
        <status>Open</status>
    </roomRate>
    <roomRate rateCode="BASE" roomCode="DBL#STD">
        <dateFrom>01/01/2016</dateFrom>
        <dateTo>01/01/2016</dateTo>
        <availableQuota>5</availableQuota>
        <status>Open</status>
    </roomRate>
</RoomRatesUpdateRequest>
````

````json
{
  "RoomRatesUpdateRequest": {
    "credentials": {
      "vendorCode": "FOO",
      "user": "BAR",
      "password": "FOOBAR"
    },
    "hotelCode": "1234",
    "roomRate": [
      {
        "rateCode": "BASE",
        "roomCode": "SGL#STD",
        "dateFrom": "01/01/2016",
        "dateTo": "02/01/2016",
        "availableQuota": "9",
        "status": "Open"
      },
      {
        "rateCode": "BASE",
        "roomCode": "DBL#STD",
        "dateFrom": "01/01/2016",
        "dateTo": "01/01/2016",
        "availableQuota": "5",
        "status": "Open"
      }
    ]
  }
}
````

> Ejemplo RoomRatesUpdateRequest actualizando inventario, precios y restricciones para los régimenes RO y BB de la tarifa BASE, modalidad DBL#STD
&nbsp;&nbsp;<span class="postman-button">[![Run in Postman](https://run.pstmn.io/button.svg)](https://app.getpostman.com/run-collection/495ff7995b655b745365)</span>

````xml
<?xml version="1.0" encoding="UTF-8"?>
<RoomRatesUpdateRequest>
    <credentials>
        <vendorCode>FOO</vendorCode>
        <user>BAR</user>
        <password>FOOBAR</password>
    </credentials>
    <hotelCode>1234</hotelCode>
    <roomRate rateCode="BASE" roomCode="DBL#STD">
        <dateFrom>01/01/2016</dateFrom>
        <dateTo>07/01/2016</dateTo>
        <availableQuota>10</availableQuota>
        <status>Open</status>
        <mealPlan code="RO">
            <status>Open</status>
            <minimumStay>2</minimumStay>
            <maximumStay>7</maximumStay>
            <closedOnCheckIn>false</closedOnCheckIn>
            <closedOnCheckOut>false</closedOnCheckOut>
            <release>0</release>
            <price>
                <adults>2</adults>
                <children>0</children>
                <amount>100.0</amount>
                <status>Open</status>
            </price>
            <price>
                <adults>2</adults>
                <children>1</children>
                <amount>125.0</amount>
                <status>Open</status>
            </price>
        </mealPlan>
        <mealPlan code="BB">
            <status>Open</status>
            <minimumStay>2</minimumStay>
            <maximumStay>7</maximumStay>
            <closedOnCheckIn>false</closedOnCheckIn>
            <closedOnCheckOut>false</closedOnCheckOut>
            <release>7</release>
            <price>
                <adults>2</adults>
                <children>0</children>
                <amount>130.0</amount>
                <status>Open</status>
            </price>
            <price>
                <adults>2</adults>
                <children>1</children>
                <amount>150</amount>
                <status>Open</status>
            </price>
        </mealPlan>
    </roomRate>
</RoomRatesUpdateRequest>
````

````json
{
  "RoomRatesUpdateRequest": {
    "credentials": {
      "vendorCode": "FOO",
      "user": "BAR",
      "password": "FOOBAR"
    },
    "hotelCode": "1234",
    "roomRate": {
      "rateCode": "BASE",
      "roomCode": "DBL#STD",
      "dateFrom": "01/01/2016",
      "dateTo": "07/01/2016",
      "availableQuota": "10",
      "status": "Open",
      "mealPlan": [
        {
          "code": "RO",
          "status": "Open",
          "minimumStay": "2",
          "maximumStay": "7",
          "closedOnCheckIn": "false",
          "closedOnCheckOut": "false",
          "release": "0",
          "price": [
            {
              "adults": "2",
              "children": "0",
              "amount": "100.0",
              "status": "Open"
            },
            {
              "adults": "2",
              "children": "1",
              "amount": "125.0",
              "status": "Open"
            }
          ]
        },
        {
          "code": "BB",
          "status": "Open",
          "minimumStay": "2",
          "maximumStay": "7",
          "closedOnCheckIn": "false",
          "closedOnCheckOut": "false",
          "release": "7",
          "price": [
            {
              "adults": "2",
              "children": "0",
              "amount": "130.0",
              "status": "Open"
            },
            {
              "adults": "2",
              "children": "1",
              "amount": "150",
              "status": "Open"
            }
          ]
        }
      ]
    }
  }
}
````

> Ejemplo respuesta RoomRatesUpdateResponse procesada correctamente

````xml
<?xml version="1.0" encoding="UTF-8"?>
<RoomRatesUpdateResponse>
    <sessionId>SUP#FOO#123456789</sessionId>
</RoomRatesUpdateResponse>
````

````json
{
  "RoomRatesUpdateResponse": { 
    "sessionId": "SUP#FOO#123456789" 
  }
}
````

Mensaje utilizado para la actualización de inventario y tarifas (precios, paros de venta y restricciones) de un hotel.
Si únicamente se quiere actualizar inventario, no será necesario informar mealPlan

### RoomRatesUpdateRequest

Mensaje petición de actualización de inventario y tarifas de hotel.
 
Elemento | Tipo | Obl? |  Descripción
--------- | ----------- | ----------- | -----------
credentials | **Credentials** | Sí |Credenciales de autenticación del usuario (Ver Autenticación)
hotelCode | *Integer* | Sí |Código de hotel
roomRate[] | **RoomRate** | Sí | Información asociada a una combinación de tarifa y modalidad de hotel
↳ @rateCode| *String* | Sí | Código de tarifa
↳ @roomCode| *String* | Sí | Código de modalidad
↳ dateFrom| *Date* | Sí | Fecha desde (dd/MM/yyyy, rangos cerrados)
↳ dateTo| *Date* | Sí | Fecha hasta (dd/MM/yyyy, rangos cerrados)
↳ availableQuota| *Integer* | Sí | Unidades de cupo disponible
↳ status| *Enum* | Sí | Estado del inventario <sup>1</sup> 
↳ mealPlan[]| **MealPlan** | No | Información asociada al régimen alimenticio
↳↳ @code| *String* | Sí | Código de régimen alimenticio
↳↳ status| *Enum* | Sí | Estado del régimen <sup>1</sup>
↳↳ minimumStay| *Integer* | Sí | Días de estancia mínima (0: No hay estancia mínima)
↳↳ maximumStay| *Integer* | Sí | Días de estancia máxima (0: No hay límite de estancia)
↳↳ release| *Integer* | Sí | Días de release (0: No hay release)
↳↳ closedOnCheckIn| *Boolean* | Sí | Indica si no está permitida la entrada
↳↳ closedOnCheckOut| *Boolean* | Sí | Indica si no está permitida la salida
↳↳ price[]| **Price** | Sí | Precio para una ocupación
↳↳↳ adults| *Integer* | Sí | Número de adultos
↳↳↳ children| *Integer* | Sí | Número de niños
↳↳↳ amount| *Double* | Sí | Precio para el total de la ocupación (#.##)
↳↳↳ status| *Enum* | Sí | Estado de la ocupación <sup>1</sup>

<aside class="notice">
<sup>1</sup>&nbsp;&nbsp;&nbsp; Posibles valores, <b>Open</b>: a la venta; <b>Closed</b>: Cerrado; <b>OnRequest</b>: Se permite reservar, pero bajo petición.
En caso de conflicto, siempre prevalecerá el estado más restrictivo (Closed > Request > Open). Por ejemplo, si a nivel de MealPlan el estado es Closed, 
todas las ocupaciones a nivel de price también lo estarán, independientemente de que el estado se informe a Open. <br/>
No obstante, podemos tener por ejemplo el mealPlan a la venta (Open) y cerrar (Closed) una ocupación concreta.
</aside>

### RoomRatesUpdateResponse

Mensaje respuesta que indica si la actualización se ha procesado correctamente

Elemento | Tipo | Obl? | Descripción
--------- | ----------- | ----------- | -----------
sessionId | *String* | Sí|Identificador de la sesión que ha procesado la transacción
notification | **Notification** | No |Información de notificación (Error o Warning)
↳ type | *Enum* | Sí |Tipo de notificación (E:Error, W: Warning)
↳ code | *String* | Sí | Código de la notificación
↳ text | *String* | Sí | Texto descriptivo de la notificación

