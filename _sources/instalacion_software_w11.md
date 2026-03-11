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