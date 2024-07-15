# Proyecto NUCLEO-H755ZI-Q con Ethernet y lwIP

Este proyecto configura y utiliza el puerto Ethernet de la placa NUCLEO-H755ZI-Q para enviar mensajes a través del protocolo UDP a una PC y permite realizar PING a la placa. El proyecto sigue el tutorial de STMicroelectronics disponible en [este enlace](https://community.st.com/t5/stm32-mcus/how-to-create-a-project-for-stm32h7-with-ethernet-and-lwip-stack/ta-p/49308).

## Descripción

El código configura la placa NUCLEO-H755ZI-Q para:
- Enviar un mensaje UDP a una PC con la dirección IP `192.168.100.246`.
- Responder a solicitudes de PING.
- Utilizar una dirección IP estática `192.168.100.123` y para el gateway `192.168.100.1`.

## Instalación

Para instalar y configurar el proyecto, sigue estos pasos:

1. Clona este repositorio en tu máquina local:
    ```sh
    git clone <URL_DEL_REPOSITORIO>
    ```

2. Abre el proyecto en tu entorno de desarrollo preferido (por ejemplo, STM32CubeIDE).

3. Asegúrate de tener las siguientes dependencias instaladas:
    - STM32CubeMX
    - STM32CubeIDE
    - lwIP stack

4. Configura el entorno de desarrollo para compilar y cargar el código en la placa NUCLEO-H755ZI-Q.

## Uso

1. Conecta la placa NUCLEO-H755ZI-Q a tu red local mediante un cable Ethernet.

2. Compila y carga el código en la placa utilizando STM32CubeIDE.

3. La placa debería obtener la dirección IP estática `192.168.100.123`.

4. Para enviar un mensaje UDP a la PC:
    - Asegúrate de que la PC tenga la dirección IP `192.168.100.246`.
    - Abre una terminal en la PC y ejecuta el siguiente comando para escuchar el mensaje UDP en el puerto `55151`:
        ```sh
        netcat -lup 55151
        ```
    - El mensaje se enviará automáticamente al iniciar la placa.

5. Para hacer PING a la placa:
    - Desde una terminal en la PC, ejecuta:
        ```sh
        ping 192.168.100.123
        ```

## Contribución

Si deseas contribuir a este proyecto, por favor sigue estos pasos:

1. Haz un fork del repositorio.
2. Crea una nueva rama (`git checkout -b feature/nueva-funcionalidad`).
3. Realiza tus cambios y haz commit (`git commit -am 'Añadir nueva funcionalidad'`).
4. Sube tus cambios a tu fork (`git push origin feature/nueva-funcionalidad`).
5. Abre un Pull Request en este repositorio.


## Autores

- Facundo Quiroga (https://github.com/fqga) - Autor principal y mantenedor.

## Tecnologías

- STM32CubeMX
- STM32CubeIDE
- lwIP stack
- C/C++
