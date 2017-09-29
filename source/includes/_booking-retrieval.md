# BookingRetrieval

> Ejemplo BookingRetrievalRequest para recuperar una reserva en particular
&nbsp;&nbsp;<span class="postman-button">[![Run in Postman](https://run.pstmn.io/button.svg)](https://app.getpostman.com/run-collection/495ff7995b655b745365)</span>

````xml
<?xml version="1.0" encoding="UTF-8"?>
<BookingRetrievalRequest>
    <credentials>
        <systemCode>SFO</systemCode>
        <vendorCode>FOO</vendorCode>
        <user>BAR</user>
        <password>FOOBAR</password>
    </credentials>   
    <reference>EPL10032017140800-SALE</reference>
</BookingRetrievalRequest>
````

````json
{
  "BookingRetrievalRequest": {
    "credentials": {
      "systemCode": "SFO",
      "vendorCode": "FOO",
      "user": "BAR",
      "password": "FOOBAR"
    },
    "reference": "EPL10032017140800-SALE"
  }
}
````

> Ejemplo BookingRetrievalRequest para para recuperar las reservas de un hotel en un determinado rango de fechas (creadas, canceladas o modificadas)
&nbsp;&nbsp;<span class="postman-button">[![Run in Postman](https://run.pstmn.io/button.svg)](https://app.getpostman.com/run-collection/495ff7995b655b745365)</span>

````xml
<?xml version="1.0" encoding="UTF-8"?>
<BookingRetrievalRequest>
    <credentials>
        <systemCode>SFO</systemCode>
        <vendorCode>FOO</vendorCode>
        <user>BAR</user>
        <password>FOOBAR</password>
    </credentials>   
    <hotelCode>1234</hotelCode>
    <dateFrom>10/03/2017 14:30</dateFrom>
    <dateTo>10/03/2017 15:00</dateTo>
</BookingRetrievalRequest>
````

````json
{
  "BookingRetrievalRequest": {
    "credentials": {
      "systemCode": "SFO",
      "vendorCode": "FOO",
      "user": "BAR",
      "password": "FOOBAR"
    },
    "hotelCode": "1234",
    "dateFrom": "10/03/2017 14:30",
    "dateTo": "10/03/2017 15:00"
  }
}
````

> Ejemplo respuesta BookingRetrievalResponse procesada correctamente
La reserva recuperada contiene dos habitaciones: 1 doble + 1 individual

````xml
<?xml version="1.0" encoding="UTF-8"?>
<BookingRetrievalResponse>
    <sessionId>SUP#FOO#123456789</sessionId>
    <booking>
        <reference>EPL10032017140800-SALE</reference>
        <creationDate>10/03/2017 14:15</creationDate>
        <checkIn>15/04/2017</checkIn>
        <checkOut>18/04/2017</checkOut>
        <status>Confirmed</status>
        <amount>550.00</amount>
        <bookingClient>
            <clientCode>EPL</clientCode>
            <clientName>Europlayas</clientName>
            <clientReference>AA45645D55</clientReference>
        </bookingClient>
        <endCustomer>
            <name>Elena Ballester</name>
            <mail>elena_ballester1234@mail.com</mail>
            <phone>003466667788</phone>
        </endCustomer>
        <hotelCode>1234</hotelCode>
        <bookingRoom id="1">
            <checkIn>15/04/2017</checkIn>
            <checkOut>17/04/2017</checkOut>
            <status>Confirmed</status>
            <roomCode>DBL#STD</roomCode>
            <mealPlanCode>BB</mealPlanCode>
            <amount>350.00</amount>
            <roomRateDay>
                <day>15/04/2017</day>
                <rateCode>BASE</rateCode>
                <amount>116.67</amount>
            </roomRateDay>
            <roomRateDay>
                <day>16/04/2017</day>
                <rateCode>BASE</rateCode>
                <amount>116.67</amount>
            </roomRateDay>
            <roomRateDay>
                <day>17/04/2017</day>
                <rateCode>BASE</rateCode>
                <amount>116.67</amount>
            </roomRateDay>
            <guest id="1">
                <type>Adult</type>
                <amount>175.00</amount>
            </guest>
            <guest id="2">
                <type>Adult</type>
                <amount>175.00</amount>
            </guest>
        </bookingRoom>
        <bookingRoom id="2">
            <checkIn>15/04/2017</checkIn>
            <checkOut>17/04/2017</checkOut>
            <status>Confirmed</status>
            <roomCode>SGL#STD</roomCode>
            <mealPlanCode>BB</mealPlanCode>
            <amount>150.00</amount>
            <roomRateDay>
                <day>15/04/2017</day>
                <rateCode>BASE</rateCode>
                <amount>50.00</amount>
            </roomRateDay>
            <roomRateDay>
                <day>16/04/2017</day>
                <rateCode>BASE</rateCode>
                <amount>50.00</amount>
            </roomRateDay>
            <roomRateDay>
                <day>17/04/2017</day>
                <rateCode>BASE</rateCode>
                <amount>50.00</amount>
            </roomRateDay>
            <guest id="3">
                <type>Adult</type>
                <amount>100.00</amount>
            </guest>
            <guest id="4">
                <type>Child</type>
                <amount>50.00</amount>
            </guest>
        </bookingRoom>
        <bookingSupplement>
            <code>PKG</code>
            <code>Parking</code>
            <description>Suplemento Parking toda la estancia</description>
            <checkIn>15/04/2017</checkIn>
            <checkOut>17/04/2017</checkOut>
            <amount>50.00</amount>
        </bookingSupplement>
        <remark>
            <code>GENERAL</code>
            <from>Hotel</from>
            <to>Client</to>
            <text>Piscina cerrada hasta el 15/04/2017</text>
        </remark>
        <remark>
            <code>GENERAL</code>
            <from>Client</from>
            <to>Hotel</to>
            <text>Por favor, habitaciones no fumadores</text>
        </remark>
        <paymentCardDetail>
            <holder>Elena Ballester</holder>
            <number>4111111111111111</number>
            <expiryDate>01/01/2020</expiryDate>
            <securityCode>123</securityCode>
        </paymentCardDetail>
    </booking>
</BookingRetrievalResponse>
````

````json
{
  "BookingRetrievalResponse": {
    "sessionId": "SUP#FOO#123456789",
    "booking": {
      "reference": "EPL10032017140800-SALE",
      "creationDate": "10/03/2017 14:15",
      "checkIn": "15/04/2017",
      "checkOut": "18/04/2017",
      "status": "Confirmed",
      "amount": "550.00",
      "bookingClient": {
        "clientCode": "EPL",
        "clientName": "Europlayas",
        "clientReference": "AA45645D55"
      },
      "endCustomer": {
        "name": "Elena Ballester",
        "mail": "elena_ballester1234@mail.com",
        "phone": "003466667788"
      },
      "hotelCode": "1234",
      "bookingRoom": [
        {
          "id": "1",
          "checkIn": "15/04/2017",
          "checkOut": "17/04/2017",
          "status": "Confirmed",
          "roomCode": "DBL#STD",
          "mealPlanCode": "BB",
          "amount": "350.00",
          "roomRateDay": [
            {
              "day": "15/04/2017",
              "rateCode": "BASE",
              "amount": "116.67"
            },
            {
              "day": "16/04/2017",
              "rateCode": "BASE",
              "amount": "116.67"
            },
            {
              "day": "17/04/2017",
              "rateCode": "BASE",
              "amount": "116.67"
            }
          ],
          "guest": [
            {
              "id": "1",
              "type": "Adult",
              "amount": "175.00"
            },
            {
              "id": "2",
              "type": "Adult",
              "amount": "175.00"
            }
          ]
        },
        {
          "id": "2",
          "checkIn": "15/04/2017",
          "checkOut": "17/04/2017",
          "status": "Confirmed",
          "roomCode": "SGL#STD",
          "mealPlanCode": "BB",
          "amount": "150.00",
          "roomRateDay": [
            {
              "day": "15/04/2017",
              "rateCode": "BASE",
              "amount": "50.00"
            },
            {
              "day": "16/04/2017",
              "rateCode": "BASE",
              "amount": "50.00"
            },
            {
              "day": "17/04/2017",
              "rateCode": "BASE",
              "amount": "50.00"
            }
          ],
          "guest": [
            {
              "id": "3",
              "type": "Adult",
              "amount": "100.00"
            },
            {
              "id": "4",
              "type": "Child",
              "amount": "50.00"
            }
          ]
        }
      ],
      "bookingSupplement": {
        "code": [
          "PKG",
          "Parking"
        ],
        "description": "Suplemento Parking toda la estancia",
        "checkIn": "15/04/2017",
        "checkOut": "17/04/2017",
        "amount": "50.00"
      },
      "remark": [
        {
          "code": "GENERAL",
          "from": "Hotel",
          "to": "Client",
          "text": "Piscina cerrada hasta el 15/04/2017"
        },
        {
          "code": "GENERAL",
          "from": "Client",
          "to": "Hotel",
          "text": "Por favor, habitaciones no fumadores"
        }
      ],
      "paymentCardDetail": {
        "holder": "Elena Ballester",
        "number": "4111111111111111",
        "expiryDate": "01/01/2020",
        "securityCode": "123"
      }
    }
  }
}
````

Mensaje utilizado para recuperación de reservas. Se puede recuperar una reserva en particular (filtrando por reference),
o bien las reservas de un hotel creadas, canceladas o modificadas dentro de un rango de fechas.

### BookingRetrievalRequest

Mensaje petición de recuperación de reservas
 
Elemento | Tipo | Obl? |  Descripción
--------- | ----------- | ----------- | -----------
credentials | **Credentials** | Sí |Credenciales de autenticación del usuario (Ver Autenticación)
reference | *String* | No<sup>1</sup> | Localizador de la reserva
hotelCode | *Integer* | Sí | Código de hotel
dateFrom | *DateTime* | Sí | Fecha desde. Devolverá todas las reservas que se hayan creado, cancelado o modificado a partir de esta fecha (dd/MM/yyy HH:mm)
dateTo | *DateTime* | Sí | Fecha hasta. Devolverá todas las reservas que se hayan creado, cancelado o modificado hasta esta fecha (dd/MM/yyy HH:mm)
notificationStatus | *Enum* | No | Filtro por estado de notificación de reserva (Delivered: Notificada / UnDelivered: No notificada) No<sup>2</sup>

<aside class="notice">
<sup>1</sup>&nbsp;&nbsp;&nbsp;Si no se informa localizador de la reserva (reference), es obligatorio informar el resto de parámetros (hotelCode, dateFrom, dateTo)
</aside>

<aside class="notice">
<sup>2</sup>&nbsp;&nbsp;&nbsp;Si no se informa, se devolverán todas las reservas sea cual sea su estado. Una reserva se marca como notificada cuando se entrega vía PUSH o bien se devuelve en alguna respuesta BookingRetrievalResponse.
</aside>

### RoomRatesRetrievalResponse

Mensaje respuesta de recuperación de reservas

Elemento | Tipo | Obl? | Descripción
--------- | ----------- | ----------- | -----------
sessionId | *String* | Sí|Identificador de la sesión que ha procesado la transacción
booking[] | **Booking** | No | Información de una reserva de hotel
↳ reference| *String* | Sí | Localizador de la reserva
↳ creationDate| *DateTime* | Sí | Fecha de creación de la reserva (dd/MM/yyy HH:mm)
↳ checkIn| *Date* | Sí | Fecha de entrada (dd/MM/yyy)
↳ checkOut| *Date* | Sí | Fecha de salida (dd/MM/yyy)
↳ status| *Enum* | Sí | Estado de la reserva (Confirmed, Cancelled, OnRequest)
↳ amount| *Double* | Sí | Importe total de la reserva (#.##)
↳ bookingClient| **BookingClient** | Sí | Información del cliente que ha realizado la reserva, refiriéndose a la agencia (Ej: Logitravel), OTA (Ej: Booking.com), o el propio hotel
↳↳ clientCode| *String* | Sí | Código de cliente
↳↳ clientName| *String* | Sí | Nombre de cliente
↳↳ clientReference| *String* | Sí | Referencia de la reserva del cliente (habitualmente su localizador)
↳ endCustomer| **EndCustomer** | Sí | Información del cliente final de la reserva
↳↳ name| *String* | Sí | Nombre del cliente final
↳↳ birthDate| *Date* | No | Fecha de nacimiento (dd/MM/yyy)
↳↳ mail| *String* | No | Email del cliente final
↳↳ phone| *String* | No | Teléfono de contacto del cliente final
↳↳ nationality| *String* | No | Nacionadlidad (2 letter ISO 3166)
↳ hotelCode| *Integer* | Sí | Código de hotel
↳ currencyCode| *String* | Sí | Código de divisa (Códigos ISO 4217)
↳ bookingRoom[]| **BookingRoom** | Sí | Información de habitación de hotel reservada
↳↳ checkIn| *Date* | Sí | Fecha de entrada (dd/MM/yyy)
↳↳ checkOut| *Date* | Sí | Fecha de salida (dd/MM/yyy)
↳↳ status| *Enum* | Sí | Estado de la reserva (Confirmed, Cancelled, OnRequest)
↳↳ roomCode| *String* | Sí | Código de habitación
↳↳ mealPlanCode| *String* | Sí | Código de régimen alimenticio
↳↳ amount| *Double* | Sí | Importe de la habitación reservada (#.##)
↳↳ roomRateDay[]| **RoomRateDay** | Sí | Desglose de reserva por día, informando la tarifa y precio correspondiente a cada día de la estancia
↳↳↳ day| *Date* | Sí | Día de la estancia (dd/MM/yyy)
↳↳↳ rateCode| *String* | No | Código de tarifa
↳↳↳ amount| *String* | Sí | Importe del día
↳↳ guest[]| **Guest** | Sí | Pasajero de la reserva
↳↳↳ @id| *Integer* | Sí | Identificador del pasajero
↳↳↳ type| *Enum* | Sí | Tipo (Adult, Child, Baby)
↳↳↳ amount| *Double* | Sí | Importe correspondiente al pasajero
↳↳↳ birthDate| *Date* | No | Fecha de nacimiento
↳ bookingSupplement[]| **BookingSupplement** | No | Información de suplemento reservado
↳↳ code| *String* | Sí | Código del suplemento opcional reservado
↳↳ name| *String* | Sí | Nombre del suplemento opcional reservado
↳↳ description| *String* | No | Descripción detallada del suplemento opcional reservado
↳↳ checkIn| *Date* | No | Fecha de inicio del suplemento (dd/MM/yyy)
↳↳ checkOut| *Date* | No | Fecha de fin del suplemento (dd/MM/yyy)
↳↳ bookingRoomId| *Integer* | No | Identificador de la habitación reservada, si el suplemento referencia a una habitación en concreto
↳↳ guestId[]| *Integer* | No | Identificador del pasajero al que se hace referencia, si el suplemento referencia a un pasajero/os en concreto
↳↳ amount| *Double* | Sí | Importe total del suplemento opcional reservado
↳↳ mandatory| *Boolean* | Sí | Indica si el suplemento es obligatorio (true) o opcional (false)
↳ paymentCardDetail| **PaymentCardDetail** | No | Detalles de la tarjeta que ha realizado el pago
↳↳ holder| *String* | Sí | Nombre del titular de la tarjeta
↳↳ number| *String* | Sí | Número de la tarjeta
↳↳ expiryDate| *Date* | Sí | Fecha de caducidad (dd/MM/yyy)
↳↳ securityCode| *String* | Sí | Código de seguridad (cvc2)

