# Instalación de Software en Windows 7

Si utilizas un equipo con Windows 7, la instalación del entorno para programar tu bloque LEGO Mindstorms NXT es mucho más directa que en versiones posteriores del sistema operativo. Necesitaremos instalar el controlador de comunicación (Fantom Driver) y el entorno de desarrollo (Bricx Command Center).

## 1. Instalación del Fantom Driver

El Fantom Driver es el controlador oficial que permite que Windows reconozca el bloque NXT al conectarlo mediante el cable USB.

1. Descarga el archivo de instalación del Fantom Driver y extráelo en una carpeta de tu preferencia. [📥 Descargar Fantom Driver para Windows](./recursos/NXT-Fantom-Drivers-v120.zip)
2. Navega hasta esa carpeta y busca el archivo ejecutable de instalación (generalmente llamado `setup.exe` o similar).
3. Haz doble clic sobre el archivo para ejecutarlo.
4. Sigue las instrucciones del asistente de instalación en pantalla. A diferencia de Windows 10, Windows 7 suele permitir la instalación de este controlador sin mayores inconvenientes. Si aparece alguna advertencia de seguridad estándar de Windows preguntando si deseas ejecutar el archivo o instalar el software, haz clic en "Ejecutar" o "Instalar de todas formas".

## 2. Instalación de Bricx Command Center (BricxCC)

Una vez que el controlador está instalado, procedemos con el entorno de programación.

1. Descarga el instalador de BricxCC. [📥 Descargar Bricx Command Center](./recursos/bricxcc_setup_3389.exe)
2. Ejecútalo e instálalo dejando las opciones que vienen marcadas por defecto.
3. Al finalizar la instalación, **enciende tu bloque LEGO NXT** y conéctalo al computador utilizando el cable USB.
4. Abre el programa BricxCC. Al iniciar, te mostrará una pequeña ventana llamada "Find Brick" para configurar la conexión inicial:
   * En **Port**, selecciona **USB**.
   * En **Brick Type**, selecciona **NXT**.
   * En **Firmware**, selecciona **Standard**.
5. Haz clic en **OK**. Si la ventana principal de BricxCC se abre sin mostrar ningún error de conexión, significa que el software se está comunicando correctamente con tu bloque NXT.

## 3. Primera prueba de funcionamiento: Mover un motor

Para confirmar que todo está listo para empezar a trabajar, probaremos un programa básico. Conecta un motor al **Puerto B** del bloque NXT.

1. En BricxCC, ve al menú superior y selecciona *File > New* para abrir un nuevo documento en blanco.
2. Copia y pega el siguiente código en NXC:

```c
task main()
{
    OnFwd(OUT_B, 75); // Enciende el motor del puerto B al 75% de potencia
    Wait(2000);       // Mantiene la acción durante 2 segundos (2000 ms)
    Off(OUT_B);       // Apaga el motor
}
```

3. Guarda tu archivo (puedes llamarlo `prueba_motor`).
4. Presiona el botón **Download and Run** en la barra de herramientas (o utiliza el atajo de teclado `Ctrl+F5`).
5. El código se enviará a tu bloque NXT y verás cómo el motor conectado al puerto B gira durante dos segundos. ¡La instalación ha sido un éxito!





# Instalación de Software en Windows 10

Para programar y comunicarnos con nuestro bloque LEGO Mindstorms NXT desde un equipo moderno con Windows 10, necesitamos instalar dos componentes fundamentales: el controlador de comunicación (Fantom Driver) [📥 Descargar Fantom Driver para Windows](./recursos/NXT-Fantom-Drivers-v120.zip) y el entorno de desarrollo (Bricx Command Center).

## 1. Instalación del Fantom Driver

El Fantom Driver es el controlador oficial que permite que el sistema operativo reconozca el bloque NXT al conectarlo mediante el cable USB. Como es un software antiguo, Windows 10 bloqueará su instalación por no tener una firma digital reciente. 

Para instalarlo exitosamente, debemos dividir el proceso en dos partes: primero, deshabilitar la firma de controladores y, segundo, instalarlo como administrador.

### Parte A: Deshabilitar el uso obligatorio de controladores firmados
1. Haz clic en el menú **Inicio** de Windows y selecciona el ícono del engranaje para abrir **Configuración**.
2. Ve a **Actualización y seguridad** y luego selecciona **Recuperación** en el menú lateral izquierdo.
3. En la sección *Inicio avanzado*, haz clic en el botón **Reiniciar ahora**. Tu computador se reiniciará en una pantalla azul con varias opciones.
4. Selecciona **Solucionar problemas** > **Opciones avanzadas** > **Configuración de inicio**.
5. Haz clic en el botón **Reiniciar**.
6. Al volver a encender, verás una lista de opciones. Presiona la tecla **7** o **F7** en tu teclado para seleccionar **Deshabilitar el uso obligatorio de controladores firmados**. Windows iniciará normalmente.

### Parte B: Instalación desde la consola
Incluso con el paso anterior, Windows puede mostrar una pantalla azul indicando "Windows protegió su PC" al intentar abrir el instalador. Para evitarlo:

1. Ve al menú Inicio de Windows, escribe `cmd`.
2. Haz clic derecho sobre la aplicación **Símbolo del sistema** y selecciona **Ejecutar como administrador**.
3. En la consola, utiliza el comando `cd` para navegar hasta la carpeta donde extrajiste los archivos del instalador del Fantom Driver. Por ejemplo:
   ```cmd
   cd C:\Ruta\A\Tu\Carpeta\Descargas\FantomDriver
   ```
4. Escribe el nombre del archivo ejecutable (por ejemplo, `setup.exe` o el instalador `.msi` correspondiente) y presiona **Enter**.
5. Ahora el asistente de instalación se abrirá sin bloqueos. Sigue las instrucciones en pantalla para finalizar el proceso. En un momento te pedirá confirmación para instalar un controlador no firmado; acéptalo.

## 2. Instalación de Bricx Command Center (BricxCC)

BricxCC es el entorno de programación donde escribiremos el código (usaremos el lenguaje NXC - *Not eXactly C*) para darle instrucciones a nuestro robot.

1. Descarga el instalador de BricxCC.
2. Ejecútalo e instálalo con las opciones por defecto.
3. Una vez instalado, **enciende tu bloque LEGO NXT** y conéctalo al computador mediante USB.
4. Abre BricxCC. Se abrirá una pequeña ventana emergente llamada "Find Brick" para establecer la conexión:
   * En **Port**, selecciona **USB**.
   * En **Brick Type**, selecciona **NXT**.
   * En **Firmware**, selecciona **Standard**.
5. Haz clic en **OK**. BricxCC debería abrirse correctamente, confirmando que la comunicación entre el PC y el bloque es exitosa.

## 3. Primera prueba de funcionamiento: Mover un motor

Para confirmar que toda la instalación fue exitosa, haremos que el bloque ejecute un código muy simple. Conecta un motor al **Puerto B** del bloque NXT.

1. En BricxCC, ve a *File > New* para abrir un archivo en blanco.
2. Escribe el siguiente código:

```c
task main()
{
    OnFwd(OUT_B, 75); // Enciende el motor del puerto B al 75% de potencia
    Wait(2000);       // Mantiene la acción durante 2 segundos (2000 ms)
    Off(OUT_B);       // Apaga el motor
}
```

3. Guarda el archivo.
4. Presiona el botón **Download and Run** en la barra de herramientas (o presiona `Ctrl+F5`).
5. El código se compilará, se transferirá al bloque y el motor B girará durante dos segundos. ¡Tu entorno está listo para programar!





# Instalación de Software en Windows 11

Para programar y comunicarnos con nuestro bloque LEGO Mindstorms NXT, necesitamos instalar el controlador de comunicación (**Fantom Driver**) y el entorno de desarrollo (**Bricx Command Center** o BricxCC).

El proceso varía dependiendo de tu sistema operativo, ya que el Fantom Driver es un controlador antiguo y las versiones más recientes de Windows bloquean su instalación por defecto. Busca tu versión a continuación:

---

## Instalación en Windows 10 y Windows 11

Ambos sistemas operativos tienen políticas de seguridad estrictas que bloquean los controladores no firmados digitalmente. Para instalar el Fantom Driver, debemos dividir el proceso en dos partes: deshabilitar la firma de controladores y luego instalar desde la consola.

### Parte A: Deshabilitar el uso obligatorio de controladores firmados

**En Windows 10:**
1. Ve a **Configuración** > **Actualización y seguridad** > **Recuperación**.
2. En *Inicio avanzado*, haz clic en **Reiniciar ahora**.
3. Selecciona **Solucionar problemas** > **Opciones avanzadas** > **Configuración de inicio** y haz clic en **Reiniciar**.
4. Al reiniciar, presiona **7** o **F7** para seleccionar **Deshabilitar el uso obligatorio de controladores firmados**.

**En Windows 11:**
1. Ve a **Configuración** > **Sistema** > **Recuperación**.
2. En *Inicio avanzado*, haz clic en **Reiniciar ahora**.
3. Sigue la misma ruta: **Solucionar problemas** > **Opciones avanzadas** > **Configuración de inicio** > **Reiniciar**.
4. Presiona **7** o **F7** en la pantalla de opciones.

### Parte B: Instalación desde la consola (Para evitar el bloqueo SmartScreen)

Incluso tras el reinicio, Windows puede mostrar el mensaje "Windows protegió su PC". Para evitarlo:

1. Abre el menú Inicio, escribe `cmd`, haz clic derecho en **Símbolo del sistema** (o Terminal en W11) y selecciona **Ejecutar como administrador**.
2. Usa el comando `cd` para ir a la carpeta del instalador. Ejemplo:
   ```cmd
   cd C:\Ruta\A\Tu\Carpeta\Descargas\FantomDriver
   ```
3. Escribe el nombre del ejecutable (ej. `setup.exe`) y presiona **Enter**.
4. Sigue las instrucciones y acepta cuando Windows pregunte si deseas instalar el controlador no firmado.

---

## Instalación en Windows 7

En Windows 7 el proceso es directo y no requiere reiniciar el equipo.

1. Descarga y extrae el archivo de instalación del **Fantom Driver**.
2. Haz doble clic en el archivo ejecutable (`setup.exe`).
3. Sigue las instrucciones del asistente. Si aparece una advertencia de seguridad, haz clic en "Ejecutar" o "Instalar de todas formas".

---

## Instalación de Bricx Command Center (Todos los Windows)

Una vez instalado el Fantom Driver, el proceso para el entorno de programación es el mismo para cualquier versión de Windows:

1. Descarga el instalador de **BricxCC**.
2. Ejecútalo e instálalo con las opciones por defecto.
3. **Enciende tu bloque LEGO NXT** y conéctalo al PC mediante el cable USB.
4. Abre BricxCC. En la ventana "Find Brick":
   * **Port**: selecciona **USB**.
   * **Brick Type**: selecciona **NXT**.
   * **Firmware**: selecciona **Standard**.
5. Haz clic en **OK**. BricxCC debería abrirse correctamente.

---

## Primera prueba: Mover un motor

Para confirmar que todo funciona, conecta un motor al **Puerto B** del bloque NXT.

1. En BricxCC, ve a *File > New*.
2. Escribe el siguiente código en NXC:

```c
task main()
{
    OnFwd(OUT_B, 75); // Enciende el motor del puerto B al 75% de potencia
    Wait(2000);       // Mantiene la acción durante 2 segundos (2000 ms)
    Off(OUT_B);       // Apaga el motor
}
```

3. Guarda el archivo.
4. Presiona **Download and Run** (o `Ctrl+F5`). El código se transferirá y el motor B girará durante dos segundos. ¡Tu entorno está listo!