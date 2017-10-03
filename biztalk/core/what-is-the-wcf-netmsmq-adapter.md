---
title: "¿Qué es el adaptador de WCF-NetMsmq? | Microsoft Docs"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: WCF-NetMsmq adapters, about WCF-NetMsmq adapters
ms.assetid: 506c5e2d-6cbe-4788-8e37-49d009dc559a
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1008cc7178c38532f1781890080eacf4b5dfb56c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="what-is-the-wcf-netmsmq-adapter"></a>¿Qué es el adaptador de WCF-NetMsmq?
El adaptador de WCF-NetMsmq proporciona comunicaciones entre equipos desconectados mediante tecnología de cola en un entorno donde tanto los servicios como los clientes están basados en WCF. Utiliza el transporte de Message Queue Server (MSMQ) y los mensajes tienen codificación binaria.  
  
 La siguiente tabla resume las características del adaptador de WCF-NetMsmq.  
  
|Description|Característica|  
|-----------------|--------------------|  
|Nivel de interoperabilidad|Perfil de .NET|  
|Codificación de mensaje|Binario|  
|Límite|Entre equipos|  
|Protocolo de transporte|MSMQ|  
|Modo de seguridad|Ninguno, Mensaje, Transporte y Ambos.|  
|Mecanismo de autenticación de cliente|Seguridad de transporte y seguridad de mensaje|  
|Compatibilidad con WS-ReliableMessaging|No aplicable|  
|Compatibilidad con WS-AtomicTransaction|Sí|  
|Compatibilidad con mensajería unidireccional|Sí|  
|Compatibilidad con mensajería bidireccional|No|  
|Tipo de host para adaptador de recepción|En curso|  
|Tipo de host para adaptador de envío|En curso|  
  
> [!NOTE]
>  Se deben crear por adelantado las colas de las que el adaptador de recepción WCF-NetMsmq extrae los mensajes. Los mensajes de las colas se deben basar en WCF. De lo contrario, estos mensajes se enviarán a la cola de mensajes con problemas de entrega.  
  
 El adaptador de WCF-NetMsmq se compone de dos adaptadores: un adaptador de recepción y un adaptador de envío.  
  
 **Adaptador de recepción de WCF-NetMsmq**  
  
 Utilice el adaptador de recepción WCF-NetMsmq para recibir solicitudes de Servicio WCF mediante MSMQ. Una ubicación de recepción que utiliza el adaptador de recepción WCF-NetMsmq sólo se puede configurar como recepción unidireccional.  
  
 **Adaptador de envío WCF-NetMsmq**  
  
 Utilice el adaptador de envío WCF-NetMsmq para llamar a un Servicio WCF a través del contrato sin tipo mediante MSMQ.  
  
 Para obtener más información acerca de WCF de recepción y adaptadores de envío, vea [¿cuáles son los adaptadores de WCF?](../core/what-are-the-wcf-adapters.md).  
  
## <a name="see-also"></a>Vea también  
 [Configurar el adaptador de WCF-NetMsmq](../core/configuring-the-wcf-netmsmq-adapter.md)   
 [Adaptadores de WCF](../core/wcf-adapters.md)