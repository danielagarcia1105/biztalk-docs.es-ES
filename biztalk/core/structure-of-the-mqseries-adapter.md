---
title: Estructura del adaptador de MQSeries | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- architecture, MQSeries adapters
- MQSeries adapters, architecture
ms.assetid: d25caf6a-3f93-4164-9c92-489b919a624d
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6239b78f0b9bd2c44a314b7ba0ba6ace8f3b78e4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="structure-of-the-mqseries-adapter"></a>Estructura del adaptador de MQSeries
El adaptador de MQSeries tiene dos partes: el adaptador que se ejecuta bajo [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y una aplicación COM +, MQSAgent, que se ejecuta en MQSeries Server para Windows. Esta relación se muestra en la ilustración siguiente.  
  
 ![Componentes de adaptador de MQSeries](../core/media/bts-dev-mqoverallstructure.gif "BTS_Dev_MQOverallStructure")  
  
 El adaptador se comunica con la aplicación MQSAgent. La aplicación MQSAgent, a su vez, se comunica con MQSeries Server para Windows. Puede instalar el agente en el mismo equipo del adaptador si instala en él MQSeries Server para Windows.  
  
 La parte de envío del adaptador envía el mensaje a MQSAgent. MQSAgent, a continuación, usar **MQPut**, envía el mensaje para el Administrador de cola de MQSeries.  
  
 La parte de recepción del adaptador realiza sondeos en el MQSAgent para comprobar si hay mensajes. Cuando hay un mensaje, MQSAgent realiza una **MQGet** para recuperar el mensaje. MQSAgent incluye un intervalo de espera codificado de tres segundos para recuperar el mensaje del administrador de cola.  
  
> [!NOTE]
>  Puede establecer el intervalo de sondeo del adaptador. Si el intervalo de sondeo es inferior a tres segundos, el intervalo de espera se establece con el intervalo de sondeo.  
  
 Tanto las acciones de mensaje de envío como de recepción pueden producirse en las transacciones. Esto permite deshacer los mensajes y, posiblemente, recuperar las operaciones de envío o recepción. Para obtener más información acerca de las transacciones, vea [procesamiento por lotes del adaptador de MQSeries y tratamiento de las transacciones](../core/mqseries-adapter-batching-and-transaction-handling.md).  
  
 Puesto que el adaptador funciona en más de un equipo, puede que se produzca un problema de seguridad. Un programa hostil podría suplantar al agente y capturar datos. Para obtener más información sobre una protección mejorada para el adaptador y el agente, consulte [seguridad del adaptador de MQSeries](../core/mqseries-adapter-security.md).  
  
## <a name="see-also"></a>Vea también  
 [Arquitectura del adaptador de MQSeries](../core/mqseries-adapter-architecture.md)   
 [¿Qué es el adaptador de MQSeries?](../core/what-is-the-mqseries-adapter.md)