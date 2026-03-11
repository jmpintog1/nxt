# Primeros Pasos: Instalación de Software en Windows 10

Para programar y comunicarnos con nuestro bloque LEGO Mindstorms NXT desde un equipo moderno con Windows 10, necesitamos instalar dos componentes fundamentales: el controlador de comunicación (Fantom Driver) y el entorno de desarrollo (Bricx Command Center).

## 1. Instalación del Fantom Driver

El Fantom Driver es el controlador oficial que permite que el sistema operativo reconozca el bloque NXT al conectarlo mediante el cable USB.

**Solución al bloqueo de Windows 10:**
Al intentar ejecutar el instalador del Fantom Driver, es muy común que el sistema operativo lo detenga mostrando una pantalla azul con el mensaje "Windows protegió su PC". Para evitar este bloqueo y realizar la instalación, debemos usar la consola de comandos con privilegios elevados:

1. Ve al menú Inicio de Windows, escribe `cmd`.
2. Haz clic derecho sobre la aplicación **Símbolo del sistema** y selecciona **Ejecutar como administrador**.
3. En la consola, utiliza el comando `cd` para navegar hasta la carpeta donde extrajiste los archivos del instalador del Fantom Driver. Por ejemplo:
   ```cmd
   cd C:\Ruta\A\Tu\Carpeta\Descargas\FantomDriver
   ```
4. Escribe el nombre del archivo ejecutable (por ejemplo, `setup.exe` o el instalador `.msi` correspondiente) y presiona **Enter**.
5. Ahora el asistente de instalación se abrirá sin bloqueos. Sigue las instrucciones en pantalla para finalizar el proceso.

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