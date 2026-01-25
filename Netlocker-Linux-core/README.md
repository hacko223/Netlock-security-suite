# NetLocker Linux Core - Especificaciones Técnicas v1.6.2

NetLocker es una solución de aislamiento de host de alto rendimiento diseñada para el kernel Linux. Utiliza el stack de **Netfilter** para interceptar y filtrar el tráfico en las capas 3 y 4 del modelo OSI, permitiendo una contención inmediata de amenazas.

---

## 1. Arquitectura del Sistema
NetLocker actúa directamente sobre las tablas de filtrado de paquetes del kernel mediante `iptables`, garantizando que ningún paquete sea procesado antes de cumplir con las políticas de seguridad establecidas.



---

## 2. Edición para Servidor (CLI Edition)
Diseñada para entornos *Headless* (servidores en la nube o racks) y administración remota. Prioriza la automatización y la seguridad crítica mediante la terminal.

* **Modo --panic:** Aislamiento total. Establece políticas `DROP` globales y limpia tablas de excepción. Corta la conexión SSH actual.
* **Modo --safe (SSH Survival):** Utiliza estados de conexión (`conntrack`) para mantener abierto el puerto 22 exclusivamente para la sesión actual, bloqueando todo lo demás.
* **Modo --restore:** Limpia las reglas de NetLocker y devuelve el servidor a su estado de conectividad normal.



---

## 3. Edición para Escritorio (Desktop Edition)
Enfocada en la protección del usuario final y la integridad física de estaciones de trabajo personales.

* **Interfaz Gráfica (GUI):** Panel intuitivo desarrollado en Tkinter para acciones inmediatas sin necesidad de comandos.
* **Protección de Hardware (USB 2FA):** Requiere la presencia física de un dispositivo USB con un Serial ID registrado para autorizar cambios en el firewall.
* **Módulo Sentinel:** Hilo de ejecución persistente que monitorea y restaura automáticamente el firewall si detecta una modificación externa maliciosa.



---

## 4. Comparativa Técnica

| Característica | Server Edition (CLI) | Desktop Edition (GUI) |
| :--- | :--- | :--- |
| **Interfaz de Usuario** | Terminal / Argumentos | Ventana Gráfica (Tkinter) |
| **Acceso Remoto** | Protegido (SSH Safe Mode) | No disponible (Local Only) |
| **Validación Física** | Master Password | Password + USB Hardware ID |
| **Distribución** | Script de Sistema (.py) | Binario / AppImage |
| **Nivel de Control** | Capa 3 y 4 (Netfilter) | Capa 3, 4 y 7 (Sentinel) |



---

## 5. Proceso de Despliegue (Hardening)
Para asegurar la integridad del núcleo, el archivo debe ser inaccesible para usuarios comunes. Ejecute los siguientes comandos:

# 1. Asignar propiedad al usuario Root
```sudo chown root:root netlocker.py```

# 2. Restringir permisos: Solo Root puede leer, escribir o ejecutar
```sudo chmod 700 netlocker.py```

# 3. Crear enlace simbólico para uso global
```sudo ln -s $(pwd)/netlocker.py /usr/local/bin/netlocker```

---

## 6. Registro de Logs y Auditoría
La versión Server Edition escribe automáticamente en `/var/log/netlocker.log`, registrando:
1. Intentos de acceso fallidos.
2. Cambio de estados de red (Panic/Safe/Restore).
3. Timestamps de actividad del administrador.

---

## 7. Descargo de Responsabilidad (Disclaimer)
Este software es una herramienta de seguridad defensiva. El autor no se hace responsable por la pérdida accidental de conectividad o daños derivados de una mala configuración. 

**ADVERTENCIA:** El uso del modo `--panic` en servidores remotos sin acceso físico o consola serie (KVM/IPMI) resultará en un bloqueo permanente de la gestión.

---
**Desarrollado por:** hacko223  
**Licencia:** MIT (2026)
