---
title: Configuración de Hosts e instancias de Host | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a36a73a4-cc5f-47d6-b56f-7871684c4489
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 286bdaaff66cf0b85caa3bb169bb506501ff386f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36969005"
---
# <a name="configuring-hosts-and-host-instances"></a>Configuración de Hosts e instancias de Host
Un Host de BizTalk representa un conjunto lógico de cero o más procesos de tiempo de ejecución en el que puede implementar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] servicios y artefactos (como controladores de adaptador, ubicaciones de recepción y orquestaciones). Una instancia de host es la instancia física de un host en un equipo que ejecuta [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Para obtener más información acerca de los Hosts de BizTalk e instancias de host, consulte [Hosts](http://go.microsoft.com/fwlink/?LinkId=154189) (<http://go.microsoft.com/fwlink/?LinkId=154189>) y [instancias de Host](http://go.microsoft.com/fwlink/?LinkId=154190) (<http://go.microsoft.com/fwlink/?LinkId=154190>).  
  
 Para obtener más información acerca de cómo administrar Hosts de BizTalk e instancias de host, consulte [administración de Hosts de BizTalk e instancias de Host](http://go.microsoft.com/fwlink/?LinkId=154191) (http://go.microsoft.com/fwlink/?LinkId=154191).  
  
 Para obtener información sobre cómo configurar un host de seguimiento dedicado, vea [configurar un Host de seguimiento dedicado](../technical-guides/configuring-a-dedicated-tracking-host.md).  
  
## <a name="separating-host-instances-by-functionality"></a>Separación de instancias de Host por funcionalidad  
 Además de los aspectos de alta disponibilidad de la configuración de la instancia de host, debe separar enviar, recibir, procesar y funcionalidad de seguimiento en varios hosts. Esto proporciona flexibilidad al configurar la carga de trabajo en el grupo de BizTalk y es el medio principal de distribuir el procesamiento en un grupo de BizTalk. Esto también permite detener un host sin que afecte a otros hosts. Por ejemplo, desea dejar de enviar mensajes para permitirles cola la base de datos de cuadro de mensajes, mientras sigue permitiendo la recepción de mensajes que se produzca entrante.  
  
 Separación de instancias de host mediante la funcionalidad, también proporciona las siguientes ventajas:  
  
- Cada instancia de host tiene su propio conjunto de recursos, como memoria, identificadores y los subprocesos en el grupo de subprocesos. NET.  
  
- Varios Hosts de BizTalk también se reducirá la contención en las tablas de cola de host de base de datos de cuadro de mensajes puesto que cada host se asigna a sus propias tablas de cola de trabajo en la base de datos de cuadro de mensajes.  
  
- La limitación está implementada en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] a nivel de host. Esto le permite establecer diferentes características de limitación para cada host.  
  
- Se implementa la seguridad en el nivel de host; cada host se ejecuta bajo una identidad de Windows discreta. Esto le permitiría, por ejemplo, para proporcionar a **Host_A** el acceso a **FileShare_B**, al no permitir que cualquiera de los demás hosts para tener acceso a recurso compartido de archivos.  
  
  > [!NOTE]  
  >  Aunque existen ventajas a la creación de instancias de host adicionales, también hay inconvenientes posibles si se han creado demasiadas instancias de host. Cada instancia de host es un servicio de Windows (BTSNTSvc.exe o BTSNTSvc64.exe), que genera una carga adicional en la base de datos de cuadro de mensajes y consume recursos del equipo (como CPU, memoria, subprocesos).  
  
  Para obtener más información acerca de cómo modificar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] las propiedades de Host, consulte [cómo modificar las propiedades de Host](http://go.microsoft.com/fwlink/?LinkId=154192) (<http://go.microsoft.com/fwlink/?LinkId=154192>).  
  
##  <a name="BKMK_MemLimit"></a> Límites máximos de prácticos de uso de memoria de una instancia de Host de BizTalk de 32 bits  
 los procesos de 32 bits del sistema operativo Windows de 32 bits con el conjunto de 3 GB tienen 3 gigabytes (GB) de memoria direccionable si el proceso es "compatible con grandes address" (es decir, el archivo ejecutable tiene la marca IMAGE_FILE_LARGE_ADDRESS_AWARE establecida en el encabezado de imagen).  El proceso de host de BizTalk, que se va a "dirección grande consciente", puede abordar/3 GB de memoria en el sistema operativo de Windows con el conjunto de 3 GB.  De forma similar, los procesos de 32 bits en sistema de operativo Windows de 64 bits (AMD64) tienen 4 GB de memoria direccionable, si el proceso es "compatible con grandes address".  De nuevo, el proceso de host de BizTalk, que se va a "dirección grande consciente", puede abordar los 4 GB de memoria cuando se ejecuta como un proceso de 32 bits en sistema operativo de Windows de 64 bits. los procesos de 64 bits en sistema de operativo Windows de 64 bits (AMD64) tienen 8 terabytes de memoria direccionable.  
  
 Aunque la cantidad máxima de memoria direccionable mediante un proceso en un sistema operativo de Windows de 32 bits (sin el modificador/3 GB) es de 2 GB, una aplicación de .NET (por ejemplo, una instancia de host de BizTalk) recibirá errores de memoria insuficiente antes de "bytes virtuales" llegue a 2 GB. En la tabla siguiente se resume esto y se incluye los límites prácticos para bytes privados y bytes virtuales.  
  
|Procesar|Sistema operativo Windows|Memoria direccionable (con un proceso de gran tamaño compatible con dirección)|Límite práctico para Bytes virtuales|Límite práctico para bytes privados|  
|-------------|----------------|---------------------------------------------------------------|---------------------------------------|--------------------------------------|  
|32 bits|32 bits|2 GB|1400 MB|800 MB|  
|32 bits|32 bits con 3 GB|/ 3 GB|2400 MB|1800 MB|  
|32 bits|64 bits|4 GB|3400 MB|2800 MB|  
|64 bits|64 bits|8 terabytes|-|-|  
  
 Para obtener más información, vea:  
  
-   [Supervisión de rendimiento de ASP.NET y cuándo alertar a los administradores](http://go.microsoft.com/fwlink/?LinkId=151856) ()http://go.microsoft.com/fwlink/?LinkId=151856)  
  
-   [Los límites de memoria para las versiones de Windows](http://go.microsoft.com/fwlink/?LinkId=151857) ()http://go.microsoft.com/fwlink/?LinkId=151857)  
  
## <a name="see-also"></a>Vea también  
 [Lista de comprobación: Configuración de BizTalk Server](../technical-guides/checklist-configuring-biztalk-server.md)   
 [Configuración de un host de seguimiento dedicado](../technical-guides/configuring-a-dedicated-tracking-host.md)