# Repositorio de investigación de plataforma Home Assistant
Repositorio usado para investigar capacidades de HomeAssistant como plataforma de desarrollo, principalmente orientado al desarrollo en aplicaciones de procesamiento de imágenes y modelos de visión artificial.

# Hardware usado
Por ahora, el *setup* comprende: 
  - Una Raspberry Pi 4B (2018) corriendo Home Assistant Operating System (HASSOS). Instrucciones de instalación se encuentran en: https://www.home-assistant.io/installation/raspberrypi
  - Una ESP32-CAM usada como cámara IP de baja resolución (AliExpress: www.bit.ly/3Llnrzp)
  - Una Raspberry Pi Zero W con Raspberry Pi Camera como cámara IP. 

# Instrucciones
El archivo `configuration.yaml` contiene la configuración y parámetros de Home Assistant necesarios para correr detección de objetos usando una cámara IP por medio de la plataforma DOODS. Este archivo debe ir en `config/configuration.yaml`. 

Para correr DOODS se tienen dos opciones, correrlo en un contenedor independientemente (aparte de Home Assistant) o correrlo como un *add-on* en Home Assistant. La segunda opción es la más fácil. Las instrucciones de instalación se encuentran aquí: https://www.home-assistant.io/integrations/doods/. Los settings, por ahora, se deben dejar en los valores predeterminados. 

Una vez corriendo HASSOS, se deben instalar las cámaras IP. Se incluye el archivo `esp32-cam.yaml` que es un archivo de configuración usado para *flashear* la cámara ESP32-CAM. Para esto, es necesario instalar la extensión `ESP-HOME` de Home Assistant (https://www.home-assistant.io/integrations/esphome/). Una vez instalada, se debe agregar y flashear un dispositivo usando el *Dashboard* que provee la extensión. Con esto, tendremos la cámara corriendo (se deben cambiar parámetros en el archivo para que funcione correctamente).

Cabe decir que DOODS funciona con cualquier cámara IP o con imágenes fijas, y solamente se deben agregar a Home Assistant a través de una entidad `camera` como se muestra en el archivo de configuración.

## Para instalar en PC o Mac
Se puede correr Home Assistant en una máquina virtual o como un container de Docker (Home Assistant Core) siguiendo las instrucciones de https://www.home-assistant.io/installation según el sistema operativo o máquina en donde se quiera correr.
