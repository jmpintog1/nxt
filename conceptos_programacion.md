# Conceptos Básicos en NXC

Para darle vida a nuestra Base Motriz, dejaremos atrás los lenguajes de bloques visuales y utilizaremos **NXC** (*Not eXactly C*). NXC es un lenguaje de programación basado en texto, muy similar a C, lo que lo convierte en una excelente herramienta para introducir la lógica de programación formal y aplicarla a fenómenos del mundo físico, como el movimiento, la velocidad y las trayectorias.

## 1. La Estructura de un Programa

Todo programa en NXC necesita un punto de partida principal. Al igual que en C, utilizamos una "tarea principal" llamada `task main()`. Dentro de las llaves `{ }` irán todas las instrucciones que el robot ejecutará de forma secuencial (una instrucción tras otra).

```c
task main()
{
    // Aquí escribiremos nuestras instrucciones.
    // Los textos con doble barra son "comentarios" y el robot los ignora.
}
```

## 2. Instrucciones de Movimiento (Cinemática Básica)

En el capítulo de ensamblaje conectamos los motores de tracción a los **puertos B y C**. Ahora, le daremos instrucciones precisas controlando dos variables fundamentales del movimiento: la potencia y el tiempo.

### Encender los motores: `OnFwd` y `OnRev`
Para avanzar (*Forward*) o retroceder (*Reverse*), indicamos qué motores queremos mover y a qué porcentaje de potencia (de 0 a 100). La potencia se traducirá directamente en la velocidad angular de las ruedas.

* `OnFwd(OUT_BC, 75);` -> Enciende los motores B y C hacia adelante al 75% de su capacidad.
* `OnRev(OUT_B, 50);`  -> Enciende solo el motor B hacia atrás al 50%.

### El control del tiempo: `Wait`
El microcontrolador del NXT ejecuta las líneas de código en fracciones de segundo. Si le decimos "avanza" y en la siguiente línea "apágate", lo hará tan rápido que no veremos movimiento. Necesitamos la función `Wait()`, que pausa la lectura del código (pero mantiene la acción física en curso) durante una cantidad de milisegundos.

* `Wait(2000);` -> Mantiene la acción anterior durante 2 segundos (2000 ms).

> **Nota Pedagógica:** Al combinar una potencia constante con un tiempo determinado en línea recta, podemos experimentar físicamente con el Movimiento Rectilíneo Uniforme (MRU). Midiendo la distancia que recorre el robot en esos 2 segundos, se puede calcular su velocidad real.

### Detener los motores: `Off`
Para detener el movimiento y frenar activamente los motores, usamos el comando `Off()`.

* `Off(OUT_BC);` -> Detiene inmediatamente los motores B y C.

## 3. Nuestro Primer Código: Avanzar y Girar

Vamos a integrar estos conceptos en un programa completo. El objetivo es que nuestra Base Motriz avance en línea recta por 2 segundos, realice un giro hacia la derecha, y se detenga.

Abre BricxCC, crea un nuevo archivo (*File > New*) y escribe el siguiente código:

```c
task main()
{
    // 1. Avanzar en línea recta
    OnFwd(OUT_BC, 75);   // Ambos motores (B y C) adelante al 75%
    Wait(2000);          // Durante 2 segundos

    // 2. Girar a la derecha
    // Para girar, detenemos el motor interno del giro (C)
    // y mantenemos avanzando el motor externo (B)
    Off(OUT_C);
    OnFwd(OUT_B, 75);
    Wait(850);           // El tiempo de giro dependerá del roce del suelo

    // 3. Detener todo
    Off(OUT_BC);
}
```

## 4. Compilar y Ejecutar

1.  Asegúrate de que tu bloque NXT esté encendido y conectado al computador por USB.
2.  Guarda tu archivo de código (por ejemplo, con el nombre `primer_movimiento.nxc`).
3.  Presiona el botón **Download and Run** en la barra de herramientas de BricxCC (o presiona `Ctrl+F5`).

Si la sintaxis está correcta, el código se compilará, escucharás un tono de confirmación en el bloque NXT, y tu robot ejecutará su primera coreografía de movimiento en el suelo.