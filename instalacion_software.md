# Primeros Pasos: Instalación de Software en Windows 10

Para programar y comunicarnos con nuestro bloque LEGO Mindstorms NXT desde un equipo moderno con Windows 10, necesitamos instalar dos componentes fundamentales: el controlador de comunicación (Fantom Driver) y el entorno de desarrollo (Bricx Command Center).

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