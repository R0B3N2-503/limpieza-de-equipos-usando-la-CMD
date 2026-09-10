# 🧹 Limpieza y Mantenimiento de Equipos vía CMD y PowerShell

![Windows](https://img.shields.io/badge/OS-Windows-blue?style=flat&logo=windows)
![License](https://img.shields.io/badge/License-MIT-green.svg)
![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)

Repositorio con métodos nativos para el mantenimiento, reparación y desinfección de sistemas operativos Windows utilizando la **Símbolo del sistema (CMD)**, **PowerShell** y herramientas integradas del sistema.

---

> ⚠️ **Advertencia de Seguridad**
>
> Ejecutar comandos con privilegios de **Administrador** otorga acceso directo a la configuración crítica del sistema operativo. Asegúrate de digitar exactamente las instrucciones presentadas en esta guía para evitar la modificación o eliminación accidental de archivos esenciales.

---

## 📋 Métodos de Mantenimiento

### 1. Restauración de Atributos de Archivos (CMD)
Ideal para restaurar la visibilidad y permisos de archivos ocultos o modificados por software malicioso en unidades externas o en el sistema.

* **Comando:**
  ```cmd
  attrib -s -h -r /s /d *.*
¿En qué ayuda este código?

-s: Quita el atributo de archivo de sistema.

-h: Desoculta archivos y carpetas invisibles.

-r: Elimina la protección de solo lectura para habilitar modificación.

/s: Aplica el comando a todos los archivos del directorio actual y sus subdirectorios.

/d: Procesa tanto archivos como carpetas.

*.*: Aplica la regla a cualquier nombre de archivo con cualquier extensión.

2. Comprobador de Archivos del Sistema (sfc) (CMD - Administrador)
Herramienta de diagnóstico que examina la integridad de los archivos protegidos de Windows.

Comando:

DOS
sfc /scannow
¿En qué ayuda este código?
Escanea todos los archivos del sistema y reemplaza automáticamente los elementos corruptos, dañados o faltantes utilizando una copia en caché recuperada desde la imagen de Windows.

Precaución:

Requiere abrir la consola como Ejecutar como Administrador.

No cierres la ventana ni apagues el equipo mientras el análisis esté en curso.

3. Análisis de Antivirus con Windows Defender (PowerShell - Administrador)
Permite ejecutar un análisis de seguridad directamente desde la línea de comandos de PowerShell.

Análisis Completo:

PowerShell
Start-MpScan -ScanType FullScan
Análisis Rápido:

PowerShell
Start-MpScan -ScanType QuickScan
¿En qué ayuda este código?
Inicia un escaneo en segundo plano utilizando el motor de protección de Microsoft Defender para rastrear y neutralizar amenzas activas.

Precaución:
Verifica ingresar correctamente los parámetros (-ScanType FullScan o -ScanType QuickScan), respetando mayúsculas y guiones para evitar errores de sintaxis en PowerShell.

4. Herramienta de Eliminación de Software Malintencionado (MRT)
Ejecutable gráfico integrado en Windows para la eliminación de malware específico.

Instrucciones:

Presiona la combinación de teclas Windows + R.

Escribe mrt y presiona Enter.

Acepta los permisos de administrador en la ventana desplegada.

Selecciona el tipo de análisis deseado (Análisis rápido, Análisis completo o Análisis personalizado).

¿En qué ayuda?
Realiza una búsqueda profunda de amenazas comunes y software malintencionado específico en segundo plano con interfaz gráfica intuitiva.

🔗 Recursos y Documentación Oficial
📄 Documentación del comando ATTRIB

🛠️ Cómo usar la herramienta SFC (System File Checker)

⚡ Módulo Defender en PowerShell (Start-MpScan)

🛡️ Información sobre la Herramienta de Eliminación de Software Malintencionado (MRT)

🤝 Contribuciones
Las contribuciones, correcciones o sugerencias de nuevos comandos útiles son bienvenidas. Siéntete libre de abrir un Issue o enviar un Pull Request.
