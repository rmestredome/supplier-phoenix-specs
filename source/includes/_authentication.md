# Autenticación

> Ejemplo elemento credentials, presente en todas las peticiones XML

````xml
<credentials>
    <systemCode>SFO</systemCode>
    <vendorCode>FOO</vendorCode>
    <user>BAR</user>
    <password>FOOBAR</password>
</credentials>
````

````json
{
   "credentials": {
       "systemCode": "SFO",
       "vendorCode": "FOO",
       "user": "BAR",
       "password": "FOOBAR"
   }
}
````

Todas las peticiones contienen el elemento credentials (ejemplo a la derecha), el cuál contiene las credenciales de autenticación.
El proveedor puede elegir si utilizar XML o JSON _(disponible próximamente)_:

- URL XML: **https://xml.hotetec.com/supplier-api/supplier/xmlservice.srv**
- URL JSON: **https://xml.hotetec.com/supplier-api/supplier/jsonservice.srv** _(disponible próximamente)_

<aside class="notice">Por favor, solicitar credenciales de acceso a <b>soporte@hotetec.com</b></aside>

