# RoomRatesRetrieval

> Ejemplo RoomRatesRetrievalRequest para recuperar la información publicada (inventario, precios y restricciones) de la tarifa  BASE
&nbsp;&nbsp;<span class="postman-button">[![Run in Postman](https://run.pstmn.io/button.svg)](https://app.getpostman.com/run-collection/495ff7995b655b745365)</span>

````xml
<?xml version="1.0" encoding="UTF-8"?>
<RoomRatesRetrievalRequest>   
    <credentials>
        <vendorCode>FOO</vendorCode>
        <user>BAR</user>
        <password>FOOBAR</password>
    </credentials>   
    <hotelCode>1234</hotelCode>
    <rateCode>BASE</rateCode>    
</RoomRatesRetrievalRequest>
````

````shell
curl 
   -H "Content-type:text/xml"  
   -d "<RoomRatesRetrievalRequest>   
           <credentials>
               <vendorCode>FOO</vendorCode>
               <user>BAR</user>
               <password>FOOBAR</password>
           </credentials>   
           <hotelCode>1234</hotelCode>
           <rateCode>BASE</rateCode>    
       </RoomRatesRetrievalRequest>" 
	http://xml.hotetec.com/supplier-api/supplier/xmlservice.srv
````

> Ejemplo respuesta RoomRatesRetrievalResponse procesada correctamente

````xml
<?xml version="1.0" encoding="UTF-8"?>
<RoomRatesRetrievalResponse>
    <sessionId>SUP#FOO#123456789</sessionId>
    <roomRate rateCode="BASE" roomCode="DBL#STD">
        <dateFrom>01/01/2017</dateFrom>
        <dateTo>31/01/2017</dateTo>
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
    <roomRate rateCode="BASE" roomCode="DBL#STD">
        <dateFrom>01/02/2017</dateFrom>
        <dateTo>28/02/2017</dateTo>
        <availableQuota>5</availableQuota>
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
                <amount>110.0</amount>
                <status>Open</status>
            </price>
            <price>
                <adults>2</adults>
                <children>1</children>
                <amount>135.0</amount>
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
    <roomRate rateCode="BASE" roomCode="SGL#STD">
        <dateFrom>01/01/2017</dateFrom>
        <dateTo>31/01/2017</dateTo>
        <availableQuota>1</availableQuota>
        <status>Open</status>
        <mealPlan code="RO">
            <status>Open</status>
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
    </roomRate>
</RoomRatesRetrievalResponse>
````

````shell
"<?xml version="1.0" encoding="UTF-8"?>
 <RoomRatesRetrievalResponse>
     <sessionId>SUP#FOO#123456789</sessionId>
     <roomRate rateCode="BASE" roomCode="DBL#STD">
         <dateFrom>01/01/2017</dateFrom>
         <dateTo>31/01/2017</dateTo>
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
     <roomRate rateCode="BASE" roomCode="DBL#STD">
         <dateFrom>01/02/2017</dateFrom>
         <dateTo>28/02/2017</dateTo>
         <availableQuota>5</availableQuota>
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
                 <amount>110.0</amount>
                 <status>Open</status>
             </price>
             <price>
                 <adults>2</adults>
                 <children>1</children>
                 <amount>135.0</amount>
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
     <roomRate rateCode="BASE" roomCode="SGL#STD">
         <dateFrom>01/01/2017</dateFrom>
         <dateTo>31/01/2017</dateTo>
         <availableQuota>1</availableQuota>
         <status>Open</status>
         <mealPlan code="RO">
             <status>Open</status>
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
     </roomRate>
 </RoomRatesRetrievalResponse>"
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
&nbsp;&nbsp;- @rateCode| *String* | Sí | Código de tarifa
&nbsp;&nbsp;- @roomCode| *String* | Sí | Código de modalidad
&nbsp;&nbsp;- dateFrom| *Date* | Sí | Fecha desde (dd/MM/yyyy, rangos cerrados)
&nbsp;&nbsp;- dateTo| *Date* | Sí | Fecha hasta (dd/MM/yyyy, rangos cerrados)
&nbsp;&nbsp;- availableQuota| *Integer* | Sí | Unidades de cupo disponible
&nbsp;&nbsp;- status| *Enum* | Sí | Estado del inventario
&nbsp;&nbsp;- mealPlan[]| **MealPlan** | No | Información asociada al régimen alimenticio
&nbsp;&nbsp;&nbsp;&nbsp;- @code| *String* | Sí | Código de régimen alimenticio
&nbsp;&nbsp;&nbsp;&nbsp;- status| *Enum* | Sí | Estado del régimen
&nbsp;&nbsp;&nbsp;&nbsp;- minimumStay| *Integer* | Sí | Días de estancia mínima (0: No hay estancia mínima)
&nbsp;&nbsp;&nbsp;&nbsp;- maximumStay| *Integer* | Sí | Días de estancia máxima (0: No hay límite de estancia)
&nbsp;&nbsp;&nbsp;&nbsp;- release| *Integer* | Sí | Días de release (0: No hay release)
&nbsp;&nbsp;&nbsp;&nbsp;- closedOnCheckIn| *Boolean* | Sí | Indica si no está permitida la entrada
&nbsp;&nbsp;&nbsp;&nbsp;- closedOnCheckOut| *Boolean* | Sí | Indica si no está permitida la salida
&nbsp;&nbsp;&nbsp;&nbsp;- price[]| **Price** | Sí | Precio para una ocupación
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;- adults| *Integer* | Sí | Número de adultos
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;- children| *Integer* | Sí | Número de niños
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;- amount| *Double* | Sí | Precio para el total de la ocupación (#.##)
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;- status| *Enum* | Sí | Estado de la ocupación
notification | **Notification** | No |Información de notificación (Error o Warning)
&nbsp;&nbsp;- type | *Enum* | Sí |Tipo de notificación (E:Error, W: Warning)
&nbsp;&nbsp;- code | *String* | Sí | Código de la notificación
&nbsp;&nbsp;- text | *String* | Sí | Texto descriptivo de la notificación

