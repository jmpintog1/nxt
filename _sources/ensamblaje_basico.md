# La Base Motriz

Antes de construir robots complejos como brazos mecánicos o clasificadores de color, necesitamos dominar la estructura más fundamental en la robótica móvil: **La Base Motriz** (o *Driving Base*).

Esta estructura simple de dos ruedas y un punto de apoyo libre nos permitirá probar el movimiento básico (avanzar, retroceder y girar) y servirá como chasis para añadir sensores más adelante.

## 1. Conceptos de Diseño de la Base Motriz

El diseño de esta base se sustenta en tres principios clave para la estabilidad y el control:

1.  **Centro de Gravedad Bajo:** El bloque inteligente NXT, que es la pieza más pesada (especialmente si usa pilas AA), debe ir montado lo más bajo posible o bien centrado sobre el eje de las ruedas principales para evitar que el robot vuelque al frenar de golpe.
2.  **Tracción Independiente (Drive Diferencial):** Usaremos dos motores independientes, uno para la rueda izquierda y otro para la derecha. Esto nos permite girar sobre el propio eje del robot (haciendo que una rueda avance y la otra retroceda simultáneamente).
3.  **El Tercer Punto de Apoyo:** Como solo tenemos dos ruedas motrices, necesitamos un tercer punto para que el robot no arrastre la parte trasera. Usaremos una "rueda loca" (una rueda pequeña pivotante) o una pieza de plástico lisa que deslice sobre el suelo.

## 2. Preparando los Componentes Principales

Para esta construcción inicial, separa las siguientes piezas de tu kit:

* **[ ] 1x Bloque Inteligente NXT**
* **[ ] 2x Servomotores Interactivos**
* **[ ] 2x Ruedas grandes con sus neumáticos**
* **[ ] 1x Rueda pequeña o pieza de apoyo deslizante**
* **[ ] 2x Cables de conexión NXT cortos o medianos**
* **[ ] Vigas (Beams) largas (de 11 o 15 hoyos) y pines de conexión (negros y azules)**

## 3. Pasos de Ensamblaje (Estructura Sugerida)

*(Nota para el autor: En esta sección de tu libro final, lo ideal es incluir imágenes o diagramas generados en software como Studio 2.0. Por ahora, describiremos la lógica del armado paso a paso).*

### Paso 1: Unir los Motores
Comienza uniendo los dos servomotores espalda con espalda. Utiliza pines negros (con fricción) y un par de vigas cortas para asegurarlos firmemente. Las cabezas naranjas giratorias de los motores deben quedar apuntando hacia afuera, en direcciones opuestas.

### Paso 2: Montar el Bloque NXT
Coloca el bloque NXT sobre los motores unidos. Utiliza vigas en forma de "L" (Liftarms angulados) y pines para anclar la base del bloque a la estructura de los motores. Asegúrate de que los puertos de letras (A, B, C) queden accesibles para conectar los motores, y los puertos numéricos (1, 2, 3, 4) queden libres para los futuros sensores.

### Paso 3: Colocar las Ruedas Principales
Inserta un eje en cruz corto en el centro de cada cabeza naranja del motor y luego coloca las ruedas grandes. Asegúralas con un tope pequeño (bush) si el eje es muy largo, para que las ruedas no se salgan al girar.

### Paso 4: El Apoyo Trasero
En la parte posterior de la estructura de los motores, añade una extensión usando vigas largas. Al final de esta extensión, monta la rueda pequeña pivotante o la pieza deslizante de plástico. Asegúrate de que, al apoyar el robot en el suelo, quede nivelado horizontalmente.

### Paso 5: Cableado
1.  Toma un cable NXT y conecta el **Motor Izquierdo** al **Puerto B** del bloque.
2.  Toma el segundo cable y conecta el **Motor Derecho** al **Puerto C**.

*Nota: Es una convención en la comunidad NXT usar los puertos B y C para la tracción principal, dejando el puerto A libre para un motor auxiliar (como una garra o un brazo).*

---

## 4. Comprobación Física

Antes de encenderlo, haz esta prueba rápida:
1.  Levanta el robot del suelo.
2.  Gira suavemente con la mano la rueda izquierda. Deberías sentir la resistencia del motor.
3.  Gira la rueda derecha.
4.  Revisa que ningún cable esté rozando contra las ruedas o el suelo.

¡Felicidades! Tienes tu Base Motriz lista. En el siguiente capítulo, escribiremos nuestro primer programa en BricxCC para hacer que este vehículo cobre vida.