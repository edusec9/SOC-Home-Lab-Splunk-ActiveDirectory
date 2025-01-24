# **SOC Home Lab**

Este repositorio documenta cómo construir un laboratorio SOC local con **Active Directory** y **Splunk**. El objetivo es simular un entorno real para la detección y respuesta a amenazas, enfocado en desarrollar habilidades del Blue Team.

---

## **Tabla de Contenidos**
1. [Requisitos del Laboratorio](#requisitos-del-laboratorio)  
2. [Arquitectura del Laboratorio](#arquitectura-del-laboratorio)  
3. [Guías Documentadas](#guías-documentadas)  
    - [1. Instalación de Sistemas Operativos](#1-instalación-de-sistemas-operativos)  
    - [2. Instalación y Configuración de Splunk | Sysmon](#2-instalación-y-configuración-de-splunk--sysmon)  
    - [3. Configuración de Active Directory](#3-configuración-de-active-directory)  
    - [4. Simulación de Ataques con Kali Linux](#4-simulación-de-ataques-con-kali-linux)  
4. [Prácticas y Detección de Amenazas](#prácticas-y-detección-de-amenazas)  
5. [Referencias](#referencias)  

---

## **Requisitos del Laboratorio**
- **Almacenamiento**: 250 GB  
- **Memoria RAM**: 16 GB (recomendado)  
- **Hardware/Software necesario**:
  - Virtualización: VMware o VirtualBox.
  - Imágenes ISO: Windows 10 Pro, Windows Server 2022, Kali Linux, Ubuntu Server.  

---

## **Arquitectura del Laboratorio**
El laboratorio consiste en:  
1. Un controlador de dominio basado en **Active Directory**.  
2. Un servidor de monitoreo con **Splunk**, configurado para recibir datos de **Sysmon**.  
3. Máquinas simuladas de ataque y prueba: **Kali Linux** y **Windows 10 Pro**.  

*Diagrama general del laboratorio:

![Arquitectura del Laboratorio](https://github.com/user-attachments/assets/ca040f7a-6103-4486-b762-add3350b4b1b)


---

## **Guías Documentadas**

### **1. Instalación de Sistemas Operativos**
- **Descripción**: 
  Esta guía detalla cómo instalar los sistemas operativos necesarios para el laboratorio. Incluye:  
  - Instalación de **Windows 10 Pro** para simular un endpoint empresarial.  
  - Configuración de **Kali Linux** como máquina atacante.  
  - Instalación de **Windows Server 2022** para configurar Active Directory.  
  - Configuración de **Ubuntu Server** para instalar Splunk.  
- **Contenido del archivo**:  
  - Configuración de redes virtuales para permitir la comunicación entre las máquinas.  
  - Capturas de pantalla y pasos detallados para la instalación de cada sistema operativo.  
  - Ver guía completa: [Instalación de los sistemas operativos](https://github.com/edusec9/SOC-Home-Lab/blob/main/1.Instalacion-Sistemas-Operativos.md)  

---

### **2. Instalación y Configuración de Splunk | Sysmon**
- **Descripción**:  
  Esta sección explica cómo instalar y configurar **Splunk** como herramienta SIEM, y cómo utilizar **Sysmon** para capturar eventos detallados en las máquinas Windows.  
- **Contenido del archivo**:  
  - Instalación de Splunk en Ubuntu Server.  
  - Configuración de un **Universal Forwarder** para enviar logs desde máquinas Windows.  
  - Instalación y configuración de **Sysmon** en el endpoint Windows para monitorizar eventos críticos como creación de procesos y conexiones de red.  
  - Ejemplo de búsquedas en Splunk para visualizar los eventos recolectados.  
  - Ver guía completa: [Instalar y configurar Splunk | Sysmon](https://github.com/edusec9/SOC-Home-Lab/blob/main/2.Instalar-y-configurar-Splunk-Sysmon.md)  

---

### **3. Configuración de Active Directory**
- **Descripción**:  
  Una guía detallada sobre cómo configurar un dominio usando **Active Directory** en Windows Server 2022.  
- **Contenido del archivo**:  
  - Configuración inicial del controlador de dominio.  
  - Creación de usuarios y grupos simulando una estructura empresarial.  
  - Configuración de políticas de grupo (Group Policy Objects, GPOs) para simular entornos reales.  
  - Pruebas básicas de autenticación en el dominio usando la máquina Windows 10.  
  - Ver guía completa: [Instalar y Configurar Active Directory](https://github.com/edusec9/SOC-Home-Lab/blob/main/3.Instalar-y-Configurar-Active-Directory.md)  

---

### **4. Simulación de Ataques con Kali Linux**
- **Descripción**:  
  Demostración práctica de cómo simular ataques y analizarlos en el laboratorio SOC.  
- **Contenido del archivo**:  
  - Configuración de **Kali Linux** para realizar un ataque de fuerza bruta contra servicios como RDP o SSH.  
  - Análisis de logs en Splunk para identificar intentos fallidos de inicio de sesión (**EventCode 4625**).  
  - Ejemplo de cómo configurar alertas en Splunk basadas en los eventos detectados.  
  - Ver guía completa: [Ataque de Fuerza Bruta con Kali Linux](https://github.com/edusec9/SOC-Home-Lab/blob/main/4.Kali-Linux-ataque-fuerza-bruta.md)  

---

## **Prácticas y Detección de Amenazas**
En este laboratorio, aprenderás a:  
- Detectar intentos de **fuerza bruta** usando búsquedas en Splunk.  
- Configurar dashboards en Splunk para monitorear actividad sospechosa.  
- Identificar eventos generados por herramientas como Sysmon y Active Directory.  

---

## **Referencias**

- **Splunk**: [Documentación oficial de Splunk](https://docs.splunk.com/)  
- **Microsoft Sysmon**: [Microsoft Sysmon](https://learn.microsoft.com/en-us/sysinternals/downloads/sysmon)  
- **Active Directory**: [Instalación de Active Directory](https://learn.microsoft.com/en-us/windows-server/identity/ad-ds/deploy/install-active-directory-domain-services--level-100-)  
- **Remote Desktop Protocol (RDP)**: [Understanding Remote Desktop Protocol (RDP)](https://learn.microsoft.com/en-us/troubleshoot/windows-server/remote/understanding-remote-desktop-protocol)  
- **Hydra**: [THC-Hydra GitHub Repository](https://github.com/vanhauser-thc/thc-hydra)  
- **Ubuntu Server**: [Ubuntu Server Documentation](https://ubuntu.com/server/docs)  


