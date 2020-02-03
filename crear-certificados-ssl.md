# Crear certificados auto-firmados

1. Descargar OpenSSL http://slproweb.com/products/Win32OpenSSL.html

2. Agregar al path la carpeta /bin que se instalo en el directorio de instalación

3. Ejecutar comando ``OpenSLL``

4. Ejecutar el siguiente comando para generar llave privada y certificado

```bash
req -x509 -sha256 -nodes -days 365 -newkey rsa:2048 -keyout privateKey.key -out certificate.crt
```
