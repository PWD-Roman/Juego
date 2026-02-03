Reporte de Desarrollo – Sistema de Movimiento y Animaciones del Personaje
1. Introducción

El presente reporte documenta el desarrollo completo del sistema de movimiento y animaciones del personaje principal dentro del motor Godot Engine, utilizando el lenguaje GDScript. El objetivo fue crear un jugador funcional con movimiento top-down, capaz de responder de manera inmediata a la entrada del usuario y reproducir las animaciones correspondientes según la dirección del desplazamiento.

2. Creación de la escena del jugador

Se creó una escena independiente denominada Player, utilizando como nodo raíz un CharacterBody2D, lo cual permite un manejo adecuado de físicas y colisiones.

Dentro de esta escena se agregaron los siguientes nodos:

AnimatedSprite2D: encargado de reproducir las animaciones del personaje.

CollisionShape2D: utilizado para definir el área de colisión del jugador dentro del entorno.

Esta estructura permite una correcta separación entre la lógica del personaje, la representación visual y las colisiones.

3. Configuración de animaciones

Se configuró el nodo AnimatedSprite2D con animaciones organizadas por estado y dirección, siguiendo la siguiente nomenclatura:

idle_up, idle_down, idle_left, idle_right

run_up, run_down, run_left, run_right

Esta organización facilita la selección dinámica de animaciones desde el código, permitiendo cambiar de forma eficiente entre estados de reposo y movimiento.

4. Implementación del movimiento Top-Down

El sistema de movimiento fue implementado bajo un enfoque top-down, permitiendo el desplazamiento libre del personaje en los cuatro ejes principales (arriba, abajo, izquierda y derecha).

Se utilizó el método Input.get_vector() para capturar la entrada del jugador, lo cual permite:

Un control fluido del movimiento.

Compatibilidad con teclado y controladores.

Normalización automática del vector de movimiento.

La velocidad del personaje se definió mediante una variable configurable, facilitando futuros ajustes.

5. Lógica de dirección y animación

El sistema determina dinámicamente la última dirección válida del personaje con base en el eje dominante del movimiento (horizontal o vertical). Esta dirección se almacena para:

Mantener la orientación correcta al detenerse.

Reproducir la animación adecuada en cada estado.

Las animaciones se actualizan en tiempo real según:

Si el personaje está en movimiento → animación run

Si el personaje está detenido → animación idle

Además, se implementó una validación para evitar la reproducción innecesaria de animaciones ya activas, mejorando el rendimiento y la fluidez visual.

6. Resultado final

Como resultado del desarrollo:

Se creó exitosamente la escena del jugador desde cero.

Se configuraron y enlazaron correctamente las animaciones direccionales.

Se implementó un sistema de movimiento top-down funcional y fluido.

El personaje responde de manera inmediata a la entrada del usuario.

Las animaciones cambian correctamente según la dirección y el estado del movimiento.

Este sistema sirve como base sólida para futuras implementaciones como ataques, interacciones, colisiones avanzadas o integración con un sistema de estados más complejo.

7. Conclusión

El desarrollo del sistema de movimiento y animaciones del personaje fue completado de manera satisfactoria, logrando un comportamiento coherente, escalable y acorde a los estándares de desarrollo en Godot Engine. El resultado obtenido cumple con los objetivos planteados y deja una base estable para la expansión del proyecto.
