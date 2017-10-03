---
title: Glossary8 | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7d271fe0-1b54-4a83-87e6-20aa1c37df97
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a89d9aee3652f0e76714184d4f3a9a18ad610173
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="glossary"></a>Glosario
Este tema definen los términos claves usados en esta guía.  
  
## <a name="glossary"></a>Glosario  
  
|Término|Definición|  
|----------|----------------|  
|**Controladora programable avanzada de interrupciones (APIC)**|Un controlador que recibe las interrupciones de varios orígenes y los envía a un núcleo de procesador para el control. En un sistema multiprocesador, lo que puede ser una máquina virtual o un equipo físico, envía la APIC y recibir mensajes de interrupción interprocessor a y desde otros procesadores lógicos en el bus del sistema. Para obtener más información acerca de la controladora programable avanzada de interrupciones, consulte el capítulo 8 de la [3A volumen Manual del desarrollador de Software de IA-32 arquitecturas y 64 bits de Intel®: Guía de programación de sistema, parte 1](http://go.microsoft.com/fwlink/?LinkId=148923) (http://go.microsoft.com/ ¿fwlink /? LinkId = 148923).|  
|**partición secundaria**|Cualquier partición que se crea la partición primaria (o raíz).|  
|**Core**|Vea **procesador lógico**. **Nota:** en esta guía, core es a veces indistintamente con procesador virtual, especialmente en los gráficos. Este uso se corregirá en una futura edición de esta guía.|  
|**virtualización de dispositivo**|Una tecnología de software que permite un hardware recursos se extraen y compartirse entre varios consumidores.|  
|**dispositivo emulado**|Un dispositivo virtualizado que se asemeje a un dispositivo de hardware físico real para que los invitados pueden usar los controladores habituales para ese dispositivo de hardware. Dispositivos emulados son menos eficaces que los dispositivos sintéticos, pero dispositivos emulados proporcionan compatibilidad para "unenlightened" sistemas operativos que no tiene instalados componentes de integración.|  
|**iluminación**|Una optimización a un sistema operativo para que sea consciente de los entornos de máquina virtual y ajustar su comportamiento para las máquinas virtuales. Optimizaciones de ayudan a reducir el costo de ciertas funciones de sistema operativo como la administración de memoria. Optimizaciones se obtiene acceso a través de la interfaz de hiperllamadas. E/S habilitadas pueden utilizar VMBus directamente, omitiendo cualquier capa de emulación de dispositivos. Se dice que un sistema operativo que aprovecha las ventajas de todas las optimizaciones de posibles son "totalmente habilitadas".|  
|**sistema operativo invitado**|El software de sistema operativo (SO) que se ejecuta en una partición secundaria. Los invitados pueden ser un sistema operativo completo o un núcleo pequeño, en especial.|  
|**hiperllamadas (interfaz)**|Interfaz de programación de aplicaciones (API) que las particiones se utilizan para tener acceso el hipervisor.|  
|**Hyper-V**|Tecnología de virtualización basada en hipervisor para x64 versiones de [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]. La plataforma de virtualización Hyper-V permite que varios sistemas operativos aislados compartir una única plataforma de hardware.|  
|**hipervisor**|Una capa de software que se encuentra justo encima del hardware y por debajo de uno o más sistemas operativos. Su tarea principal consiste en proporcionar entornos de ejecución aislados que se denominan particiones. El hipervisor controla y arbitra acceso al hardware subyacente.|  
|**interrupción**|Una señal asíncrona de hardware que indica la necesidad de atención o un suceso sincrónico en el que indica la necesidad de un cambio en la ejecución de software.|  
|**Unidad de administración de memoria de entrada y salida (IOMMU)**|Vuelve a asignar direcciones de memoria física para las direcciones que usan las particiones secundarias|  
|**componentes de integración (IC)**|Un conjunto de servicios y controladores que mejoran el rendimiento y la integración entre las máquinas físicas y virtuales. Componentes de integración de habilitar los sistemas operativos invitados utilizar estos dispositivos, lo que reduce considerablemente la sobrecarga necesaria para acceder a los dispositivos. Vea también **iluminación**.|  
|**Servicios de integración**|Vea **componentes de integración de**.|  
|**procesador lógico**|Una CPU que controla un subproceso de ejecución (secuencia de instrucciones). Un procesador lógico puede ser una de las principales o de un subproceso de hyper. Puede haber uno o más procesadores lógicos por uno o más núcleos por socket de procesador y los núcleos (más de uno si hyper-threading está habilitada).|  
|**número de unidad lógica (LUN)**|Un número que se usa para identificar un disco en un controlador de disco determinado o dentro de una SAN.|  
|**partición primaria**|Vea **partición raíz**.|  
|**partición**|Una máquina de virtual (VM) creada por el software de hipervisor. Cada partición tiene su propio conjunto de recursos de hardware (CPU, memoria y dispositivos). Particiones pueden poseer o compartir los recursos de hardware.|  
|**acceso al disco de acceso directo**|Una representación de todo un disco físico como un disco virtual en el invitado. Los datos y los comandos se "pasan a través de" en el disco físico (a través de la pila de almacenamiento nativo de la partición raíz) con ningún procesamiento que intervienen por la pila virtual.|  
|**partición raíz**|Una partición que se crea en primer lugar y pertenece a todos los recursos que no tiene el hipervisor, incluidas la mayoría de los dispositivos y memoria del sistema. Hospeda la pila de virtualización y crea y administra las particiones secundarias. La partición raíz es también conocida como la partición primaria.|  
|**red de área de almacenamiento (SAN)**|SAN es redes de dispositivos de almacenamiento. Una SAN (normalmente) conecta varios servidores y dispositivos de almacenamiento en una red óptica de fibra de alta velocidad único.|  
|**dispositivo sintético**|Un dispositivo virtualizado sin hardware físico analógico para que los invitados no es necesario un controlador (cliente de servicios de virtualización) en el dispositivo sintético. Controladores para estos dispositivos se incluyen con los componentes de integración (optimizaciones) para el sistema operativo invitado. Los controladores de dispositivos sintéticos usan VMBus para comunicarse con el software del dispositivo virtualizado en la partición raíz.|  
|**disco duro virtual (VHD)**|Un disco duro virtual es un archivo almacenado en el sistema de disco nativo del equipo físico. Desde dentro de una máquina virtual, el disco duro virtual aparece como si fuese un disco duro físico. Discos duros virtuales se basan en la especificación de formato de imagen de disco duro Virtual. Para obtener más información acerca de la especificación de formato de disco duro Virtual, consulte [http://go.microsoft.com/fwlink/?LinkId=122975](http://go.microsoft.com/fwlink/?LinkId=122975).|  
|**máquina virtual (VM)**|Un equipo virtual que se creó mediante la emulación de software y tiene las mismas características que un equipo real.|  
|**servicio de administración de máquina virtual (VMM)**|Ya que los VMM es parte de la interfaz del proveedor de servicios de virtualización Windows Management Instrumentation (WMI). Herramientas de administración que se conectan a este servicio en tiempo de ejecución para recopilar datos sobre particiones activas.|  
|**proceso de trabajo de máquina virtual (VMWP)**|Cada máquina virtual tiene un proceso de trabajo que se ejecuta en la partición primaria. VMWPs ejecutar el código para guardar el estado, obtener acceso a dispositivos emulados y controlar la máquina virtual.|  
|**procesador virtual**|Una abstracción virtual de un procesador que está programado para ejecutarse en un procesador lógico. Una máquina virtual puede tener uno o más procesadores virtuales.|  
|**cliente de servicios de virtualización (VSC)**|Un módulo de software que se carga un invitado para consumir un recurso o servicio. Para dispositivos de E/S, el cliente del servicio de virtualización puede ser un controlador de dispositivo que carga el núcleo del sistema operativo.|  
|**proveedor de servicios de virtualización (VSP)**|Un proveedor, expuesto por la pila de virtualización, que proporciona recursos o servicios como la E/S a una partición secundaria.|  
|**pila de virtualización**|Una colección de componentes de software en la partición raíz que funcionan conjuntamente para admitir las máquinas virtuales. La pila de virtualización funciona con y se sitúa encima el hipervisor. También proporciona capacidades de administración.|  
|**VMBus**|Un mecanismo de comunicación basada en canal utilizado para la enumeración de comunicación y el dispositivo de partición entre en sistemas con varias particiones virtualizadas activas.|