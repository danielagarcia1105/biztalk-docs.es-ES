---
title: 'Apéndice B: arquitectura de Hyper-V e Introducción a las características | Microsoft Docs'
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
ms.openlocfilehash: d9e20add207d9e4303bd823b82b79e8fad6c07c3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37002149"
---
# <a name="appendix-b-hyper-v-architecture-and-feature-overview"></a>Apéndice B: arquitectura de Hyper-V e Introducción a las características
Este tema proporciona información general de arquitectura de Hyper-V, describe las ventajas y desventajas de Hyper-V.  
  
## <a name="hyper-v-architecture"></a>Arquitectura de Hyper-V  
  
 Hyper-V es una plataforma de virtualización basada en hipervisor y una tecnología para una de las características del servidor de Windows de marquesina, migración en vivo. Con Hyper-V, Windows Server es capaz de migración rápida, lo que podría mover las máquinas virtuales entre hosts físicos con solo unos pocos segundos de tiempo de inactividad. Con migración en vivo, se desplaza entre destinos físicos se producen en milisegundos, lo que significa que las operaciones de migración en es invisibles para los usuarios conectados. Consulte [cuáles son las novedades en Hyper-V en Windows Server](https://docs.microsoft.com/windows-server/virtualization/hyper-v/what-s-new-in-hyper-v-on-windows).
  
 El hipervisor es la plataforma de virtualización específica del procesador que puede hospedar varias máquinas virtuales (VM) que están aisladas entre sí, pero comparten los recursos de hardware subyacentes mediante la virtualización de los procesadores, memoria y dispositivos de E/S.  
  
 Sistemas operativos que se ejecutan en una máquina virtual de Hyper-V proporcionan rendimiento alcanzando el rendimiento de un sistema operativo que se ejecuta en hardware físico *si* los controladores de cliente (VSC) del servidor virtual es necesario y servicios se instalan en el sistema operativo invitado. Código de cliente (VSC) del servidor virtual de Hyper-V, también conocido como Hyper-V habilitada para la E/S, permite el acceso directo a Hyper-V "Bus de máquina Virtual" y está disponible con la instalación de Hyper-V integration services. Servicios de integración de Hyper-V que proporcionan controladores VSC también están disponibles para otros sistemas operativos de cliente.  
  
 Hyper-V admite el aislamiento en términos de una partición. Una partición es una unidad lógica de aislamiento admitido por el hipervisor, en el que se ejecutan los sistemas operativos. El hipervisor de Microsoft debe tener al menos un elemento primario, o raíz, partición, que ejecuta Windows Server. La pila de virtualización se ejecuta en la partición principal y tiene acceso directo a los dispositivos de hardware. La partición raíz, a continuación, crea al elemento secundario particiones que hospedan los sistemas operativos invitados. Una partición raíz crea particiones secundarias mediante la interfaz de programación de aplicaciones (API) de hiperllamada.  
  
 Particiones no tienen acceso al procesador físico ni controlan las interrupciones de procesador. En su lugar, tienen una vista del procesador virtual y ejecutar en una región de dirección de memoria virtual privada a cada partición de invitado. El hipervisor controla las interrupciones del procesador y las redirige a la partición correspondiente. Hyper-V también puede acelerar el hardware la traducción de direcciones entre varios espacios de direcciones virtuales del invitado mediante el uso de una entrada salida memoria administración unidad (IOMMU) que funciona de forma independiente del hardware de administración de memoria utilizado por la CPU. Se usa un IOMMU para volver a asignar las direcciones de memoria física en las direcciones que utilizan las particiones secundarias.  
  
 Las particiones secundarias también no tienen acceso directo a otros recursos de hardware y se presentan una vista virtual de los recursos, como dispositivos virtuales (vdisp). Las solicitudes a los dispositivos virtuales se redirigen a través de VMBus o el hipervisor a los dispositivos en la partición primaria, que controla las solicitudes. VMBus es un canal de comunicación entre particiones lógicos. La partición primaria hospeda los proveedores de servicios de virtualización (vsp) que se comunican a través de VMBus para controlar las solicitudes de acceso de dispositivo desde las particiones secundarias. Consumidores de servicio de virtualización (VSC) que redirigir las solicitudes del dispositivo a VSPs en la partición principal a través de VMBus de host de las particiones secundarias. Todo este proceso es transparente para el sistema operativo invitado.  
  
 Dispositivos virtuales también pueden aprovechar las ventajas de una característica de virtualización de Windows Server, denominada habilitada para operaciones de E/S, almacenamiento, redes, gráficos y los subsistemas de entrada. E/S habilitada es una implementación especializada que reconoce la virtualización de protocolos de comunicación de alto nivel (por ejemplo, SCSI) que usan VMBus directamente, omitiendo cualquier capa de emulación de dispositivos. Esto hace que la comunicación sea más eficaz pero requiere a un invitado habilitada para que sea el hipervisor y VMBus tenga en cuenta. Hyper-V habilitada para la E/S y un kernel consciente del hipervisor se proporciona a través de la instalación de Hyper-V integration services. Los componentes de integración, que incluyen controladores de cliente (VSC) del servidor virtual, también están disponibles para otros sistemas operativos de cliente. Hyper-V requiere un procesador que incluye la virtualización asistida por hardware, como se proporciona con Intel VT o la tecnología AMD Virtualization (AMD-V).  
  
 El siguiente diagrama proporciona una descripción general de la arquitectura de un entorno de Hyper-V que ejecutan Windows Server.  
  
 ![Hyper&#45;Introducción a la arquitectura V](../technical-guides/media/eadd2a84-3936-4b48-a0e2-05b94882d848.gif "eadd2a84-3936-4b48-a0e2-05b94882d848")  

  
 Acrónimos y términos usados en el diagrama anterior se describen a continuación:  
  
- **APIC** – Advanced controladora programable de interrupciones. Da como resultado un dispositivo que permite a los niveles de prioridad que se asignará a la interrupción.  
  
- **Partición secundaria** : partición que hospeda un sistema operativo invitado. Todos los accesos a memoria física y dispositivos mediante una partición secundaria se proporcionan a través del Bus de máquina Virtual (VMBus) o el hipervisor.  
  
- **Hiperllamadas** : interfaz para la comunicación con el hipervisor. Acceso a las optimizaciones que proporciona el hipervisor se adapta a la interfaz de hiperllamada.  
  
- **Hipervisor** : una capa de software que se encuentra entre el hardware y uno o más sistemas operativos. Su trabajo principal consiste en proporcionar entornos de ejecución aislados denominados particiones. El hipervisor controla y arbitra acceso al hardware subyacente.  
  
- **IC** : componente de integración. Componente que permite a secundarios particiones para la comunicación con el hipervisor y de otras particiones.  
  
- **Pila de E/S** : pila de entrada/salida.  
  
- **MSR** – rutina de servicio de la memoria.  
  
- **Partición raíz** : administra las funciones de nivel de equipo, como controladores de dispositivos, administración de energía y hot Adición/eliminación del dispositivo. La partición raíz (o principal) es la única partición que tiene acceso directo a memoria física y los dispositivos.  
  
- **VID** – controlador de la infraestructura de virtualización. Proporciona servicios de administración de la partición, los servicios de administración de procesador virtual y los servicios de administración de memoria para las particiones.  
  
- **VMBus** : mecanismo de comunicación basada en canal utilizado para la enumeración de comunicación y el dispositivo entre particiones en los sistemas con varias particiones virtualizadas activas. VMBus se instala con Hyper-V Integration Services.  
  
- **VMMS** : servicio de administración de máquinas virtuales. Responsable de administrar el estado de todas las máquinas virtuales en las particiones secundarias.  
  
- **VMWP** : proceso de trabajo de máquina Virtual. Un componente de modo de usuario de la pila de virtualización. El proceso de trabajo proporciona servicios de administración de máquinas virtuales de la instancia del servidor de Windows en la partición principal para los sistemas operativos de invitado en las particiones secundarias. El servicio de administración de máquinas virtuales se genera un proceso de trabajo independiente para cada máquina virtual en ejecución.  
  
- **VSC** : cliente de servicio de virtualización. Una instancia de dispositivo sintético que reside en una partición secundaria. VSC usan los recursos de hardware que se proporcionan los proveedores de servicios de virtualización (vsp) en la partición principal. Se comunican con el VSPs correspondientes en la partición principal a través de VMBus para satisfacer que las solicitudes de E/S del dispositivo de particiones de un elemento secundario.  
  
- **VSP** : proveedor de servicios de virtualización. Se encuentra en la partición raíz y proporcionar soporte técnico de dispositivo sintético para las particiones secundarias a través del Bus de máquina Virtual (VMBus).  
  
- **WinHv** : biblioteca de interfaz de hipervisor de Windows. WinHv es esencialmente un puente entre los controladores del sistema operativo con particiones y el hipervisor que permite que los controladores llamar al hipervisor que usa el estándares convenciones de llamada de Windows  
  
- **WMI** : el servicio de administración de la máquina Virtual se expone un conjunto de API de Instrumental de administración de Windows WMI para administrar y controlar las máquinas virtuales.  
  
  La mayoría de estos términos se define en el [glosario](../technical-guides/glossary8.md).  
  
> [!NOTE]  
>  [Introducción a la tecnología Hyper-V](https://docs.microsoft.com/windows-server/virtualization/hyper-v/hyper-v-technology-overview) es un buen recurso. 
  
## <a name="advantages"></a>Ventajas
 Las ventajas de las soluciones de nivel empresarial en ejecución en un entorno virtualizado de Hyper-V incluyen lo siguiente:  
  
1. **Consolidación de recursos de hardware** -varios servidores físicos se pueden consolidar fácilmente en un número comparativamente menor de servidores mediante la implementación de virtualización con Hyper-V. La consolidación se adapta a un uso completo de los recursos de hardware implementado. Hyper-V en Windows Server puede tener acceso a un máximo de 64 CPU lógicas en los equipos host. Esta funcionalidad no solo aprovecha las ventajas de los nuevos sistemas de varios núcleos, también significa mayores tasas de consolidación máquina virtual por cada host físico.  
  
2. **Facilidad de administración**:  
  
   -   La centralización de los recursos y la consolidación simplifica la administración.  
  
   -   Implementación de escalado vertical y escalado horizontal se ajuste con mucha más facilidad.  
  
3. **Ahorro de costos de significativos**:  
  
   -   Dado que puede ejecutar varias máquinas virtuales en un solo equipo físico, se reducen considerablemente los costos de hardware, por lo tanto, no es necesaria para todos los equipos de una máquina física separada.  
  
   -   Los costos de licencia de Hyper-V puedan estar incluidos en el costo de licencia de Windows Server y también deben adquirirse como un producto independiente.
  
   -   Se pueden reducir significativamente los requisitos de energía mediante la consolidación de las aplicaciones existentes en un entorno virtualizado de Hyper-V porque el hardware físico reducido "huella" que es necesario.  
  
4. **Error de compatibilidad con tolerancia a través de clústeres de Hyper-V** – porque Hyper-V es una aplicación compatible con clústeres, Windows Server proporciona compatibilidad con clústeres para las máquinas virtuales creadas en un entorno virtualizado de Hyper-V de host nativo.  
  
5. **Facilidad de implementación y administración**:  
  
   -   Consolidación de servidores existentes en menos servidores físicos simplifica la implementación.  
  
   -   Una completa solución de administración de Hyper-V está disponible con System Center Virtual Machine Manager. [Novedades de VMM en System Center](https://docs.microsoft.com/system-center/vmm/whats-new?view=sc-vmm-2016) proporciona alguna orientación.
  
6. **Características de rendimiento clave Hyper-V**:  
  
   -   **Arquitectura compartida de hardware mejorada** : Hyper-V proporciona mejoras de acceso y la utilización de recursos principales, como el disco, la red, y vídeo al ejecutar invitados sistemas operativos con un kernel con reconocimiento del hipervisor y que están equipados con código de cliente (VSC) de servidor virtual necesaria (conocido como Hyper-V habilitada para la E/S). Mejoras de código son las mejoras realizadas en el sistema operativo para ayudar a reducir el costo de determinadas funciones del sistema operativo, como la administración de memoria. Los componentes de integración, que incluyen controladores VSC, también están disponibles para otros sistemas operativos de cliente.  
  
        Rendimiento del disco es fundamental para aplicaciones de enterprise con uso intensivo de E/S de disco, como Microsoft BizTalk Server y además de Hyper-V habilitada para E/S; Hyper-V proporciona compatibilidad de disco de "Acceso directo" que proporciona el rendimiento de disco a la par de rendimiento de disco físico. Tenga en cuenta que "Passthrough" soporte de disco proporciona un rendimiento mejorado con un costo pequeño para mayor comodidad. Discos de "acceso directo" son esencialmente discos/LUNs físicos que están conectados a una máquina virtual y no admiten algunas de las funcionalidades de los discos virtuales, como las instantáneas de máquina Virtual.  
  
   -   **Compatibilidad de virtualización asistida por hardware de procesador** : Hyper-V aprovecha al máximo de compatibilidad de virtualización asistida por hardware de procesador que está disponible con la tecnología de procesador recientes.  
  
   -   **Compatibilidad del sistema operativo de invitado de varios núcleos (SMP)** : Hyper-V proporciona la capacidad para admitir hasta cuatro procesadores en un entorno de máquina virtual, que permite a las aplicaciones aprovechar al máximo la funcionalidad de subprocesamiento múltiple en un virtual máquina.  
  
   -   **Invitados de 32 bits y 64 bits: compatibilidad con sistemas operativos** : Hyper-V proporciona una amplia compatibilidad para ejecutar simultáneamente diferentes tipos de sistemas operativos, incluidos los sistemas de 32 bits y 64 bits en plataformas de servidor diferente, como Windows, Linux® y otros.  
  
7. **Servicio de soporte técnico integral** : dado que las aplicaciones de empresa de Microsoft (como Exchange Server y SQL Server) se han probado completamente que se ejecutan en Hyper-V, Microsoft proporciona soporte técnico de corrección de código para estas aplicaciones cuando implementado y se ejecutan en Hyper-V entorno.  
  
8. **Escalabilidad** : más potencia de procesamiento, ancho de banda de red y capacidad de almacenamiento puede realizarse rápida y fácilmente mediante prorrateo de recursos adicionales disponibles desde el equipo host para las máquinas virtuales de invitado. Esto puede requerir que se actualiza el equipo host o que las máquinas virtuales invitadas se mueven a un equipo host con más capacidad.  
  
   Para obtener información más detallada acerca de las ventajas de aprovechar la tecnología de virtualización con Hyper-V, consulte el [Introducción a la tecnología Hyper-V](https://docs.microsoft.com/windows-server/virtualization/hyper-v/hyper-v-technology-overview). 
  
## <a name="disadvantages"></a>Inconvenientes
 Entre las desventajas de la ejecución de soluciones de nivel empresarial en un entorno virtualizado de Hyper-V pueden incluir:  
  
-   **Requisitos de hardware:** debido a las exigencias de consolidación de servidores, máquinas virtuales de Hyper-V tienden a consumen más CPU y memoria y requieren mayor ancho de banda de E/S de disco que los servidores físicos con cargas informáticos comparables. Dado que el rol de servidor Hyper-V sólo está disponible para todas las ediciones de Windows Server y de 64 bits son solo 64 bits, el hardware físico debe admitir virtualización asistida por hardware. Esto significa que el procesador debe ser compatible con Intel VT o la tecnología AMD Virtualization (AMD-V), el BIOS del sistema debe admitir la prevención de ejecución de datos (DEP) y DEP debe estar habilitada.  
  
-   **Requisitos de software:** aunque se admite la mayoría del software Microsoft que se ejecutan en máquinas virtuales de Hyper-V, algunos programas de software de Microsoft aún está en proceso para garantizar la compatibilidad con un entorno virtualizado de Hyper-V está probando. Por ejemplo, la mayoría aplicaciones de nivel empresarial de Microsoft admiten la ejecución en Hyper-V o están en proceso que se está probando de compatibilidad de Hyper-V. Para obtener más información sobre la compatibilidad de BizTalk Server y SQL Server en Hyper-V, consulte [Apéndice C: BizTalk Server y la compatibilidad de Hyper-V de SQL Server](../technical-guides/appendix-c-biztalk-server-and-sql-server-hyper-v-supportability.md).