# Prácticas de Alta Disponibilidad y Sincronización en RHEL 10

Este repositorio contiene la implementación de tres prácticas realizadas en **Red Hat Enterprise Linux 10 (RHEL 10)**, enfocadas en sincronización de archivos, automatización de tareas y alta disponibilidad de servicios. Cada práctica incluye su configuración, scripts utilizados y evidencias del funcionamiento.

## Objetivos

- Implementar sincronización automática de archivos utilizando **Rsync**.
- Automatizar tareas mediante **Cron**.
- Configurar un clúster de alta disponibilidad con **Pacemaker** y **Corosync**.
- Implementar alta disponibilidad para un servicio web utilizando **Keepalived**.

---

# Práctica 1 - Sincronización de carpetas con Rsync

## Descripción

Se configuró un mecanismo de sincronización entre un servidor principal y un servidor secundario utilizando **Rsync** sobre **SSH**.

### Actividades realizadas

- Creación de una carpeta en el servidor principal.
- Generación de 100 archivos mediante el comando `touch`.
- Sincronización del contenido hacia el servidor remoto utilizando `rsync`.
- Creación de un script Bash para automatizar la sincronización.
- Configuración de una tarea programada con `crontab` para ejecutarse cada minuto.
- Validación del funcionamiento creando nuevos archivos en el servidor principal y comprobando su sincronización automática.

**Herramientas utilizadas**

- RHEL 10
- Rsync
- OpenSSH
- Bash
- Cron

---

# Práctica 2 - Cluster de Alta Disponibilidad con Pacemaker y Corosync

## Descripción

Se implementó un clúster de alta disponibilidad compuesto por dos nodos utilizando **Pacemaker** y **Corosync**, configurando una dirección IP virtual (Floating IP) para garantizar la continuidad del servicio.

### Actividades realizadas

- Instalación de Pacemaker y Corosync.
- Configuración del clúster de dos nodos.
- Configuración de una IP flotante.
- Validación del failover mediante reinicios alternados de los servidores.
- Verificación de la disponibilidad continua mediante pruebas de conectividad con `ping`.

**Herramientas utilizadas**

- RHEL 10
- Pacemaker
- Corosync
- pcs
- Floating IP

---

# Práctica 3 - Cluster de Alta Disponibilidad HTTP con Keepalived

## Descripción

Se implementó un servicio web altamente disponible utilizando **Apache HTTP Server** y **Keepalived**.

Cada servidor aloja una página HTML que identifica el nodo correspondiente (Server1 y Server2), mientras que Keepalived administra una dirección IP virtual para ofrecer acceso transparente al servicio.

### Actividades realizadas

- Instalación de Apache HTTP Server.
- Configuración de páginas HTML independientes en cada servidor.
- Instalación y configuración de Keepalived.
- Configuración del protocolo VRRP para administrar la IP virtual.
- Validación de la alta disponibilidad apagando uno de los servidores y verificando el acceso continuo desde el navegador.

**Herramientas utilizadas**

- RHEL 10
- Apache HTTP Server
- Keepalived
- VRRP

---

# Requisitos

- Dos servidores con RHEL 10.
- Acceso como usuario con privilegios administrativos.
- Comunicación de red entre ambos nodos.
- Acceso SSH configurado.
- Interfaces de red en modo Bridge.

---

Cada práctica incluye capturas de pantalla donde se muestran:

- Instalación de los paquetes.
- Configuración de los servicios.
- Scripts utilizados.
- Pruebas de sincronización.
- Estado del clúster.
- Funcionamiento del failover.
- Resultados obtenidos.

---

# Autor

**Víctor De Peña**

Prácticas desarrolladas en **Red Hat Enterprise Linux 10 (RHEL 10)** para la asignatura de Administración de Servidores Linux.
