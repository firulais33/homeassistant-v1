# Contador de personas 
Automatizaciones que permiten contar personas que entran o salen de un lugar usando una cámara IP (ESP32-CAM) y la plataforma de detección de objetos DOODS.

# Explicación y archivos
La implementación del contador es algo rudimentaria. 

    1) se definieron áreas que representan el lado izquierdo y derecho de la imagen proveniente de la cámara, y se corre detección de personas en cada una de estas áreas en paralelo. Todo esto se puede encontrar en el archivo `image_processings.yaml`. Se dejó un espacio entre las áreas para que no haya traslape y no ocurra que se detecte a una persona dos veces, u otros casos indeseables.
    2) se crean automatizaciones que permiten detectar cuándo una persona pasa desde el área izquierda hacia la derecha y viceversa. Se pueden encontrar en el archivo `automations.yaml`. Dependiendo de la dirección se suma o se resta al contador definido en `counters.yaml`. 
    3) para que todo esto funcione, se deben incluir estos archivos en la configuración principal (`configuration.yaml`) como sigue:

            counter: !include counters.yaml
            automation: !include automations.yaml 
            image_processing: !include image_processings.yaml

# Comentarios