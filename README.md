# 🧩 Lab_VirtualizacionConVMware
Laboratorio completo y documentado sobre **virtualización profesional usando VMware Workstation Pro, ESXi, vCenter y redes virtuales**, orientado al aprendizaje avanzado, pruebas de infraestructura y simulación de entornos empresariales.

Este proyecto demuestra mi capacidad para **diseñar, desplegar, administrar, automatizar y centralizar la gestion (Conmutador Distribuido) de un entorno de virtualización real**, utilizando tanto herramientas gráficas como consola (SSH/ESXi Shell), configuraciones de red, almacenamiento, snapshots, creación manual de VMs mediante archivos `.vmx`, y conceptos clave de arquitectura.

---

## 📌 Objetivo del Proyecto

Diseñar y construir un ecosistema virtual completamente funcional, compuesto por:

- **VMware Workstation Pro** como hipervisor base  
- **ESXi 8.x** instalado de forma nested  
- **vCenter Server Appliance (VCSA)** para administración centralizada  
- **Configuración de redes virtuales (vSwitch / vDS)**  
- **Creación de múltiples VMs para escenarios reales**  
- **DNS en Windows Server para resolución y dependencias del vCenter**  
- **Análisis de datastore, VMFS y discos virtuales**  
- **Automatización y administración por SSH**

Este laboratorio reproduce un entorno real de un **datacenter virtual**.

---

## 🏗️ Arquitectura del Laboratorio

### 🖥️ Host Físico – VMware Workstation Pro
El host físico actúa como plataforma base donde se ejecutan todos los hipervisores y máquinas virtuales del entorno.  
Desde aquí se gestiona el hardware físico (CPU, RAM, almacenamiento, redes) que alimenta todo el laboratorio.

---

### 🔧 Hipervisores ESXi (Nested)

#### ✔ ESXi #1 — Nodo Principal
- Host configurado con **Management Network**
- Interfaces **VMkernel** para:
  - Gestión (vSphere)
  - Comunicación con vCenter
- Almacena máquinas virtuales de pruebas

#### ✔ ESXi #2 — Nodo Adicional
- Participa como host extra dentro del laboratorio
- Permite simular escenarios multi-host
- Útil para pruebas de migraciones, redes, almacenamiento y clustering

#### ✔ ESXi #3 — Nodo Adicional
- Segundo host extra para topología avanzada
- Usado para:
  - vSphere Distributed Switch (vDS)
  - Alta disponibilidad (HA) en entornos de simulación
  - Balanceo de carga entre hosts

---

### 🎛️ vCenter Server Appliance (VCSA)
El centro de control del entorno VMware.

Incluye:

- **Gestión centralizada** de los hosts ESXi
- **Inventario completo** de máquinas virtuales y redes
- **Configuración del Distributed Virtual Switch (vDS)**
- **Supervisión de rendimiento y logs**
- **Usuarios, roles, permisos y certificados**

Requisitos complementarios:

- Un **DNS interno** que resuelva el FQDN del vCenter
- Configuración estable de red y VMkernel en cada host
- IP estática + registros A/PTR en Windows DNS

---

### 🌐 Servicios Adicionales

#### 🧩 Windows Server (DNS)
- Proporciona:
  - Resolución directa (A)
  - Zona inversa (PTR)
  - Requisito esencial para desplegar vCenter
- Mantiene consistencia entre los hosts y el VCSA

#### 🛜 Redes del Laboratorio
- Gestión
- Tráfico de máquinas virtuales
- VMkernel (Management)
- Opcional:
  - vMotion
  - vSAN
  - Storage Network (iSCSI/NFS)

---

### 🧱 Resumen Visual

- **Host Físico**
  - Workstation Pro (hipervisor tipo 2)

- **Hipervisores Nested**
  - ESXi #1 (principal)
  - ESXi #2 (nodo)
  - ESXi #3 (nodo)

- **Orquestación**
  - VCSA (vCenter Server Appliance)

- **Servicios de Red**
  - DNS interno (Windows Server)

- **Componentes Avanzados**
  - Distributed Switch (vDS)
  - Gestión centralizada del clúster

---

## 📸 Imágenes del Proyecto

Las imágenes del repositorio se encuentran en:  
**`assets/images/`**

Aquí puedes ver algunas de las algunas capturas principales utilizadas en el proyecto:

### 🔧 Configuración del Host ESXi
![](assets/images/Esxi1_ConfigVM.PNG)

![](assets/images/Esxi1_HostClientWeb.png)

![](assets/images/Esxi1_HostClientRedes.png)

---

### 🌐 Configuración de Redes VMkernel
![](assets/images/Esxi1_VMKernel.png)

![](assets/images/Esxi2_VMKernel.png)

![](assets/images/Esxi3_VMKernel.png)

---

### 🔌 Configuración del vSwitch y vDS
![](assets/images/Esxi3_vSwitch0.PNG)

![](assets/images/Esxi3_vDSwitch_1uplink.PNG)

---

### 🧠 vCenter Server Appliance
![](assets/images/VMvCenter_vSphereClientWeb.PNG)

![](assets/images/VMvCenter_VMKernel.png)

![](assets/images/VMvCenter_DSwitch_distribuido.PNG)

---

### 📡 DNS Server – Dependencia esencial para vCenter
![](assets/images/WinServerDNS_ConfigIP.png)

![](assets/images/WinServerDNS_ConfigVM.png)

![](assets/images/WinServerDNS_Zonas.png)

---

## 🧰 Tecnologías Utilizadas

### 🟦 VMware Stack
- VMware Workstation Pro 25H2
- VMware ESXi 8.x (nested)
- vCenter Server Appliance 8.x
- VMware Tools
- VMFS6
- vSwitch & vDSwitch

### 🟨 Windows Server & Servicios
- Windows Server 2019/2022
- DNS Server para resolución de FQDN del VCSA

### 🟩 Linux (en pruebas)
- Ubuntu Server para testing de despliegue

---

## 🎓 Habilidades Demostradas

✔ Instalación completa de **ESXi 8.x** en nested  
✔ Creación de **datastores VMFS6**  
✔ Alojamiento de máquinas virtuales con discos virtuales personalizados  
✔ Configuración avanzada de **vSwitch**, **portgroups**, VLANs y **VMkernel**  
✔ Creación de un **Distributed Virtual Switch (vDS)**  
✔ Despliegue y configuración del **vCenter Server Appliance**  
✔ Integración con **DNS** (A / PTR)  
✔ Gestión completa por **SSH / ESXi Shell**  
✔ Edición manual de archivos `.vmx`  
✔ Montaje de ISOs y despliegue desde consola  
✔ Gestión de snapshots y herramientas de mantenimiento  

---

## 🔥 ¿Qué se puede aprender con este proyecto?

Este laboratorio sirve como base para aprender:

- Arquitectura real de un entorno de virtualización empresarial  
- Gestión centralizada con vCenter  
- Redes distribuidas y segmentación  
- Automatización básica  
- Buenas prácticas de despliegue  
- Diagnóstico y resolución de problemas  
- Entender cómo se interconectan los componentes del ecosistema VMware  

---

## 🛠️ Próximas Mejoras

- Agregar documentación completa en `/docs/`
- Añadir scripts de automatización por SSH y PowerCLI
- Crear plantillas `.vmx` listas para usar
- Incluir topologías de red detalladas
- Añadir comparativa con Microsoft Hyper‑V

---

## 📬 Contacto

Si quieres colaborar o tienes sugerencias:

**Autor:** *EXXEL ADRIAN JIBAJA MACEDO*  
**GitHub:** https://github.com/eadrianjm16

---

## ⭐ Si este proyecto te ha servido o parecido interesante, ¡no olvides dejar una estrella!

