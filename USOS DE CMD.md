# 🧹 Limpieza de Equipos Usando la CMD

<p align="center">
  <a href="https://learn.microsoft.com/es-es/windows-server/administration/windows-commands/windows-commands">
    <img src="https://img.shields.io/badge/Console-Windows%20CMD-0078D6?style=for-the-badge&logo=windows&logoColor=white" alt="Windows CMD" />
  </a>
  <a href="https://learn.microsoft.com/es-es/powershell/scripting/overview">
    <img src="https://img.shields.io/badge/PowerShell-Security-5391FE?style=for-the-badge&logo=powershell&logoColor=white" alt="PowerShell" />
  </a>
  <a href="https://support.microsoft.com/es-es/windows/protecci%C3%B3n-contra-virus-y-amenazas-en-seguridad-de-windows-22b02cdb-f2f0-1059-fcb6-22b38810634e">
    <img src="https://img.shields.io/badge/Microsoft-Defender%20%26%20MRT-00A4EF?style=for-the-badge&logo=microsoft&logoColor=white" alt="Microsoft Security" />
  </a>
</p>

Guía interactiva, completa y profesional para desinfectar, diagnosticar y reparar sistemas operativos Windows utilizando exclusivamente herramientas nativas de consola (`CMD`, `PowerShell`) y utilidades integradas del sistema.

---

## 📋 Tabla de Contenidos

- [🛡️ Fundamentos: Virus y Clasificación de Malware](#️-fundamentos-virus-y-clasificación-de-malware)
- [🧹 Método 1: Desocultar Archivos y Limpieza USB (`attrib`)](#-método-1-desocultar-archivos-y-limpieza-usb-attrib)
- [🛠️ Método 2: Reparación de Archivos del Sistema (`sfc /scannow`)](#️-método-2-reparación-de-archivos-del-sistema-sfc-scannow)
- [⚡ Método 3: Escaneo Antivirus en PowerShell (`Start-MpScan`)](#-método-3-escaneo-antivirus-en-powershell-start-mpscan)
- [⚙️ Método 4: Herramienta de Eliminación de Software Malintencionado (`MRT`)](#️-método-4-herramienta-de-eliminación-de-software-malintencionado-mrt)
- [🔗 Enlaces y Fuentes Oficiales](#-enlaces-y-fuentes-oficiales)
- [🤝 Contribuciones](#-contribuciones)

---

## 🛡️ Fundamentos: Virus y Clasificación de Malware

Un **virus informático** es un programa diseñado para insertarse en ejecitables o áreas del sistema sin autorización del usuario.

### Categorías Generales de Virus
* **Residentes en Memoria:** Permanecen en la RAM tras cerrar la aplicación infectada.
* **Sector de Arranque (MBR):** Modifican el inicio del disco duro para ejecutarse antes que el sistema operativo.
* **Virus de Macro:** Infectan plantillas y documentos ofimáticos (Microsoft Office).
* **Polimórficos:** Mutan su código para evitar la detección por firmas del antivirus.

### Nivel de Impacto / Daño Bajo
Un **malware de impacto bajo** no busca borrar archivos ni robar contraseñas, sino alterar parámetros menores del navegador, redireccionar búsquedas o desplegar anuncios (*Adware* / *Hijacker*).

---

## 📁 Método 1: Desocultar Archivos y Limpieza USB (`attrib`)

Ciertos tipos de malware (especialmente los propagados por unidades USB) no eliminan la información del usuario, sino que ocultan las carpetas reales y generan accesos directos maliciosos con los mismos nombres para infectar otros sistemas.

### 💻 Instrucciones
1. Abre la consola **CMD** (Símbolo del sistema).
2. Cambia a la letra de la unidad afectada (ejemplo: `E:`).
3. Ejecuta la siguiente instrucción:

```cmd
cd /d E:
attrib -s -h -r /s /d *.*
