# hotelConfiguration

Mensaje utilizado para obtener la configuración del hotel. A través de este mensaje, el proveedor podrá obtener todos 
los códigos y tipología para poder gestionar el hotel vía PUSH. Típicamente, este mensaje es el que utiliza el proveedor 
para recuperar los elementos a mapear. En resumen:

- Habitaciones del hotel así como sus ocupaciones permitidas
- Regímenes alimenticios
- Tarifas gestionables vía PUSH

### HotelConfigurationRequest

> Ejemplo petición HotelConfigurationRequest para recuperar la configuración del hotel 1234 <span class="postman-button">[![Run in Postman](https://run.pstmn.io/button.svg)](https://app.getpostman.com/run-collection/495ff7995b655b745365)</span>

````xml
<?xml version="1.0" encoding="UTF-8"?>
<HotelConfigurationRequest>
   <credentials>
      <vendorCode>FOO</vendorCode>
      <user>BAR</user>
      <password>FOOBAR</password>
   </credentials>
   <hotelCode>1234</hotelCode>
</HotelConfigurationRequest>
````

Mensaje petición para recuperar la configuración de los hoteles del proveedor. 
Opcionalmente se puede filtrar por código de hotel (hotelCode). 
Si no se indica, en la respuesta aparecerán todos los hoteles que gestiona el proveedor.
 
Elemento | Tipo | Obl? | Restricciones | Descripción
--------- | ----------- | ----------- | ----------- | -----------
credentials | **Credentials** | Sí | |Credenciales de autenticación del usuario (Ver Autenticación)
hotelCode | *Integer* | No | |Código de hotel

### HotelConfigurationResponse

> Ejemplo respuesta HotelConfigurationResponse

````xml
<?xml version="1.0" encoding="UTF-8"?>
<HotelConfigurationResponse>
    <sessionId>SUP#FOO#123456789</sessionId>
    <hotelConfig>
        <hotelCode>1234</hotelCode>
        <name>Hotetec Test</name>
        <currencyCode>EUR</currencyCode>
        <roomConfig>
            <roomCode>SGL#STD</roomCode>
            <name>Individual Estándar</name>
            <occupancy>
                <adults>1</adults>
                <children>0</children>
            </occupancy>
            <occupancy>
                <adults>1</adults>
                <children>1</children>
            </occupancy>
        </roomConfig>        
        <roomConfig>
            <roomCode>DBL#STD</roomCode>
            <name>Doble Estándar</name>
            <occupancy>
                <adults>1</adults>
                <children>0</children>
            </occupancy>
            <occupancy>
                <adults>2</adults>
                <children>0</children>
            </occupancy>
            <occupancy>
                <adults>2</adults>
                <children>1</children>
            </occupancy>
        </roomConfig>
        <mealPlanConfig>
            <mealPlanCode>RO</mealPlanCode>
            <name>Sólo alojamiento</name>
        </mealPlanConfig>
        <mealPlanConfig>
            <mealPlanCode>BB</mealPlanCode>
            <name>Alojamiento y desayuno</name>
        </mealPlanConfig>
        <mealPlanConfig>
            <mealPlanCode>HB</mealPlanCode>
            <name>Media pensión</name>
        </mealPlanConfig>
        <inventoryConfig>
            <inventoryCode>1</inventoryCode>
            <name>Inventario general</name>
        </inventoryConfig>
        <rateConfig>
            <rateCode>BASE</rateCode>
            <name>Tarifa Base</name>
            <inventoryCode>1</inventoryCode>
            <cancelPolicyType>Variable</cancelPolicyType>
        </rateConfig>
        <rateConfig>
            <rateCode>OFENRE</rateCode>
            <name>Tarifa No Reembolsable</name>
            <inventoryCode>1</inventoryCode>
            <rateProperty>
                <name>Destacada</name>
            </rateProperty>
            <cancelPolicyType>NonRefundable</cancelPolicyType>
        </rateConfig>        
    </hotelConfig>
</HotelConfigurationResponse>
````

Mensaje respuesta que contiene la configuración de los hoteles del proveedor (modalidades, regímenes, tarifas...)

Elemento | Tipo | Obl? | Descripción
--------- | ----------- | ----------- | -----------
hotelConfig[] | **HotelConfig** | |Elemento que contiene la configuración del hotel
- hotelCode | *Integer* | Sí | Código de hotel
- name | *String* | Sí |Nombre de hotel
- currencyCode | *String* | Sí | Código de divisa (Códigos  ISO 4217 )
- roomConfig[] | **RoomConfig** | Sí | Configuración de la modalidad de hotel
&nbsp;&nbsp;- roomCode | *String* | Sí |Código de modalidad
&nbsp;&nbsp;- name | *String* | Sí | Nombre de modalidad
&nbsp;&nbsp;- nestedInventoryRoomCode | *String* | No | Código de la modalidad sobre la cuál anida el inventario <sup>1</sup>
&nbsp;&nbsp;- babiesCountInOccupancy | *Boolean* | Sí | Indica si los bebés ocupan plaza <sup>2</sup>
&nbsp;&nbsp;- occupancy | **Occupancy** | Sí | Ocupación permitida en la modalidad
&nbsp;&nbsp;&nbsp;&nbsp;- adults | *Integer* | Sí | Número de adultos de la ocupación
&nbsp;&nbsp;&nbsp;&nbsp;- children | *Integer* | Sí | Número de niños de la ocupación
- mealPlanConfig[] | **MealPlanConfig** | Sí | Configuración de la regímenes alimenticios de hotel
&nbsp;&nbsp;- mealPlanCode | *String* | Sí |Código de régimen alimentício
&nbsp;&nbsp;- name | *String* | Sí | Nombre de régimen alimentício
- inventoryConfig[] | **InventoryConfig** | Sí | Configuración de los inventarios del hotel <sup>3</sup>
&nbsp;&nbsp;- inventoryCode | *Integer* | Sí |Código de inventario
&nbsp;&nbsp;- name | *String* | Sí | Nombre de inventario
- rateConfig[] | **RateConfig** | Sí | Configuración de las tarifas del hotel
&nbsp;&nbsp;- rateCode | *String* | Sí |Código de tarifa
&nbsp;&nbsp;- name | *String* | Sí | Nombre de tarifa
&nbsp;&nbsp;- inventoryCode | *Integer* | Sí | Inventario asociado a la tarifa
&nbsp;&nbsp;- rateProperty | **RateProperty** | No | Propiedad de la tarifa
&nbsp;&nbsp;&nbsp;&nbsp;- name | **String** | Sí | Nombre de la propiedad
&nbsp;&nbsp;&nbsp;&nbsp;- value | **String** | No | Valor de la propiedad. Ej: Propiedad Mayores de, value 55
&nbsp;&nbsp;- cancelPolicyType | *Enum* | Sí | Políticas de cancelación de la tarifa (Free/NonRefundable/Variable)


<aside class="notice">
<sup>1</sup>&nbsp;&nbsp;&nbsp;Generalmente no vendra informado, sólo en aquellos hoteles que trabajan con modalidades de cupo anidado. Ej: Modalidad Doble uso individual
 utiliza el inventario de la modalidad Doble estándar.
</aside>

<aside class="notice">
<sup>2</sup>&nbsp;&nbsp;&nbsp;Si los bebés ocupan plaza, contabilizarán como children en las ocupaciones permitidas en la modalidad. 
Generalmente, el valor será false.
</aside>

<aside class="notice">
<sup>3</sup>&nbsp;&nbsp;&nbsp;Por norma general, el hotel trabaja con un único inventario y todas la tarifas utilizan el mismo.
En el caso de que el hotel utilice varios, con el inventoryCode podrá distinguir que inventario utiliza cada tarifa.
</aside>

