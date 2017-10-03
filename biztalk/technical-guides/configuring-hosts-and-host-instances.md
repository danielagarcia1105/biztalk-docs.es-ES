---
title: "Configuración de Hosts e instancias de Host | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a36a73a4-cc5f-47d6-b56f-7871684c4489
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 55dda06d447d9e27c7c8b491986b499003c0bb73
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-hosts-and-host-instances"></a>Configuración de Hosts e instancias de Host
Un Host de BizTalk representa un conjunto lógico de cero o más procesos de tiempo de ejecución en el que puede implementar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] servicios y artefactos (como controladores de adaptador, ubicaciones de recepción y orquestaciones). Una instancia de host es la instancia física de un host en un equipo que ejecuta [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Para obtener más información sobre los Hosts de BizTalk y las instancias de host, consulte [Hosts](http://go.microsoft.com/fwlink/?LinkId=154189) (http://go.microsoft.com/fwlink/?LinkId=154189) y [instancias de Host](http://go.microsoft.com/fwlink/?LinkId=154190) (http://go.microsoft.com/fwlink/?LinkId=154190).  
  
 Para obtener más información acerca de cómo administrar Hosts de BizTalk e instancias de host, consulte [administración de Hosts de BizTalk e instancias de Host](http://go.microsoft.com/fwlink/?LinkId=154191) (http://go.microsoft.com/fwlink/?LinkId=154191).  
  
 Para obtener información sobre cómo configurar un host de seguimiento dedicado, vea [configurar un Host de seguimiento dedicado](../technical-guides/configuring-a-dedicated-tracking-host.md).  
  
## <a name="separating-host-instances-by-functionality"></a>Separación de instancias de Host por funcionalidad  
 Además de los aspectos de alta disponibilidad de la configuración de la instancia de host, debe separar enviar, recibir, procesar y funcionalidad de seguimiento en varios hosts. Esto proporciona flexibilidad al configurar la carga de trabajo en el grupo de BizTalk y es el medio principal de distribuir el procesamiento a través de un grupo de BizTalk. Esto también permite detener un host sin que afecte a otros hosts. Por ejemplo, desea detener el envío de mensajes que les permiten cola en la base de datos de cuadro de mensajes, mientras sigue permitiendo la recepción entrante de mensajes que se produzca.  
  
 Separación de instancias de host según su funcionalidad, también ofrece las siguientes ventajas:  
  
-   Cada instancia de host tiene su propio conjunto de recursos, como memoria, identificadores y los subprocesos en el grupo de subprocesos. NET.  
  
-   Varios Hosts de BizTalk también se reducirá la contención en las tablas de cola de host de base de datos de cuadro de mensajes puesto que cada host se asigna a sus propias tablas de cola de trabajo en la base de datos de cuadro de mensajes.  
  
-   La limitación se implementa en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en el nivel de host. Esto permite establecer diferentes características de limitación para cada host.  
  
-   La seguridad se implementa en el nivel de host; cada host se ejecuta bajo una identidad de Windows discreta. Esto le permitirá, por ejemplo, para conceder a **Host_A** el acceso a **FileShare_B**, permitiendo no cualquiera de los demás hosts para tener acceso a recurso compartido de archivos.  
  
    > [!NOTE]  
    >  Aunque existen ventajas a la creación de instancias de host adicionales, también hay posibles inconvenientes si hay demasiadas instancias de host se crean. Cada instancia de host es un servicio de Windows (BTSNTSvc.exe o BTSNTSvc64.exe), que genera una carga adicional en la base de datos de cuadro de mensajes y consume recursos del equipo (por ejemplo, CPU, memoria, subprocesos).  
  
 Para obtener más información acerca de cómo modificar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] las propiedades de Host, consulte [cómo modificar propiedades de Host](http://go.microsoft.com/fwlink/?LinkId=154192) (http://go.microsoft.com/fwlink/?LinkId=154192).  
  
##  <a name="BKMK_MemLimit"></a>Límites máximos de prácticos de uso de memoria de una instancia de Host de BizTalk de 32 bits  
 procesos de 32 bits en sistema de operativo de Windows de 32 bits con/3 GB configurado tienen 3 gigabytes (GB) de memoria direccionable si el proceso es "grande dirección compatible con" (es decir, el archivo ejecutable tiene el indicador IMAGE_FILE_LARGE_ADDRESS_AWARE definido en el encabezado de la imagen).  El proceso de host de BizTalk, que se va a "grandes" address tenga en cuenta, puede solucionar/3 GB de memoria en el sistema operativo Windows con/3 GB configurado.  De forma similar, los procesos de 32 bits en sistema de operativo de Windows de 64 bits (AMD64) tienen 4 GB de memoria direccionable, si el proceso es "grande dirección compatible con".  De nuevo, el proceso de host de BizTalk, que se va a "grandes" address tenga en cuenta, puede direccionar 4 GB de memoria cuando se ejecuta como un proceso de 32 bits en sistemas operativos de Windows de 64 bits. los procesos de 64 bits en sistema de operativo de Windows de 64 bits (AMD64) tienen 8 terabytes de memoria direccionable.  
  
 Aunque la cantidad máxima de memoria direccionable por un proceso en un sistema de operativo de Windows de 32 bits (sin el modificador/3 GB) es de 2 GB, una aplicación de .NET (por ejemplo, una instancia de host de BizTalk) recibirá errores de memoria insuficiente antes de que el "bytes virtuales" alcance los 2 GB. En la tabla siguiente se resume este y se incluye los límites prácticos para bytes privados y bytes virtuales.  
  
|Procesar|Sistema operativo Windows|Memoria direccionable (con un proceso grande consciente de dirección)|Límite práctico para Bytes virtuales|Límite práctico para PrivateBytes|  
|-------------|----------------|---------------------------------------------------------------|---------------------------------------|--------------------------------------|  
|32 bits|32 bits|2 GB|1400 MB|800 MB|  
|32 bits|32 bits con/3 GB|/ 3 GB|2400 MB|1800 MB|  
|32 bits|64 bits|4 GB|3400 MB|2800 MB|  
|64 bits|64 bits|8 terabytes|-|-|  
  
 Para obtener más información, vea:  
  
-   [Supervisión de rendimiento de ASP.NET y cuándo se deben alertar a los administradores](http://go.microsoft.com/fwlink/?LinkId=151856) (http://go.microsoft.com/fwlink/?LinkId=151856)  
  
-   [Límites de memoria para versiones de Windows](http://go.microsoft.com/fwlink/?LinkId=151857) (http://go.microsoft.com/fwlink/?LinkId=151857)  
  
## <a name="see-also"></a>Vea también  
 [Lista de comprobación: Configuración de BizTalk Server](../technical-guides/checklist-configuring-biztalk-server.md)   
 [Configurar un Host de seguimiento dedicado](../technical-guides/configuring-a-dedicated-tracking-host.md)