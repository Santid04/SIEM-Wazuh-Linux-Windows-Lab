# Wazuh SIEM – Laboratorio de Detección de Eventos

## Descripción

Este laboratorio consiste en la implementación de un SIEM utilizando Wazuh para la detección y análisis de eventos de seguridad en sistemas Linux y Windows mediante agentes monitoreados.

El objetivo es validar la recolección de logs, la detección de eventos relevantes y su visualización centralizada desde el dashboard.

---

## Arquitectura

- Wazuh Server
  - Wazuh Manager
  - Wazuh Indexer
  - Wazuh Dashboard
- Agente Linux (VM Ubuntu Server)
- Agente Windows (host Windows)

---

## Tecnologías utilizadas

- Wazuh 4.7.5
- Linux (Ubuntu Server)
- Windows
- VirtualBox
- Networking local (Host-only)
- Conceptos de SIEM / Blue Team

---

## Implementación

1. Despliegue del Wazuh Server (manager, indexer y dashboard).
2. Instalación y configuración del Wazuh Agent en una máquina Linux.
3. Instalación y configuración del Wazuh Agent en un sistema Windows.
4. Registro y verificación del estado de ambos agentes desde el dashboard.
5. Generación de eventos de seguridad en los sistemas monitoreados.
6. Análisis de alertas detectadas por el SIEM.

---

## Eventos y alertas analizadas

### Linux

#### First time user executed sudo
- Nivel: Medio/Alto
- Descripción: Detección del primer uso de sudo por parte de un usuario.
- Relevancia: Posible escalada de privilegios o cambio de comportamiento.

#### User changed password
- Nivel: Medio
- Descripción: Modificación de credenciales de usuario.
- Relevancia: Manipulación de cuentas o intento de persistencia.

#### New group added to the system
- Nivel: Alto
- Descripción: Creación de un nuevo grupo en el sistema.
- Relevancia: Posible asignación de permisos adicionales.

---

### Windows

#### Failed logon
- Nivel: Medio
- Descripción: Intento de inicio de sesión fallido en el sistema.
- Relevancia: Detección de autenticaciones anómalas.

#### User created
- Nivel: Medio
- Descripción: Creación de una cuenta local en Windows.
- Relevancia: Manipulación de cuentas del sistema.

#### Administrator group changed
- Nivel: Medio/Alto
- Descripción: Modificación de un grupo privilegiado en Windows.
- Relevancia: Evento asociado a escalada de privilegios.

---

## Resultados

- Ambos agentes (Linux y Windows) se conectaron correctamente al Wazuh Server.
- Se recolectaron logs en tiempo real desde sistemas heterogéneos.
- El SIEM detectó eventos relacionados con autenticación, escalada de privilegios y gestión de cuentas.
- Las alertas fueron visualizadas y analizadas desde el dashboard.

---

## Evidencias

Las evidencias del laboratorio se encuentran en el directorio correspondiente del repositorio e incluyen:

- Captura del estado Active de ambos agentes (Linux y Windows).
- Alertas de autenticación fallida en Windows.
- Alertas de creación de usuarios y modificación de grupos privilegiados en Windows.
- Alertas de escalada de privilegios y gestión de cuentas en Linux.

---

## Aprendizajes

- Arquitectura y funcionamiento de un SIEM.
- Instalación y gestión de agentes Wazuh en Linux y Windows.
- Análisis de eventos de seguridad en entornos heterogéneos.
- Detección de escalada de privilegios y manipulación de cuentas.
- Resolución de problemas reales de servicios, permisos y recolección de logs.
