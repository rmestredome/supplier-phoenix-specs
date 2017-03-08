# Protocolo de conexión

- Mensajería XML sobre HTTP. El proveedor tiene que enviar las peticiones por <b>HTTP RAW POST</b> (POST sin paso de parámetros).
- La codificación de los mensajes es <b>UTF-8</b>.
- Todos los mensajes soportan compresión <b>gzip</b>. Si el proveedor desea recibir las respuestas XML comprimidas, tiene que especificarlo en las cabeceras HTTP de su petición

`Accept-encoding: gzip`
