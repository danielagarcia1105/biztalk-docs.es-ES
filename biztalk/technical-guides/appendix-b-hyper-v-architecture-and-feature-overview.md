---
title: 'Apéndice B: arquitectura de Hyper-V y la introducción a las características | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 87b6b9a0-a470-43f7-b076-36075477cc34
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 613c0a28d9aaf3f8a07b34b65345979d69223668
ms.sourcegitcommit: 32f380810b90b70e5df7be72a6a14988a747868e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2018
ms.locfileid: "29710307"
---
# <a name="appendix-b-hyper-v-architecture-and-feature-overview"></a>Apéndice B: arquitectura de Hyper-V y la introducción a las características
En este tema se proporciona información general de arquitectura de Hyper-V, describe las ventajas y desventajas de Hyper-V.  
  
## <a name="hyper-v-architecture"></a>Arquitectura de Hyper-V  
  
 Hyper-V es una plataforma de virtualización basada en hipervisor y una tecnología impulsora para una de las características de marquesina de servidor de Windows, migración en vivo. Con Hyper-V, Windows Server es capaz de una migración rápida, que podría mover máquinas virtuales entre hosts físicos con solo unos pocos segundos de tiempo de inactividad. Con migración en vivo, se mueve entre destinos físicos se producen en milisegundos, lo que significa que las operaciones de migración están visibles para los usuarios conectados. Vea [Novedades de Hyper-V en Windows Server](https://docs.microsoft.com/windows-server/virtualization/hyper-v/what-s-new-in-hyper-v-on-windows).
  
 El hipervisor es la plataforma de virtualización específica del procesador que puede hospedar varias máquinas virtuales (VM) que están aisladas entre sí pero comparten los recursos de hardware subyacentes mediante la virtualización de los procesadores, memoria y dispositivos de E/S.  
  
 Sistemas operativos invitados en una máquina virtual de Hyper-V proporciona rendimiento alcanzando el rendimiento de un sistema operativo que se ejecuta en hardware físico *si* los controladores de cliente (VSC) del servidor virtual es necesario y servicios se instalan en el sistema operativo invitado. Código de cliente (VSC) del servidor virtual de Hyper-V, también conocido como Hyper-V habilitadas i/OS, permite el acceso directo a la "Bus de máquina Virtual" de Hyper-V y está disponible con la instalación de servicios de integración de Hyper-V. Servicios de integración de Hyper-V que proporcionan controladores VSC también están disponibles para otros sistemas operativos de cliente.  
  
 Hyper-V ofrece aislamiento en términos de una partición. Una partición es una unidad lógica de aislamiento, admitido por el hipervisor, en la que se ejecutan sistemas operativos. El hipervisor de Microsoft debe tener al menos un elemento primario, o raíz, partición, ejecute Windows Server. La pila de virtualización se ejecuta en la partición principal y tiene acceso directo a los dispositivos de hardware. La partición raíz, a continuación, crea al elemento secundario particiones que hospedan los sistemas operativos invitados. Una partición raíz crea particiones secundarias mediante la interfaz de programación de aplicaciones (API) de hiperllamadas.  
  
 Las particiones no tiene acceso al procesador físico ni controlan las interrupciones del procesador. En su lugar, que dispone de una vista del procesador virtual y se ejecuten en una región de la dirección de memoria virtual que es privada para cada partición de invitado. El hipervisor administra las interrupciones del procesador y redirigirá a la partición correspondiente. Hyper-V también puede acelerar el hardware la traducción de direcciones entre varios espacios de direcciones virtuales del invitado mediante el uso de una entrada salida memoria administración unidad (IOMMU) que funciona de forma independiente del hardware de administración de memoria utilizado por la CPU. Un IOMMU se utiliza para asignar direcciones de memoria física para las direcciones que usan las particiones secundarias.  
  
 Las particiones secundarias también no tiene acceso directo a otros recursos de hardware y se presentan una vista virtual de los recursos, como dispositivos virtuales (vdisp). Las solicitudes a los dispositivos virtuales se redirigen a través de VMBus o el hipervisor en los dispositivos en la partición primaria, que controla las solicitudes. VMBus es un canal de comunicación entre partición lógicos. La partición primaria hospeda los proveedores de servicios de virtualización (vsp) que se comunican a través de VMBus para controlar las solicitudes de acceso de dispositivo de las particiones secundarias. Las particiones secundarias hospedan de virtualización de los consumidores del servicio (VSC) que redirigir las solicitudes del dispositivo a VSPs en la partición primaria a través de VMBus. Todo este proceso es transparente para el sistema operativo invitado.  
  
 Dispositivos virtuales también pueden beneficiarse de una característica de virtualización de Windows Server, denominada habilitadas, la E/S de almacenamiento, redes, gráficos y subsistemas de entrada. E/S habilitadas es una implementación especializada de preparado para virtualización de protocolos de comunicación de alto nivel (por ejemplo, SCSI) que utilizan VMBus directamente, omitiendo cualquier capa de emulación de dispositivos. Esto hace que la comunicación sea más eficaz, pero requiere a un invitado habilitada hipervisor y VMBus tenga en cuenta. E/S había habilitada para Hyper-V e hipervisor compatible con kernel se proporciona a través de la instalación de Hyper-V integration services. Componentes de integración, que incluyen controladores de cliente (VSC) de virtual server, también están disponibles para otros sistemas operativos de cliente. Hyper-V requiere un procesador que incluya la virtualización asistida por hardware, como se proporciona con Intel VT o tecnología de AMD Virtualization (AMD-V).  
  
 El siguiente diagrama proporciona una descripción general de la arquitectura de un entorno de Hyper-V que se ejecuta en Windows Server.  
  
 ![Hyper &#45; Introducción a la arquitectura V](../technical-guides/media/eadd2a84-3936-4b48-a0e2-05b94882d848.gif "eadd2a84-3936-4b48-a0e2-05b94882d848")  

  
 Acrónimos y términos usados en el diagrama anterior se describen a continuación:  
  
-   **APIC** – Advanced controladora programable de interrupciones. Da como resultado un dispositivo que permite a los niveles de prioridad que se asignará a la interrupción.  
  
-   **Partición secundaria** : partición que hospeda un sistema operativo invitado. Todos los accesos a memoria física y los dispositivos por una partición secundaria se proporcionan a través del Bus de máquina Virtual (VMBus) o el hipervisor.  
  
-   **Hiperllamadas** : interfaz para la comunicación con el hipervisor. La interfaz de hiperllamadas permite a su acceso a las optimizaciones proporcionada por el hipervisor.  
  
-   **Hipervisor** : una capa de software que se encuentra entre el hardware y uno o más sistemas operativos. Su tarea principal consiste en proporcionar entornos de ejecución aislados que se denominan particiones. El hipervisor controla y arbitra acceso al hardware subyacente.  
  
-   **IC** : componentes de integración. Componente que permite a secundario particiones para la comunicación con otras particiones y el hipervisor.  
  
-   **Pila de E/S** : pila de entrada/salida.  
  
-   **MSR** – rutina de servicio de memoria.  
  
-   **La partición raíz** : administra las funciones de nivel de equipo, como controladores de dispositivos y la administración de energía, activa Adición/eliminación del dispositivo. La partición raíz (o principal) es la única partición que tiene acceso directo a memoria física y los dispositivos.  
  
-   **VID** : controlador de infraestructura de virtualización. Proporciona servicios de administración de particiones, los servicios de administración de procesador virtual y los servicios de administración de memoria para las particiones.  
  
-   **VMBus** : mecanismo de comunicación basada en canal utilizado para la enumeración de comunicación y los dispositivos de partición entre en sistemas con varias particiones virtualizados activas. VMBus se instala con servicios de integración de Hyper-V.  
  
-   **VMMS** : servicio de administración de máquinas virtuales. Responsable de administrar el estado de todas las máquinas virtuales en las particiones secundarias.  
  
-   **VMWP** : proceso de trabajo de máquina Virtual. Un componente de modo de usuario de la pila de virtualización. El proceso de trabajo proporciona servicios de administración de máquinas virtuales de la instancia del servidor de Windows en la partición principal para los sistemas operativos de invitado en las particiones secundarias. El servicio de administración de máquinas virtuales, se genera un proceso de trabajo independiente para cada máquina virtual en ejecución.  
  
-   **VSC** : cliente de servicios de virtualización. Una instancia de dispositivo sintético que reside en una partición secundaria. VSC usan los recursos de hardware que se proporcionan con proveedores de servicios de virtualización (vsp) en la partición primaria. Se comunican con el VSPs correspondientes en la partición principal sobre VMBus para satisfacer que las solicitudes de E/S del dispositivo de particiones de un elemento secundario.  
  
-   **VSP** : proveedor de servicios de virtualización. Se encuentra en la partición raíz y proporcionan compatibilidad para las particiones secundarias sintético dispositivos a través de Bus de máquina Virtual (VMBus).  
  
-   **WinHv** : biblioteca de interfaz de hipervisor de Windows. WinHv es esencialmente un puente entre los controladores de un sistema operativo con particiones y el hipervisor que permite que los controladores llamar el hipervisor que usa las convenciones de llamada estándares de Windows  
  
-   **WMI** : el servicio de administración de máquinas virtuales expone un conjunto de API basadas en Windows Management Instrumentation WMI para administrar y controlar las máquinas virtuales.  
  
 La mayoría de estos términos se define en el [glosario](../technical-guides/glossary8.md).  
  
> [!NOTE]  
>  [Información general sobre la tecnología de Hyper-V](https://docs.microsoft.com/windows-server/virtualization/hyper-v/hyper-v-technology-overview) es un buen recurso. 
  
## <a name="advantages"></a>Ventajas
 Las ventajas de ejecutar soluciones de nivel empresarial en un entorno virtualizado de Hyper-V incluyen lo siguiente:  
  
1.  **Consolidación de recursos de hardware** -varios servidores físicos que se pueden consolidar fácilmente en comparativamente menos servidores mediante la implementación de virtualización con Hyper-V. Consolidación permite un uso completo de los recursos de hardware implementado. Hyper-V en Windows Server puede tener acceso a un máximo de 64 CPU lógicas en los equipos host. Esta capacidad no solo aprovecha las ventajas de los nuevos sistemas de varios núcleos, también significa mayores tasas de consolidación de máquinas virtuales por cada host físico.  
  
2.  **Facilidad de administración**:  
  
    -   Centralización de recursos y consolidación simplifica la administración.  
  
    -   Implementación de escalado vertical y escalado horizontal es acomodar con mucho mayor facilidad.  
  
3.  **Significativos ahorros en costos**:  
  
    -   Dado que varias máquinas virtuales pueden ejecutar en un solo equipo físico, se reducen considerablemente los costos de hardware, por lo tanto, no es necesario para todos los equipos de un equipo físico independiente.  
  
    -   Los costos de licencia de Hyper-V se pueden incluidos con el costo de licencia de Windows Server y también se puede adquirir como un producto independiente.
  
    -   Requisitos de energía pueden reducirse considerablemente mediante la consolidación de las aplicaciones existentes en un entorno virtualizado de Hyper-V porque el hardware físico reducido "huella" que es necesario.  
  
4.  **Error de compatibilidad con tolerancia a través de clústeres de Hyper-V** – porque Hyper-V es una aplicación compatible con clústeres, Windows Server proporciona compatibilidad con clústeres para las máquinas virtuales creadas en un entorno virtualizado de Hyper-V de host nativo.  
  
5.  **Facilidad de implementación y administración**:  
  
    -   Consolidación de servidores existentes en menos servidores físicos simplifica la implementación.  
  
    -   Una completa solución de administración de Hyper-V está disponible con System Center Virtual Machine Manager. [Novedades de VMM en System Center](https://docs.microsoft.com/system-center/vmm/whats-new?view=sc-vmm-2016) proporciona alguna orientación.
  
6.  **Características de rendimiento clave Hyper-V**:  
  
    -   **Arquitectura de uso compartido de hardware mejorada** : Hyper-V proporciona mejoras de acceso y la utilización de recursos principales, como el disco, la red, y sistemas operativos de vídeo al ejecutar invitados con un hipervisor compatible con kernel y que están equipados con código de cliente (VSC) de servidor virtual necesarios (conocido como había habilitada para Hyper-V i/OS). Optimizaciones son las mejoras realizadas en el sistema operativo para ayudar a reducir el costo de ciertas funciones de sistema operativo como la administración de memoria. Componentes de integración, que incluyen controladores VSC, también están disponibles para otros sistemas operativos de cliente.  
  
         Rendimiento del disco es fundamental para aplicaciones de empresa intensivo de E/S de disco, como Microsoft BizTalk Server y además de Hyper-V habilitadas E/S; Hyper-V proporciona la compatibilidad con discos de "Acceso directo" que proporciona el rendimiento de disco a la par de rendimiento de disco físico. Tenga en cuenta que "Acceso directo" soporte de disco proporciona un rendimiento mejorado con un pequeño impacto en comodidad. Discos de "Acceso directo" son básicamente discos/LUNs físicos que están conectados a una máquina virtual y no admiten algunas de las funciones de los discos virtuales, como instantáneas de máquina Virtual.  
  
    -   **Compatibilidad con la virtualización asistida por hardware de procesador** : Hyper-V aprovecha al máximo de compatibilidad de virtualización asistida por hardware de procesador que está disponible con la tecnología de procesador recientes.  
  
    -   **Compatibilidad con sistemas operativos de invitado de varios núcleos (SMP)** : Hyper-V proporciona la capacidad para admitir hasta cuatro procesadores en un entorno de máquina virtual, que permite a las aplicaciones aprovechar al máximo de la funcionalidad de subprocesamiento múltiple en un virtual máquina.  
  
    -   **Invitados de 32 bits y 64 bits compatibilidad con sistemas operativos** : Hyper-V ofrece una amplia compatibilidad con para diferentes tipos de sistemas operativos, incluidos los sistemas de 32 bits y 64 bits en plataformas de servidor diferente, como Windows, que se ejecutan simultáneamente Linux® y otros.  
  
8.  **Compatibilidad de productos completa** : dado que las aplicaciones de empresa de Microsoft (por ejemplo, Exchange Server y SQL Server) se han probado completamente ejecutando en Hyper-V, Microsoft proporciona soporte técnico de revisión de código para estas aplicaciones cuando implementado y se ejecutan en Hyper-V entorno.  
  
9. **Escalabilidad** : más potencia de procesamiento, ancho de banda de red y capacidad de almacenamiento puede realizarse rápida y fácilmente por prorratear más recursos disponibles del equipo host a las máquinas virtuales de invitado. Esto puede requerir que el equipo host está actualizado o que las máquinas virtuales invitadas se mueven a un equipo host mayor capacidad.  
  
 Para obtener información detallada acerca de las ventajas de aprovechar la tecnología de virtualización con Hyper-V, consulte el [información general sobre la tecnología de Hyper-V](https://docs.microsoft.com/windows-server/virtualization/hyper-v/hyper-v-technology-overview). 
  
## <a name="disadvantages"></a>Inconvenientes
 Entre las desventajas de ejecutar soluciones de nivel empresarial en un entorno virtualizado de Hyper-V pueden incluir:  
  
-   **Requisitos de hardware:** debido a las demandas de consolidación de servidores, máquinas virtuales de Hyper-V tienden a consumir más CPU y memoria y requieren mayor ancho de banda de E/S de disco que los servidores físicos con cargas informáticos comparables. Puesto que el rol de servidor de Hyper-V solo está disponible para todas las ediciones de Windows Server y de 64 bits son solo 64 bits, el hardware físico debe admitir virtualización asistida por hardware. Esto significa que el procesador debe ser compatible con Intel VT o tecnología de AMD Virtualization (AMD-V), el BIOS del sistema debe admitir la prevención de ejecución de datos (DEP) y DEP debe estar habilitada.  
  
-   **Requisitos de software:** mientras la mayoría del software de Microsoft se puede ejecutar en máquinas virtuales de Hyper-V, algunos programas de software de Microsoft aún está en proceso que se está probando para garantizar la compatibilidad con un entorno virtualizado de Hyper-V. Por ejemplo, la mayoría aplicaciones de nivel empresarial de Microsoft admiten la ejecución en Hyper-V o están en proceso que se está probando de compatibilidad de Hyper-V. Para obtener más información sobre la compatibilidad de BizTalk Server y SQL Server en Hyper-V, consulte [Apéndice C: BizTalk Server y compatibilidad de Hyper-V de SQL Server](../technical-guides/appendix-c-biztalk-server-and-sql-server-hyper-v-supportability.md).