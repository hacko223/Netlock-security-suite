# NetLocker - Host Isolation (Windows Server Edition)

Módulo especializado en el aislamiento de Módulo especializado en el aislamiento de servidores y estaciones de trabajo. Este componente está diseñado para entornos que requieren mantener un canal de gestión seguro mientras se restringe el tráfico de red restante.

### Descripción
Este módulo implementa políticas de seguridad basadas en el modelo de Confianza Cero (Zero Trust). Su función principal es la respuesta ante incidentes de Ransomware y la mitigación de ataques de Movimiento Lateral dentro de infraestructuras empresariales.

### Funcionalidades Técnicas
- **Management Bypass:** Permite definir direcciones IP o subredes de administración para mantener el acceso remoto (RDP/SSH).
- **Watchdog Centinela:** Hilo persistente que monitorea el firewall cada 20 segundos para revertir cambios no autorizados.
- **Stateful Blocking:** Bloqueo dinámico de puertos mediante reglas de firewall persistentes.
- **Resistencia a Reinicios:** Configuración de persistencia mediante el Registro de Windows (HKCU) para inicio automático.
- **Hardware Whitelisting (WMI):** Registro de dispositivos USB autorizados mediante la captura de su Serial ID único a través de consultas profundas de hardware.
- **Registro de Auditoría:** Almacenamiento de logs de actividad para análisis forense posterior.
- **Contraseña con cifrado:** NetLocker requiere una contraseña maestra cifrada con **SHA-512** para validar cada acción crítica.
- **Checksum Dinámico:** Sistema de verificación de integridad basado en **SHA-512** para asegurar que los archivos críticos y la base de datos no hayan sido manipulados

### Cómo verificar la integridad manualmente
Si deseas verificar que tu ejecutable no ha sido alterado, puedes generar el hash del archivo `.exe` con PowerShell:
```powershell
Get-FileHash .\NetLocker-Server.exe -Algorithm SHA512
```

### Especificaciones
- **Controlador:** PowerShell Core / Windows Command Line.
- **Interfaz de Red:** Windows Filtering Platform (WFP).
- **Modo de Operación:** Restrictivo (Deny All).

### Configuración
Se recomienda la configuración previa de variables de entorno para la gestión de IPs de administración, evitando así la pérdida de conectividad del operador ñ el despliegue del protocolo de aislamiento.

## Descargo de responsabilidad

Este software se proporciona con fines de seguridad defensiva. No se asume responsabilidad alguna por el uso indebido de esta herramienta, posibles daños a la infraestructura o pérdida accidental de conectividad.

El uso de este programa en sistemas sin autorización expresa es ilegal. El usuario final es el único responsable de la ejecución y las consecuencias de los módulos de aislamiento de red.


---
Este software debe ser utilizado exclusivamente por personal autorizado en administración de sistemas y respuesta ante incidentes.

