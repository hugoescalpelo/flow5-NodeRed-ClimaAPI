# flow5-NodeRed-ClimaAPI
Este repositorio contiene el flow de NodeRed para obtener la informacion climatica por API desde openweathermap.org

## Introducción

En este flow podrá observarse un conjunto de gráficas en Dasboard, las cuales tienen como proposito reportar la información climática recibida manualmente por MQTT, la información recibida automáticamente por API y la información de varius usuarios compartida por MQTT en un broker publico

## Material Necesario

Para realizar este flow necesitas lo siguiente

- [Ubuntu 20.04](https://releases.ubuntu.com/20.04/)
- [NodeJS](https://nodejs.org/es/)
    - [NPM](https://www.npmjs.com/)
    - [NodeRed](https://nodered.org/docs/getting-started/local)
    - [Nodos Dashboard](https://flows.nodered.org/node/node-red-dashboard)
- [Mosquitto](https://mosquitto.org/)

## Material de referencia

En los siguientes enlaces puedes encontrar cursos en la plataforma de edu.codigoiot.com que te permitirán realiar las configuraciones necesarias

- [Instalación de Virutal Box y Ubuntu 20.04](https://edu.codigoiot.com/course/view.php?id=812)
- [Instalación de NodeRed](https://edu.codigoiot.com/course/view.php?id=817)
- [Introducción a NodeRed](https://edu.codigoiot.com/course/view.php?id=278)
- [Introducción a Mosquitto](https://edu.codigoiot.com/course/view.php?id=851)

### Servicios

Para que este ejercicio funcione, necesitas los siguientes servicios
- [HiveMQ](http://www.mqtt-dashboard.com/). Es un broker publico y no se necesita cuenta
- [OpenWeatherMap](https://openweathermap.org). Servicio meteorológico gratuito. Se requiere cuenta, pero no se requiere ningun pago.
## Instrucciones

### Requisitos previos

Para que este flow funcione, debes cumplir con los siguientes requisitos previos
1. Instalación de NodeJS. Se recomienda tener instalado NodeJS en alguna versión LTS. Al momento de creación de este documento, se usó la versión 16.17.0LTS. Esta instalación debe incluir las Build-Tools para hacer uso de NPM
2. Instalación de NodeRed. La instalación se realiza por NPM. Al momento de la creación de este contenido, se usó la versión 3.0.2
3. Instalar los nodos node-red-dashboard. Para ello, dirigete a la opcion "Manage Palet" de NodeRed y en la pestaña Install busca node-red-dashboard. Finalmente haz clic en instalar.
4. Instalación de Broker local Mosquitto MQTT.
5. Cuenta en OpenWeatherMap.org. Este es el servidor del cual se obtendrán los datos del clima por API
6. API Key valida. Deberás generar una API Key con tu cuenta de openweathermaps.org

### Instrucciones de preparación del entorno

Para ejecutar este flow, es necesario lo siguiente:
1. Arrancar NodeRed con el comando `node-red`
2. Importar el flow del repositorio.
3. Coloca tu API Key personal en la API Call del nodo HTTP Request.
4. Actualiza la IP del broker público.
5. Hacer clic en el boton Deploy.

### Instrucciones de operación

- Para observar el resutlado de este flow, abre un navegador y dirígete a localhost:1880/ui.
- Para activar las gráficas de clima manual, debes enviar por MQTT un mensaje que contenga un JSON con las variables ID, temp y hum.


### Notas

- La sección manual de este flow se suscribe al tema codigoIoT/fow5/mqtt en un broker local.
- El mensaje mqtt usado para probar este flow es `mosquitto_pub -h localhost -t ccodigoIoT/fow5/mqtt -m '{"ID":"Hugo Vargas","temp":18,"hum":78}'`
- Para que la gráfica historica muestre información, deben enviarse al menos 2 puntos.
- Para actualizar la IP del broker publico, se recomienda el siguiente comando `nslookup broker.hivemq.com`. Puedes usar el broker publico de tu elección.
- Para que multiples graficas sean mostradas en la sección de Histórico Público, es necesario que multiples usuarios se encuentren publicando a la vez.

## Resultados

A continuación puedes ver los nodos del flow.
![](https://github.com/hugoescalpelo/flow5-NodeRed-ClimaAPI/blob/main/Imagenes/Nodos.png?raw=true)

A continuación puede ver el tablero resultante.
![](https://github.com/hugoescalpelo/flow5-NodeRed-ClimaAPI/blob/main/Imagenes/Dashboard.png?raw=true)

## Evidencias

- [YouTube](https://youtu.be/ePnMjiTWHs0)

# Créditos

Desarrollado por Hugo Escalpelo
- [hugoescalpelo.com](https://hugoescalpelo.com/)
- [Página en Facebook](https://www.facebook.com/Hugo-Escalpelo-Profesional-337708683840136)
- [GitHub](https://github.com/hugoescalpelo)