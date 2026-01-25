# NetLocker - Kill-Switch (Windows Desktop)

Este módulo proporciona una solución de aislamiento de red inmediata para estaciones de trabajo Windows. Está diseñado como un "botón de pánico" para cortar toda comunicación externa en caso de sospecha de malware o actividad inusual.

### Descripción
NetLocker Kill-Switch permite al usuario neutralizar cualquier intento de exfiltración de datos o comunicación con servidores C2 (Command & Control) mediante la reconfiguración instantánea del firewall del sistema.

### Funcionalidades Técnicas
- **Aislamiento Total:** Bloqueo de todas las conexiones entrantes y salientes mediante reglas de alta prioridad.
- **Interrupción de Procesos:** Diseñado para detener la actividad de red de aplicaciones en segundo plano.
- **Restauración Segura:** Función de desbloqueo protegida para recuperar la conectividad una vez que el host sea declarado seguro.
- **Interfaz Simplificada:** Ejecución directa mediante un archivo binario optimizado para rapidez de respuesta.

### Especificaciones de Ejecución
- **Tipo de archivo:** Ejecutable de Windows (.exe).
- **Arquitectura:** x86 / x64.
- **Requerimientos:** Privilegios de Administrador (necesarios para interactuar con el servicio de filtrado de red).
- **Compatibilidad:** Windows 10 y Windows 11.
- **archivo .sig:** nececita ir acompañado del archivo porque si no el porgrama no puede hacer el cheksum lo wue provocsria que se cerrara automáticamente por seguridad 

### Instrucciones de Seguridad
Este ejecutable debe ser almacenado en un lugar de fácil acceso (Escritorio o barra de tareas) para ser activado rápidamente durante un incidente. Se recomienda no modificar las reglas generadas manualmente para evitar conflictos de seguridad.

---
## Descargo de responsabilidad (Disclaimer)

Este software se proporciona exclusivamente para seguridad defensiva y respuesta ante incidentes. No se asume responsabilidad alguna por el uso indebido de esta herramienta, posibles daños a la infraestructura o pérdida accidental de conectividad derivada de su ejecución.

El uso de este programa en sistemas sin autorización expresa es ilegal. El usuario final es el único responsable de la implementación y las consecuencias de los protocolos de aislamiento de red.

