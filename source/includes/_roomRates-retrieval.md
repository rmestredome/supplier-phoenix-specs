# RoomRatesRetrieval

> Ejemplo RoomRatesRetrievalRequest para recuperar la información publicada (inventario, precios y restricciones) de la tarifa  BASE
&nbsp;&nbsp;<span class="postman-button">[![Run in Postman](https://run.pstmn.io/button.svg)](https://app.getpostman.com/run-collection/495ff7995b655b745365)</span>

````xml
<?xml version="1.0" encoding="UTF-8"?>
<RoomRatesRetrievalRequest>   
    <credentials>
        <systemCode>SFO</systemCode>
        <vendorCode>FOO</vendorCode>
        <user>BAR</user>
        <password>FOOBAR</password>
    </credentials>   
    <hotelCode>1234</hotelCode>
    <rateCode>BASE</rateCode>    
</RoomRatesRetrievalRequest>
````

````json
{
  "RoomRatesRetrievalRequest": {
    "credentials": {
      "systemCode": "SFO",
      "vendorCode": "FOO",
      "user": "BAR",
      "password": "FOOBAR"
    },
    "hotelCode": "1234",
    "rateCode": "BASE"
  }
}
````

> Ejemplo respuesta RoomRatesRetrievalResponse procesada correctamente

````xml
<?xml version="1.0" encoding="UTF-8"?>
<RoomRatesRetrievalResponse>
    <sessionId>SUP#FOO#123456789</sessionId>
    <rate rateCode="BASE" >
        <room roomCode="DBL#STD">
            <roomRateDate dateFrom="01/01/2017" dateTo="31/01/2017">
                <availableQuota>10</availableQuota>
                <status>Open</status>
                <mealPlan code="RO">
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
            </roomRateDate>
            <roomRateDate dateFrom="01/02/2017" dateTo="28/02/2017">
                <availableQuota>8</availableQuota>
                <status>Open</status>
                <mealPlan code="RO">
                    <minimumStay>2</minimumStay>                    
                    <maximumStay>0</maximumStay>
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
                    <minimumStay>2</minimumStay>
                    <maximumStay>0</maximumStay>
                    <closedOnCheckIn>false</closedOnCheckIn>
                    <closedOnCheckOut>false</closedOnCheckOut>
                    <release>0</release>
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
            </roomRateDate>
        </room>
        <room roomCode="SGL#STD">
            <roomRateDate dateFrom="01/01/2017" dateTo="31/01/2017">
                <availableQuota>1</availableQuota>
                <status>Open</status>
                <mealPlan code="RO">
                    <minimumStay>2</minimumStay>
                    <maximumStay>7</maximumStay>
                    <closedOnCheckIn>false</closedOnCheckIn>
                    <closedOnCheckOut>false</closedOnCheckOut>
                    <release>0</release>
                    <price>
                        <adults>1</adults>
                        <children>0</children>
                        <amount>80.0</amount>
                        <status>Open</status>
                    </price>
                </mealPlan>
            </roomRateDate>
        </room>
    </rate>
</RoomRatesRetrievalResponse>

````

````json
{
  "RoomRatesRetrievalResponse": {
    "sessionId": "SUP#FOO#123456789",
    "rate": {
      "rateCode": "BASE",
      "room": [
        {
          "roomCode": "DBL#STD",
          "roomRateDate": [
            {
              "dateFrom": "01/01/2017",
              "dateTo": "31/01/2017",
              "availableQuota": "10",
              "status": "Open",
              "mealPlan": [
                {
                  "code": "RO",
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
            },
            {
              "dateFrom": "01/02/2017",
              "dateTo": "28/02/2017",
              "availableQuota": "8",
              "status": "Open",
              "mealPlan": [
                {
                  "code": "RO",
                  "minimumStay": "2",
                  "maximumStay": "0",
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
                  "minimumStay": "2",
                  "maximumStay": "0",
                  "closedOnCheckIn": "false",
                  "closedOnCheckOut": "false",
                  "release": "0",
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
          ]
        },
        {
          "roomCode": "SGL#STD",
          "roomRateDate": {
            "dateFrom": "01/01/2017",
            "dateTo": "31/01/2017",
            "availableQuota": "1",
            "status": "Open",
            "mealPlan": {
              "code": "RO",
              "minimumStay": "2",
              "maximumStay": "7",
              "closedOnCheckIn": "false",
              "closedOnCheckOut": "false",
              "release": "0",
              "price": {
                "adults": "1",
                "children": "0",
                "amount": "80.0",
                "status": "Open"
              }
            }
          }
        }
      ]
    }
  }
}
````

Mensaje utilizado para consultar la información publicada de un hotel (inventario, tarifas, precios y restricciones).
Opcionalmente se puede filtrar por una tarifa concreta: rateCode

### RoomRatesRetrievalRequest

Mensaje petición para consultar la información publicada de un hotel (inventario, tarifas, precios y restricciones).
 
Elemento | Tipo | Obl? |  Descripción
--------- | ----------- | ----------- | -----------
credentials | **Credentials** | Sí |Credenciales de autenticación del usuario (Ver Autenticación)
hotelCode | *Integer* | Sí | Código de hotel
rateCode[] | *String* | No | Código de tarifa

### RoomRatesRetrievalResponse

Mensaje respuesta que contiene la información del hotel publicada.

Elemento | Tipo | Obl? | Descripción
--------- | ----------- | ----------- | -----------
sessionId | *String* | Sí|Identificador de la sesión que ha procesado la transacción
roomRate[] | **RoomRate** | No | Información asociada a una combinación de tarifa y modalidad de hotel
↳ @rateCode| *String* | Sí | Código de tarifa
↳ @roomCode| *String* | Sí | Código de modalidad
↳ roomRateDate| **RomRateDate** | Sí | Información relativa a un rango de fechas
↳↳ @dateFrom| *Date* | Sí | Fecha desde (dd/MM/yyyy, rangos cerrados)
↳↳ @dateTo| *Date* | Sí | Fecha hasta (dd/MM/yyyy, rangos cerrados)
↳↳ availableQuota| *Integer* | Sí | Unidades de cupo disponible
↳↳ status| *Enum* | Sí | Estado del inventario <sup>1</sup> 
↳↳ mealPlan[]| **MealPlan** | No | Información asociada al régimen alimenticio
↳↳↳ @code| *String* | Sí | Código de régimen alimenticio
↳↳↳ minimumStay| *Integer* | Sí | Días de estancia mínima (0: No hay estancia mínima)
↳↳↳ maximumStay| *Integer* | Sí | Días de estancia máxima (0: No hay límite de estancia)
↳↳↳ release| *Integer* | Sí | Días de release (0: No hay release)
↳↳↳ closedOnCheckIn| *Boolean* | Sí | Indica si no está permitida la entrada
↳↳↳ closedOnCheckOut| *Boolean* | Sí | Indica si no está permitida la salida
↳↳↳ price[]| **Price** | Sí | Precio para una ocupación
↳↳↳↳ adults| *Integer* | Sí | Número de adultos
↳↳↳↳ children| *Integer* | Sí | Número de niños
↳↳↳↳ amount| *Double* | Sí | Precio para el total de la ocupación (#.##)
↳↳↳↳ status| *Enum* | Sí | Estado de la ocupación
notification | **Notification** | No |Información de notificación (Error o Warning)
↳ type | *Enum* | Sí |Tipo de notificación (E:Error, W: Warning)
↳ code | *String* | Sí | Código de la notificación
↳ text | *String* | Sí | Texto descriptivo de la notificación

