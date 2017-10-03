---
title: "Clústeres de Hosts de recepción | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 93544f39-836f-4a4f-9587-230bfa3a9d4e
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 876cdb5f3740e5f06d00a536e1459c64ac886d89
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="clustering-receiving-hosts"></a>Clústeres de Hosts de recepción
[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]proporciona la funcionalidad que le permite configurar un Host de BizTalk como un recurso agrupado dentro de un [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] grupo de clúster. Compatibilidad con clústeres de host se proporciona para admitir alta disponibilidad integrados de BizTalk adaptadores de recepción que no se deben ejecutar en varias instancias de host al mismo tiempo, como controlador de recepción FTP o, en determinadas circunstancias, controlador de recepción de POP3. También se proporciona la funcionalidad de agrupación de hosts para garantizar la coherencia transaccional de los mensajes enviados o recibidos por el adaptador de MSMQ en escenarios que requieren que el servicio MSMQ esté agrupado.  
  
> [!NOTE]  
>  Clústeres de host solo está disponible con [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] Enterprise Edition.  
  
> [!NOTE]  
>  Para agrupar un Host de BizTalk debe haber configurado al menos dos [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] equipos en un grupo de BizTalk como miembros de un [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] clúster. Para obtener más información acerca de cómo configurar un [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] de clúster, consulte [documentos de agrupación en clústeres de Windows Server 2008, notas del producto, difusiones por Web, grupos de](http://go.microsoft.com/fwlink/?LinkId=156818) (http://go.microsoft.com/fwlink/?LinkId=156818).  
  
 Compatibilidad con clústeres de Host de BizTalk está disponible para proporcionar alta disponibilidad para cinco de los adaptadores integrados de BizTalk: adaptador de FTP, el adaptador de MSMQ, el adaptador de POP3, el adaptador de SQL y el adaptador SAP. También se proporciona esta funcionalidad, de modo que hay una alta disponibilidad a la hora de ejecutar una sola instancia de un adaptador para una entrega ordenada.  
  
 Todos los controladores del adaptador de BizTalk se pueden ejecutar en un host del clúster, pero no hay ninguna ventaja desde controladores de adaptador se ejecuta en un host en clúster excepto como se describe más abajo. Si los requisitos de procesamiento incluyen cualquiera de los escenarios descritos en la sección siguiente, debe ejecutar controladores de adaptador en un host del clúster. Para obtener instrucciones detalladas de configuración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] clústeres, consulte [mejorar la tolerancia a errores en BizTalk Server mediante un clúster de conmutación por error de Windows Server 2008 o clúster de servidores de Windows Server 2003](http://go.microsoft.com/fwlink/?LinkId=156819) (http://go.microsoft.com/fwlink/?LinkId=156819).  
  
## <a name="scenarios-for-running-adapter-handlers-in-clustered-hosts"></a>Escenarios para la ejecución de controladores de adaptador en Hosts en clúster  
 Si los requisitos de procesamiento incluyen cualquiera de los escenarios que se enumeran a continuación, debe ejecutar controladores de adaptador en un host del clúster.  
  
-   Ejecutar el controlador de recepción del adaptador de FTP en un host de BizTalk agrupado  
  
-   Ejecutar controladores del adaptador de MSMQ en un host de BizTalk agrupado  
  
-   Ejecutar el controlador de recepción del adaptador de POP3 en un host de BizTalk agrupado  
  
-   Ejecutar un adaptador de recepción que admita entrega ordenada con un host de BizTalk agrupado  
  
 Para obtener más información acerca de estos escenarios, vea [consideraciones para ejecutar controladores de adaptador dentro de un Host en clúster](http://go.microsoft.com/fwlink/?LinkId=151284) (http://go.microsoft.com/fwlink/?LinkId=151284).  
  
## <a name="see-also"></a>Vea también  
 [El escalado de Hosts de recepción](../technical-guides/scaling-out-receiving-hosts.md)   
 [Ajuste de escala en Hosts de procesamiento](../technical-guides/scaling-out-processing-hosts.md)   
 [El escalado de Hosts de envío](../technical-guides/scaling-out-sending-hosts.md)