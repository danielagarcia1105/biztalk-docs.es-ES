---
title: "Hosts de envío escalado horizontalmente | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- hosts, sending
- FTP adapters, high availability
- EDI adapters, high availability
- hosts, high availability
- hosts, availability
- Windows SharePoint Services adapters, high availability
- scaling, hosts
- hosts, clustering
- scaling, adapters
- high availability, hosts
- clustering, hosts
- MSMQ adapters, high availability
- hosts, planning
- hosts, scaling
- adapters, scaling
ms.assetid: a3d79e0b-8c1e-471c-88e2-623600dfd81a
caps.latest.revision: "25"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 50659e267731caafe4bad6dabe89944cb16c0c98
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="scaled-out-sending-hosts"></a>Hosts de envío escalados horizontalmente
Un host de envío de escala horizontal asegura de que la funcionalidad de envío [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] tiene una alta disponibilidad. Si agrega varios equipos a un host para el envío de mensajes, puede ejecutar varias instancias de host de envío para obtener redundancia y alta disponibilidad.  
  
 La siguiente ilustración muestra un [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] implementación que proporciona alta disponibilidad para el host de envío gracias a dos equipos que ejecutan instancias de host de envío. Tenga en cuenta que, en esta ilustración, los hosts de procesamiento y recepción no tienen una alta disponibilidad.  
  
 ![Escala &#45; Out Host de envío](../core/media/tdi-ha-scalesend.gif "TDI_HA_ScaleSend")  
  
## <a name="high-availability-for-sending-hosts"></a>Alta disponibilidad de los hosts de envío  
 Enviando la funcionalidad en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] es similar a la funcionalidad de procesamiento en el sentido de que ninguna de estas actividades requiere ninguna asociación entre el host y los datos. Igual que cualquier instancia de host de procesamiento puede recuperar mensajes de la base de datos de cuadros de mensajes y procesarlos, cualquier instancia de host de envío puede recuperar mensajes de la base de datos de cuadros de mensajes y enviarlos. Por tanto, proporcionar alta disponibilidad a los host de envío significa que utiliza las mismas técnicas que para proporcionar alta disponibilidad a los hosts de procesamiento.  
  
## <a name="scaling-the-biztalk-server-send-adapters"></a>Escala de los adaptadores de envío de BizTalk Server  
  
### <a name="high-availability-for-the-msmq-send-adapter"></a>Alta disponibilidad para el adaptador de envío MSMQ  
 Para proporcionar alta disponibilidad al adaptador de envío MSMQ, debe agrupar el servicio MSMQ, agrupar un host de BizTalk en el mismo grupo que el servicio MSMQ agrupado y configurar el controlador de envío MSMQ para ejecutarse en este host de BizTalk agrupado. Esto se debe hacer para garantizar la coherencia de los envíos transaccionales iniciados por el adaptador MSMQ. Para obtener más información, consulte [consideraciones para ejecutar controladores de adaptador dentro de un Host en clúster](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md).  
  
### <a name="high-availability-for-the-windows-sharepoint-services-send-adapter"></a>Alta disponibilidad para el adaptador de envío de Windows SharePoint Services  
 Para proporcionar alta disponibilidad al adaptador de envío de Windows SharePoint Services, agregue varios equipos al host de envío con el puerto de envío de cada equipo host haciendo referencia a la misma biblioteca de documentos. El adaptador de Windows SharePoint Services envía mensajes a SharePoint mediante una llamada al servicio web de Windows SharePoint Services instalado por BizTalk en el equipo de SharePoint. BizTalk Server proporciona alta disponibilidad para el adaptador de envío de SharePoint al permitir que se ejecuta el mismo envío puertos en varias instancias de host que envían mensajes a la misma dirección URL de HTTP que apunte a una instalación de NLB de SharePoint.  
  
## <a name="see-also"></a>Vea también  
 [Proporcionar alta disponibilidad de Hosts de BizTalk](../core/providing-high-availability-for-biztalk-hosts.md)   
 [Consideraciones para ejecutar controladores de adaptador en un host agrupado](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md)