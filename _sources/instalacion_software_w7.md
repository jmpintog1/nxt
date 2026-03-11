# Instalación de Software en Windows 7

Si utilizas un equipo con Windows 7, la instalación del entorno para programar tu bloque LEGO Mindstorms NXT es mucho más directa que en versiones posteriores del sistema operativo. Necesitaremos instalar el controlador de comunicación (Fantom Driver) y el entorno de desarrollo (Bricx Command Center).

## 1. Instalación del Fantom Driver

El Fantom Driver es el controlador oficial que permite que Windows reconozca el bloque NXT al conectarlo mediante el cable USB.

1. Descarga el archivo de instalación del Fantom Driver y extráelo en una carpeta de tu preferencia.
2. Navega hasta esa carpeta y busca el archivo ejecutable de instalación (generalmente llamado `setup.exe` o similar).
3. Haz doble clic sobre el archivo para ejecutarlo.
4. Sigue las instrucciones del asistente de instalación en pantalla. A diferencia de Windows 10, Windows 7 suele permitir la instalación de este controlador sin mayores inconvenientes. Si aparece alguna advertencia de seguridad estándar de Windows preguntando si deseas ejecutar el archivo o instalar el software, haz clic en "Ejecutar" o "Instalar de todas formas".

## 2. Instalación de Bricx Command Center (BricxCC)

Una vez que el controlador está instalado, procedemos con el entorno de programación.

1. Descarga el instalador de BricxCC.
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