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
