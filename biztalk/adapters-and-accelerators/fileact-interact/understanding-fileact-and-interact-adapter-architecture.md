---
title: Descripción de FileAct e interactuar de arquitectura de adaptador | Microsoft Docs
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
ms.openlocfilehash: 7a587b70eb3ae603d59dd5a6f21270133b5a8125
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37005309"
---
# <a name="understanding-fileact-and-interact-adapter-architecture"></a>Descripción de FileAct e interactuar de arquitectura de adaptador
El adaptador de SWIFT se basa en el adaptador de BizTalk Framework. Usa las clasificaciones de los adaptadores de BizTalk Server, los adaptadores de SWIFT, FileAct e InterAct, representan lo siguiente:  
  
- Adaptador personalizado. Se trata de un adaptador personalizado creado específicamente para interactuar con la red SWIFT con un estándar propietario denominado FileAct e Interact.  
  
- Adaptador de transporte. Este adaptador permite la aplicación de software empresarial Enviar y recibir mensajes con la red SWIFT.  
  
- Sin transacciones. El adaptador no hace uso de cualquier objeto de transacción para interactuar con la red SWIFT.  
  
- Aislado: El adaptador de recepción se ejecuta en un proceso independiente y adaptadores de envío normal que se ejecutan en proceso.  
  
  Para obtener información sobre el adaptador de BizTalk Framework, consulte el "¿Cuál es el entorno de adaptador?" tema de Ayuda de BizTalk Server.  
  
  En la siguiente ilustración se muestra una visión general de la arquitectura de FileAct e InterAct.  
  
  ![](../../adapters-and-accelerators/fileact-interact/media/035ebb05-ce11-447c-b56b-ba8b41e07e50.gif "035ebb05-ce11-447c-b56b-ba8b41e07e50")  
  
> [!NOTE]
>  Microsoft [!INCLUDE[swift_adapter](../../includes/swift-adapter-md.md)] admite solo API SWIFTNet vínculo (SNL) en modo strict.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Cliente y servidor de SWIFTNet](../../adapters-and-accelerators/fileact-interact/swiftnet-client-and-server.md)  
  
-   [Arquitectura del adaptador de envío de SWIFT](../../adapters-and-accelerators/fileact-interact/swift-send-adapter-architecture.md)  
  
-   [Arquitectura del adaptador de recepción de SWIFT](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-architecture.md)  
  
-   [Arquitectura del adaptador de FileAct](../../adapters-and-accelerators/fileact-interact/fileact-adapter-architecture.md)  
  
-   [Arquitectura del adaptador de InterAct](../../adapters-and-accelerators/fileact-interact/interact-adapter-architecture.md)