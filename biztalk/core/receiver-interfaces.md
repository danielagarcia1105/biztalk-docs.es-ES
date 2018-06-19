---
title: Interfaces del receptor | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c7ab77d4-705a-4b39-8c33-a7532ae6484c
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 77b42530d721a6dcee52e082fe46deae9ae06405
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22268332"
---
# <a name="receiver-interfaces"></a>Interfaces del receptor
Además de las interfaces de adaptador estándar, adaptadores de recepción necesitan implementar **IBTTransportConfig**. Esta es la interfaz en la que el motor de mensajería de BizTalk entrega la configuración de ubicación de recepción al adaptador.  
  
## <a name="request-response-adapters"></a>Adaptadores de solicitud-respuesta  
 Es posible que sea necesario que los adaptadores de recepción controlen los mensajes de envío en algunos casos. A los adaptadores que realizan esto se les conoce como bidireccionales o adaptadores de solicitud-respuesta. Para poder enviar mensajes, debe implementar un adaptador de recepción **IBTTransmitter**.  
  
 La siguiente ilustración muestra las interfaces implementadas por adaptadores de recepción.  
  
> [!NOTE]
>  El **IBTBatchTransmitter** interfaz no es compatible con los adaptadores de solicitud-respuesta.  
  
 ![](../core/media/requestresponseadapters.gif "RequestResponseAdapters")