# Arquitectura de un sistema UNIX/Linux

## Como estan formados estos sistemas?

Están formados por capas:
- Hardware: Son todos nuestros dispositivos físicos conectados al sistema (memoria, procesador, teclado, ratón, ...)
  - Kernel: Es una pieza de software que nos permite controlar todo el hardware de nuestro servidor como el uso de CPU o memoria RAM. y pasar esta información a las siguientes capas.
    - Shell: Es la interfaz entre el kernel y el usuario, permite ejecutar comandos y pasarlos a un sistema de bajo nivel.
      - Utilities (Apps): Interacción directa con el usuario, capa donde trabajan nuestros comandos y aplicaciones.

## Tarea

Qué hace cada una de estas partes (Hardware, Kernel, Shell, Utilities) y cual es la más importante en el sistema operativo? Respuesta con propias palabras.

- Hardware: Son precisamente toda la parte física de una maquina, capacidad de memoria, su procesador, resto de circuitos integrados y periféricos.
- Kernel: Es un software de bajo nivel que se encarga de interpretar el lenguaje de hardware que seria por pulsos eléctricos traducido a leguaje binario, a un lagunaje de programación con mayor lógica que permita interactuar de forma adecuada con el hardware.
- Shell: Es un software que interactúa con el kernel, aplicando una lógica mucho más avanzada para interactuar de forma más optima con el sistema.
- Utilities: Son aplicativos desarrollados para brindar funcionalidades y servicios de utilidad para el usuario final. 

En un sistema operativo, considero que lo más impórtate son las Utilidades o las aplicaciones que el sistema operativo incluye, porque para mi lo que le da sentido hacer uso de un sistema operativo es que cumpla con las necesidades y expectativas que se espera. 