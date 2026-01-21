# NetLock - Host Isolation (Windows Server Edition)

Módulo especializado en el aislamiento de servidores y estaciones de trabajo. Este componente está diseñado para entornos que requieren mantener un canal de gestión seguro mientras se restringe el tráfico de red restante.

### Descripción
Este módulo implementa políticas de seguridad basadas en el modelo de Confianza Cero (Zero Trust). Su función principal es la respuesta ante incidentes de Ransomware y la mitigación de ataques de Movimiento Lateral dentro de infraestructuras empresariales.

### Funcionalidades Técnicas
- **Management Bypass:** Permite definir direcciones IP o subredes de administración para mantener el acceso remoto (RDP/SSH).
- **Stateful Blocking:** Bloqueo dinámico de puertos mediante reglas de firewall persistentes.
- **Resistencia a Reinicios:** Configuración de reglas que permanecen activas tras un reinicio del sistema.
- **Registro de Auditoría:** Almacenamiento de logs de actividad para análisis forense posterior.

### Especificaciones
- **Controlador:** PowerShell Core / Windows Command Line.
- **Interfaz de Red:** Windows Filtering Platform (WFP).
- **Modo de Operación:** Restrictivo (Deny All).

### Configuración
Se recomienda la configuración previa de variables de entorno para la gestión de IPs de administración, evitando así la pérdida de conectividad del operador durante el despliegue del protocolo de aislamiento.

## Descargo de responsabilidad

Este software se proporciona con fines de seguridad defensiva. No se asume responsabilidad alguna por el uso indebido de esta herramienta, posibles daños a la infraestructura o pérdida accidental de conectividad.

El uso de este programa en sistemas sin autorización expresa es ilegal. El usuario final es el único responsable de la ejecución y las consecuencias de los módulos de aislamiento de red.


---
Este software debe ser utilizado exclusivamente por personal autorizado en administración de sistemas y respuesta ante incidentes.

