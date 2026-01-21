# NetLock - Linux Core (Netfilter Security)

Este módulo proporciona una interfaz de control para el aislamiento de red en sistemas basados en el kernel Linux. Se distribuye como un binario ejecutable autónomo que no requiere dependencias externas para su funcionamiento.

### Descripción
NetLock Linux Core está diseñado para ser una herramienta versátil tanto en entornos de escritorio como en servidores. Su objetivo es la implementación inmediata de políticas de "Denegación Total" (Default Drop) para contener incidentes de seguridad y prevenir la exfiltración de datos.

### Funcionalidades Técnicas
- **Gestión de Cadenas (Chains):** Control estricto sobre las cadenas de INPUT, OUTPUT y FORWARD mediante el stack de Netfilter.
- **Modo Dual (Desktop/Server):** Configuración adaptable para proteger la privacidad del usuario o la integridad de la infraestructura.
- **SSH/Management Protection:** Reglas automáticas para prevenir el bloqueo accidental de sesiones de administración remota.
- **Binary Portability:** Ejecutable compilado para funcionar en las principales distribuciones (Ubuntu, Debian, CentOS, RHEL).

### Especificaciones de Ejecución
- **Tipo de archivo:** Binario ejecutable (ELF).
- **Requerimientos:** Privilegios de superusuario (root/sudo) para la manipulación del stack de red.
- **Capa de Red:** Capa 3 (Red) y Capa 4 (Transporte) del modelo OSI.

### Instrucciones de Seguridad
Dada la naturaleza crítica de la manipulación de las tablas de enrutamiento y filtrado del kernel, se recomienda contar con un acceso físico o consola serie al sistema antes de aplicar políticas restrictivas en servidores remotos.

---
## Descargo de responsabilidad (Disclaimer)

Este software se proporciona con de seguridad defensiva. No se asume responsabilidad alguna por el uso indebido de esta herramienta, posibles daños a la infraestructura o pérdida accidental de conectividad.

El uso de este programa en sistemas sin autorización expresa es ilegal. El usuario final es el único responsable de la ejecución y las consecuencias de los módulos de aislamiento de red.

---
Este software debe ser utilizado exclusivamente por personal autorizado en administración de sistemas y respuesta ante incidentes.
