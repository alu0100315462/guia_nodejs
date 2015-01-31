![Imagen](https://github.com/alu0100315462/guia_nodejs/blob/master/nodetricolor.png)


#Guía de instalación y uso de Node.js

##Instalación
1. Descargar Node.js desde la [página de oficial de Node.js](http://nodejs.org/) haciendo
click en el botón INSTALL. Dependiendo del sistema operativo en el que se encuentre, se 
descargará un tipo de fichero diferente.
En Linux obtenemos un archivo comprimido .tar.gz.

2. Descomprimimos el fichero y con la consola nos situamos dentro de la carpeta descomprimida:
```
cd node-v0.10.36
```
3. Ejecutamos los siguientes comandos:
```
./configure
make
sudo make install
```
4. Comprobamos que se ha instalado correctamente:
```
node --version
```

##Uso de Node.js

Haremos un sencillo ejemplo de uso haciendo que Node.js imprima un mensaje por pantalla, podemos escribir la orden directamente en node o en un fichero de extensión js.
####Uso directo de node:
* Abrir Node en la consola:
```
node
```
* e introducir la orden:
```
console.log("Hola Mundo");
```
* obtenemos la siguiente salida:
![Imagen](https://github.com/alu0100315462/guia_nodejs/blob/master/node1.PNG)

####Uso mediante un fichero:
* Si escribimos las órdenes en un fichero de texto, podemos ejecutar todo el fichero con node. Ejecutando un fichero con la orden antes usada:
![Imagen](https://github.com/alu0100315462/guia_nodejs/blob/master/node2.PNG)

####Creando un servidor:
Para crear un servidor local donde poder ver en nuestro navegador la salida de la ejecución de los ficheros node.js, haremos lo siguiente:
* Escribir el siguiente código y ejecutarlo con node:
```
var http = require('http');
var server = http.createServer();
function control(petic, resp) {
resp.writeHead(200, {'content-type': 'text/plain'});
resp.write("Hola Mundo");
resp.end();
}
server.on('request', control);
server.listen(8080);
```

Se puede poner en la línea **server.listen(8080);** cualquier puerto que se quiera utilizar.

Después abriremos en el navegador la página:
```
localhost:8080
```
En mi caso, ya que he ejecutado el servidor desde el entorno Cloud9, abro la página como **nombreproyecto-nombreusuario.c9.io/**
![Imagen](https://github.com/alu0100315462/guia_nodejs/blob/master/node3.PNG)