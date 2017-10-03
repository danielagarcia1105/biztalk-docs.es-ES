---
title: Flujo de mensajes del adaptador de MQSeries | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: MQSeries adapters, message flow
ms.assetid: aa5c8523-afd6-4181-9c11-a150857a7790
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5df8549f99d376ea518b160ac1505aaac7feb5fa
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="mqseries-adapter-message-flow"></a>Flujo de mensajes del adaptador de MQSeries
Un mensaje que se origine en un equipo de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] pasa, en primer lugar, a un servidor MQSeries Server que se ejecute en Windows. El servidor MQSeries que se ejecuta en Windows puede estar en el mismo equipo que ejecuta el servidor BizTalk Server. El mensaje se enruta a través del servidor MQSeries Server para un equipo con Windows hasta un host del servidor MQSeries Server en un sistema operativo como UNIX. Una aplicación recupera el mensaje de la cola MQSeries.  
  
 Un mensaje que se origine en una aplicación en primer lugar va a una cola MQSeries en el servidor MQSeries Server. MQSeries Server reenvía el mensaje al servidor MQSeries Server para un equipo con Windows. BizTalk Server recibe el mensaje de MQSeries Server de un equipo con Windows y lo reenvía a la aplicación apropiada.  
  
 El adaptador de MQSeries admite los siguientes escenarios de mensajería.  
  
|**Escenario**|**Description**|  
|------------------|---------------------|  
|Receive|El adaptador recibe un mensaje de MQSeries Server, que se pasa a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].|  
|Envío (Puerto unidireccional estático)|El adaptador enruta un mensaje que se origina en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].|  
|Puerto de envío dinámico|Habilita la aplicación para seleccionar una dirección de destino (URI) en tiempo de ejecución.|  
|Recepción dinámica|Permite a la aplicación seleccionar una dirección de origen (URI) en tiempo de ejecución estableciendo la **MQSeries.DynamicReceive** propiedad de contexto **Sí** y especificando la dirección de recepción dinámica.|  
|Correlation|Los mensajes del adaptador están correlacionados con instancias específicas de una orquestación que puede administrar más de un tipo de mensajes.<br /><br /> MQSeries Server puede crear el identificador de correlación mediante la utilización de Petición- Respuesta mientras que BizTalk Server puede crear el identificador de correlación.<br /><br /> Para obtener más información acerca de conjuntos de correlaciones, vea la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].|  
  
 Para obtener más información acerca de la utilización de adaptadores y puertos en canalizaciones y orquestaciones, así como acerca del enrutamiento por contenidos, vea la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Para obtener más información sobre el uso de identificadores de correlación en el adaptador, vea [correlación de solicitud y respuesta utilizando mensajes](../core/correlating-messages-using-request-reply.md).  
  
 Para obtener información acerca de las propiedades de encabezado disponibles para el filtrado en el adaptador, vea [propiedades relacionadas con BizTalk Server](../core/properties-related-to-biztalk-server.md) y [propiedades de contexto de MQSeries](../core/mqseries-context-properties.md).  
  
## <a name="see-also"></a>Vea también  
 [Uso del adaptador de MQSeries](../core/using-the-mqseries-adapter.md)