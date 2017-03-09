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
    <roomRate rateCode="NORMAL" roomCode="SGL#STD">
        <dateFrom>01/01/2016</dateFrom>
        <dateTo>02/01/2016</dateTo>
        <availableQuota>9</availableQuota>
        <status>Open</status>
    </roomRate>
    <roomRate rateCode="NORMAL" roomCode="DBL#STD">
        <dateFrom>01/01/2016</dateFrom>
        <dateTo>01/01/2016</dateTo>
        <availableQuota>5</availableQuota>
        <status>Open</status>
    </roomRate>
</RoomRatesUpdateRequest>
````

````shell
curl 
   -H "Content-type:text/xml"  
   -d "<RoomRatesUpdateRequest>   
           <credentials>
               <vendorCode>FOO</vendorCode>
               <user>BAR</user>
               <password>FOOBAR</password>
           </credentials>   
           <roomRate rateCode="NORMAL" roomCode="SGL#STD">
               <dateFrom>01/01/2016</dateFrom>
               <dateTo>02/01/2016</dateTo>
               <availableQuota>9</availableQuota>
               <status>Open</status>
           </roomRate>
           <roomRate rateCode="NORMAL" roomCode="DBL#STD">
               <dateFrom>01/01/2016</dateFrom>
               <dateTo>01/01/2016</dateTo>
               <availableQuota>5</availableQuota>
               <status>Open</status>
           </roomRate>
       </RoomRatesUpdateRequest>" 
	http://xml.hotetec.com/supplier-api/supplier/xmlservice.srv
````

> Ejemplo RoomRatesUpdateRequest actualizando inventario, precios y restricciones para los régimenes RO y BB de la tarifa NORMAL, modalidad DBL#STD
&nbsp;&nbsp;<span class="postman-button">[![Run in Postman](https://run.pstmn.io/button.svg)](https://app.getpostman.com/run-collection/495ff7995b655b745365)</span>

````xml
<?xml version="1.0" encoding="UTF-8"?>
<RoomRatesUpdateRequest>
    <credentials>
        <vendorCode>FOO</vendorCode>
        <user>BAR</user>
        <password>FOOBAR</password>
    </credentials>
    <roomRate rateCode="NORMAL" roomCode="DBL#STD">
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

````shell
curl 
   -H "Content-type:text/xml"  
   -d "<RoomRatesUpdateRequest>
           <credentials>
               <vendorCode>FOO</vendorCode>
               <user>BAR</user>
               <password>FOOBAR</password>
           </credentials>
           <roomRate rateCode="NORMAL" roomCode="DBL#STD">
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
       </RoomRatesUpdateRequest>" 
	http://xml.hotetec.com/supplier-api/supplier/xmlservice.srv
````

> Ejemplo respuesta RoomRatesUpdateResponse procesada correctamente

````xml
<?xml version="1.0" encoding="UTF-8"?>
<RoomRatesUpdateResponse>
    <sessionId>SUP#FOO#123456789</sessionId>
</RoomRatesUpdateResponse>
````

````shell
"<?xml version="1.0" encoding="UTF-8"?>
<RoomRatesUpdateResponse>
    <sessionId>SUP#FOO#123456789</sessionId>
</RoomRatesUpdateResponse>"
````

Mensaje utilizado para la actualización de inventario y tarifas (precios, paros de venta y restricciones) de un hotel.
Si únicamente se quiere actualizar inventario, no será necesario informar <mealPlan>

### RoomRatesUpdateRequest

Mensaje petición de actualización de inventario y tarifas de hotel.
 
Elemento | Tipo | Obl? |  Descripción
--------- | ----------- | ----------- | -----------
credentials | **Credentials** | Sí |Credenciales de autenticación del usuario (Ver Autenticación)
roomRate[] | **RoomRate** | Sí | Información asociada a una combinación de tarifa y modalidad de hotel
&nbsp;&nbsp;- @rateCode| *String* | Sí | Código de tarifa
&nbsp;&nbsp;- @roomCode| *String* | Sí | Código de modalidad
&nbsp;&nbsp;- dateFrom| *Date* | Sí | Fecha desde (dd/MM/yyyy, rangos cerrados)
&nbsp;&nbsp;- dateTo| *Date* | Sí | Fecha hasta (dd/MM/yyyy, rangos cerrados)
&nbsp;&nbsp;- availableQuota| *Integer* | Sí | Unidades de cupo disponible
&nbsp;&nbsp;- status| *Enum* | Sí | Estado del inventario <sup>1</sup> 
&nbsp;&nbsp;- mealPlan[]| **MealPlan** | No | Información asociada al régimen alimenticio
&nbsp;&nbsp;&nbsp;&nbsp;- @code| *String* | Sí | Código de régimen alimenticio
&nbsp;&nbsp;&nbsp;&nbsp;- status| *Enum* | Sí | Estado del régimen <sup>1</sup>
&nbsp;&nbsp;&nbsp;&nbsp;- minimumStay| *Integer* | Sí | Días de estancia mínima (0: No hay estancia mínima)
&nbsp;&nbsp;&nbsp;&nbsp;- maximumStay| *Integer* | Sí | Días de estancia máxima (0: No hay límite de estancia)
&nbsp;&nbsp;&nbsp;&nbsp;- release| *Integer* | Sí | Días de release (0: No hay release)
&nbsp;&nbsp;&nbsp;&nbsp;- closedOnCheckIn| *Boolean* | Sí | Indica si no está permitida la entrada
&nbsp;&nbsp;&nbsp;&nbsp;- closedOnCheckOut| *Boolean* | Sí | Indica si no está permitida la salida
&nbsp;&nbsp;&nbsp;&nbsp;- price[]| **Price** | Sí | Precio para una ocupación
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;- adults| *Integer* | Sí | Número de adultos
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;- children| *Integer* | Sí | Número de niños
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;- amount| *Double* | Sí | Precio para el total de la ocupación (#.##)
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;- status| *Enum* | Sí | Estado de la ocupación <sup>1</sup>

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
&nbsp;&nbsp;- type | *Enum* | Sí |Tipo de notificación (E:Error, W: Warning)
&nbsp;&nbsp;- code | *String* | Sí | Código de la notificación
&nbsp;&nbsp;- text | *String* | Sí | Texto descriptivo de la notificación

