---
title: Descripción de FileAct e interactuar de arquitectura de adaptador | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8f97a7fe-20df-4509-bb6e-53743c3a57df
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c04d0ba8b1c2bbd99a71e3d76c8d7ad60c251147
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22223412"
---
# <a name="understanding-fileact-and-interact-adapter-architecture"></a>Descripción de FileAct e interactuar de arquitectura de adaptador
El adaptador de SWIFT se basa en el adaptador de BizTalk Framework. Mediante las clasificaciones de los adaptadores de BizTalk Server, los adaptadores de SWIFT, FileAct e InterAct, representan lo siguiente:  
  
-   Adaptador personalizado. Se trata de un adaptador personalizado creado específicamente para interactuar con la red SWIFT con un estándar propietario denominado FileAct e Interact.  
  
-   Adaptador de transporte. Este adaptador permite la aplicación de software empresarial Enviar y recibir mensajes con la red SWIFT.  
  
-   Sin transacciones. El adaptador no hace uso de cualquier objeto de transacción para interactuar con la red SWIFT.  
  
-   Aislado: El adaptador de recepción se ejecuta en un proceso independiente y adaptadores de envío normal que se ejecutan en proceso.  
  
 Para obtener información sobre el adaptador de BizTalk Framework, consulte la "¿Cuál es el marco de trabajo?" tema de Ayuda de BizTalk Server.  
  
 En la siguiente ilustración muestra una vista de alto nivel de la arquitectura de FileAct e InterAct.  
  
 ![](../../adapters-and-accelerators/fileact-interact/media/035ebb05-ce11-447c-b56b-ba8b41e07e50.gif "035ebb05-ce11-447c-b56b-ba8b41e07e50")  
  
> [!NOTE]
>  Microsoft [!INCLUDE[swift_adapter](../../includes/swift-adapter-md.md)] admite solo las API de vínculo SWIFTNet (SNL) de modo strict.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [SWIFTNet cliente y servidor](../../adapters-and-accelerators/fileact-interact/swiftnet-client-and-server.md)  
  
-   [Arquitectura del adaptador de envío SWIFT](../../adapters-and-accelerators/fileact-interact/swift-send-adapter-architecture.md)  
  
-   [Arquitectura del adaptador de recepción de SWIFT](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-architecture.md)  
  
-   [Arquitectura del adaptador de FileAct](../../adapters-and-accelerators/fileact-interact/fileact-adapter-architecture.md)  
  
-   [Interactuar de arquitectura de adaptador](../../adapters-and-accelerators/fileact-interact/interact-adapter-architecture.md)