🛠️ Limpieza y Mantenimiento de Equipos usando la CMD y PowerShell

Una guía práctica, rápida y estructurada con comandos esenciales de Símbolo del sistema (CMD), PowerShell y herramientas nativas de Windows para realizar tareas de desinfección de archivos, reparación del sistema y análisis de malware sin necesidad de instalar software de terceros.

📌 Tabla de Contenidos

Método 1: Mostrar Archivos Ocultos y Desinfectar Atributos (attrib)

Método 2: Reparación de Archivos del Sistema (sfc /scannow)

Método 3: Análisis de Antivirus desde PowerShell (Start-MpScan)

Método 4: Herramienta de Eliminación de Software Malintencionado (mrt)

⚠️ Advertencia de Seguridad

🔗 Enlaces y Fuentes Oficiales

📂 Método 1: Mostrar Archivos Ocultos y Desinfectar Atributos (attrib)

Muchos tipos de malware (especialmente en memorias USB) no eliminan tus archivos, sino que los ocultan cambiando sus atributos del sistema para hacerte creer que se borraron.

💻 Comando:

attrib -s -h -r /s /d *.*


🔍 ¿En qué ayuda este código?

Este comando remueve las restricciones de visibilidad e ingeniería del sistema que el malware haya aplicado a tus archivos en el directorio donde te encuentres situado.

Desglose de parámetros:

Parámetro

Función

-s

Quita el atributo de Archivo de Sistema (System).

-h

Quita el atributo de Archivo Oculto (Hidden).

-r

Quita el atributo de Solo Lectura (Read-only).

/s

Aplica el comando recursivamente a todos los archivos del directorio actual y subcarpetas.

/d

Aplica el proceso también a las carpetas y directorios.

*.*

Representa la combinación de todos los nombres de archivo y todas las extensiones.

🛠️ Método 2: Reparación de Archivos del Sistema (sfc /scannow)

Si tu sistema presenta errores, lentitud repentina o fallos en aplicaciones de Windows, es posible que haya archivos dañados o corruptos por el uso continuo o apagados repentinos.

📋 Pasos para ejecutar:

Haz clic en el menú Inicio de Windows y busca Símbolo del sistema (o cmd).

Haz clic derecho y selecciona Ejecutar como administrador.

Escribe el siguiente comando y presiona Enter:

sfc /scannow


🔍 ¿En qué ayuda este código?

SFC (System File Checker) examina la integridad de todos los archivos protegidos del sistema operativo. Si detecta archivos corruptos, dañados o modificados, los reemplaza automáticamente con una copia en caché limpia almacenada en el propio sistema.

🛡️ Método 3: Análisis de Antivirus desde PowerShell (Start-MpScan)

Puedes ejecutar un análisis nativo de Microsoft Defender directamente desde la consola de PowerShell sin necesidad de abrir la interfaz gráfica.

📋 Pasos para ejecutar:

Presiona Win + X y selecciona Windows PowerShell (Administrador) o Terminal (Administrador).

Ingresa uno de los siguientes comandos según el tipo de análisis deseado:

⚡ Análisis Rápido (QuickScan):

Start-MpScan -ScanType QuickScan


🔍 Análisis Completo (FullScan):

Start-MpScan -ScanType FullScan


🔍 ¿En qué ayuda este código?

Inicia un escaneo activo de amenazas a nivel de código mediante el motor nativo de Microsoft Defender. El análisis completo rastrea el registro, la memoria RAM y todas las unidades del dispositivo en busca de malware avanzado.

🧹 Método 4: Herramienta de Eliminación de Software Malintencionado (mrt)

Windows incluye una herramienta independiente integrada dedicada a detectar y eliminar amenazas específicas de forma guiada.

📋 Pasos para ejecutar:

Presiona la combinación de teclas Windows + R para abrir la ventana de diálogo Ejecutar.

Digita exactamente el comando:

mrt


Presiona Enter o haz clic en Aceptar.

En la ventana emergente, concede los permisos de administrador y selecciona el tipo de análisis de tu agrado:

Análisis rápido: Examina áreas del sistema vulnerables a software malintencionado.

Análisis completo: Examina todo el sistema (puede demorar varias horas).

Análisis personalizado: Examina carpetas específicas seleccionadas por el usuario.

⚠️ Advertencia de Seguridad

[!WARNING]
Extrema precaución al ejecutar la consola en modo Administrador:

Al ingresar a CMD o PowerShell con privilegios de administrador, otorgas al comando control directo sobre los archivos críticos del sistema operativo.

Revisa minuciosamente la sintaxis de cada comando antes de presionar Enter. Un espacio mal colocado o un carácter erróneo podría modificar o eliminar archivos no deseados.

Evita ejecutar comandos desconocidos provenientes de fuentes no verificadas en la web sin antes conocer exactamente su función.

🔗 Enlaces y Fuentes Oficiales

Para profundizar más sobre cada una de estas herramientas y sus parámetros adicionales, consulta la documentación oficial de Microsoft:

📄 Documentación oficial del comando attrib

📄 Documentación de la herramienta System File Checker (sfc)

📄 Módulo de PowerShell para Microsoft Defender (Start-MpScan)

📄 Información sobre la herramienta MRT (KB890830)
