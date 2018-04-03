---
copyright:
  years: 1994, 2017
lastupdated: "2017-06-05"
---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# La opción sin SO

Sin sistema operativo es una opción para solicitar un servidor nativo sin sistema operativo.

## ¿Cómo solicitar un servidor nativo sin ningún SO?

Primero, realice un pedido de servidor nativo mediante [SoftLayer.com](softlayer.com) o el [Portal del cliente](https://control.softlayer.com).

1. Seleccione **Otro** en **Configuración del sistema > Sistema operativo**.
2. Seleccione **Sin sistema operativo**.

## Cómo instalar un sistema operativo en un servidor sin SO

Hay dos métodos para instalar un sistema operativo en un servidor nativo sin sistema operativo.

### Opción 1: servidor PXE (Entorno de ejecución de prearranque)

Un servidor nativo sin sistema operativo se puede configurar para arrancar y cargar el SO desde una configuración de PXE (consulte [Preboot_Execution_Environment](http://en.wikipedia.org/wiki/Preboot_Execution_Environment) para obtener más información). Para ello, despliegue el servidor nativo en un entorno de red con una configuración de PXE (normalmente, esto implica ejecutar un daemon DHCP y TFTP) y configure el nuevo BIOS del servidor nativo para que se arranque desde el adaptador de red. Para que esto funcione correctamente, tenga en cuenta que la configuración de PXE debe estar en la misma VLAN que el adaptador de red, o será necesario utilizar reenvío de DHCP.

**Nota:** para que esta opción funcione, puede que sea necesario abrir una incidencia de soporte para solicitar que los puertos de conmutador se reagrupen en modalidad básica. Esto se debe a que el protocolo PXE no requiere compatibilidad con agregación de enlaces (LACP, consulte [Link Aggregation](http://en.wikipedia.org/wiki/Link_aggregation)), que ahora es una función estándar para proporcionar redundancia. Otra opción es solicitar el servidor con enlaces ascendentes desvinculados (sin agregación de enlaces) y luego, una vez instalado el SO, cambiarlos a enlaces ascendentes redundantes.

### Opción 2: dispositivo IPMI

Instalar un sistema operativo en un servidor nativo sin sistema operativo arrancando desde una ISO a través del dispositivo IPMI incluido. Pulse [aquí](mount-iso-bare-metal-server.html) para obtener más información sobre el arranque desde una ISO.
