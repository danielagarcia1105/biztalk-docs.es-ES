---
title: Arquitectura de BizTalk Adapter para TIBCO Enterprise Message Service | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- transmit adapter
- one-way receive operations
- architecture
- one-way send operations
- receive adapter
ms.assetid: 304c7236-aacd-4761-8c33-e876b53e84ff
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 88c7bc6420efb67085e4f3a05f6daf0c5dbd2feb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22230284"
---
# <a name="architecture-of-biztalk-adapter-for-tibco-enterprise-message-service"></a>Arquitectura del adaptador de BizTalk para TIBCO Enterprise Message Service
El Adaptador de Microsoft BizTalk para TIBCO Enterprise Message Service (EMS) proporciona un medio de intercambiar datos empresariales en tiempo real entre sistemas TIBCO EMS y BizTalk Server. El adaptador permite la interacción entre una aplicación XML y TIBCO EMS.  
  
 El adaptador acepta mensajes XML que permiten que las aplicaciones de BizTalk se comuniquen con TIBCO EMS usando uno de lo siguiente:  
  
-   **Adaptador de transmisión**: usa un puerto de envío unidireccional estático para enviar un mensaje a TIBCO EMS.  
  
-   **Adaptador de recepción**: utiliza un unidireccional estático puerto de recepción para recibir mensajes de TIBCO EMS.  
  
## <a name="one-way-send-operation"></a>Operación de envío unidireccional  
 En la siguiente ilustración se muestra la arquitectura de una operación de envío unidireccional que usa el Adaptador de BizTalk para TIBCO EMS.  
  
 ![](../core/media/tibcoems-architecture-send.gif "TIBCOEMS_architecture_send")  
  
## <a name="one-way-receive-operation"></a>Operación de recepción unidireccional  
 En la siguiente ilustración se muestra la arquitectura de una operación de recepción unidireccional que usa el Adaptador de BizTalk para TIBCO EMS.  
  
 ![](../core/media/tibcoems-architecture-receive.gif "TIBCOEMS_architecture_receive")  
  
## <a name="see-also"></a>Vea también  
 [Características del adaptador](../core/adapter-features.md)   
 [Planeamiento y arquitectura](../core/planning-and-architecture16.md)