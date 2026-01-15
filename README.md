# Wazuh SIEM – Laboratorio de Detección de Eventos

## Descripción

Este laboratorio consiste en la implementación de un SIEM utilizando Wazuh para la detección y análisis de eventos de seguridad en un sistema Linux mediante un agente monitoreado.

El objetivo es validar la recolección de logs, la detección de eventos relevantes y su visualización desde el dashboard.

---

## Arquitectura

- Wazuh Server
  - Wazuh Manager
  - Wazuh Indexer
  - Wazuh Dashboard
- Agente Linux (VM monitoreada)

### Comunicación
- Agente → Manager: 1514/udp  
- Registro de agentes: 1515/tcp  
- Dashboard: 443/tcp  

---

## Tecnologías utilizadas

- Wazuh 4.7.5
- Linux (Ubuntu)
- VirtualBox
- Networking local (Host-only)
- Conceptos de SIEM / Blue Team

---

## Implementación

1. Despliegue del Wazuh Server (manager, indexer y dashboard)
2. Instalación del Wazuh Agent en una máquina Linux externa
3. Registro del agente en el manager
4. Verificación del estado del agente desde el dashboard
5. Generación de eventos de seguridad en el sistema monitoreado
6. Análisis de alertas detectadas por el SIEM

---

## Eventos y alertas analizadas

### First time user executed sudo
- Nivel: Medio/Alto
- Descripción: Detección del primer uso de sudo por parte de un usuario.
- Relevancia: Indica una posible escalada de privilegios o cambio de comportamiento del usuario.

### User changed password
- Nivel: Medio
- Descripción: Detección de modificación de credenciales de usuario.
- Relevancia: Puede indicar manipulación de cuentas o intento de persistencia.

### New group added to the system
- Nivel: Alto
- Descripción: Creación de un nuevo grupo en el sistema.
- Relevancia: La creación de grupos puede otorgar permisos adicionales o facilitar accesos no autorizados.

---

## Resultados

- El agente se conectó correctamente al Wazuh Server.
- Se recolectaron logs en tiempo real desde el sistema monitoreado.
- El SIEM detectó eventos relacionados con escalada de privilegios y gestión de cuentas.
- Las alertas fueron visualizadas y analizadas desde el dashboard.

---

## Evidencias

Las evidencias del laboratorio se encuentran en el directorio correspondiente del repositorio e incluyen:

- Captura del agente en estado Active.
- Capturas de alertas visualizadas en el dashboard.
- Detalle de eventos (Rule ID, nivel y descripción).

---

## Aprendizajes

- Arquitectura y funcionamiento de un SIEM.
- Instalación y gestión de agentes Wazuh.
- Análisis de eventos de seguridad en sistemas Linux.
- Detección de escalada de privilegios y cambios en cuentas.
- Resolución de problemas reales de servicios y permisos en Linux.
