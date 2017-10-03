---
title: "Acelerador de BizTalk para SWIFT en tiempo de ejecución | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- runtime, architecture
- developing, components
- architecture, topology
- messages, message flow diagram
- runtime, components
- SWIFT runtime
- architecture, runtime architecture
- SWIFT network
- A4SWIFT, network
- topology
ms.assetid: c0f59760-7d7d-4b22-a7dc-54e563971d4a
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f312a91d403d125fe6d245b92bf83da57d1031fe
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="biztalk-accelerator-for-swift-runtime"></a>Acelerador de BizTalk para SWIFT en tiempo de ejecución
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] proporciona la funcionalidad de dos formas: materiales de desarrollo y los componentes de tiempo de ejecución. Los materiales de desarrollo incluyen esquemas XSD, reglas de validación y las directivas y código de ejemplo. Los componentes en tiempo de ejecución incluyen el Desensamblador SWIFT personalizado, el ensamblador SWIFT personalizado, la reparación de mensajes y nuevo envío orquestación (MrsrRepair.odx) y la orquestación de conciliación de respuesta de FIN (FrrMain.odx). Para obtener más información sobre la reparación de mensajes y nuevo envío, consulte [reparación de mensajes y nuevo envío](../../adapters-and-accelerators/accelerator-swift/message-repair-and-new-submission.md). Para obtener más información sobre FRR, consulte [FINÉS respuesta conciliación](../../adapters-and-accelerators/accelerator-swift/fin-response-reconciliation.md).  
  
 En la siguiente ilustración muestra la arquitectura de alto nivel de sistema de [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)].  
  
 ![](../../adapters-and-accelerators/accelerator-swift/media/a4swiftsystemarchitecture-end-to-end.gif "A4SWIFTSystemArchitecture_End_to_End")  
  
 La ilustración siguiente muestra cómo fluyen los mensajes entre A4SWIFT y una aplicación back-end, y cómo se utiliza A4SWIFT [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] formularios en MRSR de sitio de reparación de mensajes y nuevo envío.  
  
 ![](../../adapters-and-accelerators/accelerator-swift/media/a4swiftsystemarchitecture-interfaceswithbackendapplications.gif "A4SWIFTSystemArchitecture_InterfaceswithBackEndApplications")  
  
 La ilustración siguiente muestra cómo fluyen los mensajes entre A4SWIFT y la red SWIFT.  
  
 ![](../../adapters-and-accelerators/accelerator-swift/media/a4swiftsystemarchitecture-interfaceswiththeswiftnetwork.gif "A4SWIFTSystemArchitecture_InterfaceswiththeSWIFTNetwork")  
  
 Puede definir todos los componentes de A4SWIFT como implementaciones específicas de vertical de [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] componentes de la aplicación. Aceleradores de BizTalk proporcionan funciones de desarrollo y tiempo de ejecución para acelerar el desarrollo de aplicaciones de BizTalk específicos verticales sobre [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]. Por consiguiente, cumplir todos los componentes de A4SWIFT (desarrollo o en tiempo de ejecución) y ajustará, la [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] arquitectura de la aplicación. A4SWIFT instala los componentes de tiempo de ejecución en el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] en tiempo de ejecución como componentes personalizados. Tras el desarrollo materiales se compilan e implementan, A4SWIFT y [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] en tiempo de ejecución usarlos para proporcionar funcionalidad de mensajería y la automatización de SWIFT.  
  
 En la siguiente ilustración se muestra la topología de aplicaciones de alto nivel para [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)].  
  
 ![](../../adapters-and-accelerators/accelerator-swift/media/fsa-intro1.gif "FSA_Intro1")  
  
 El [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] modelo de aplicación utiliza la base de datos de cuadro de mensajes y el modelo del publicador y el suscriptor que rige el flujo de mensajes dentro y fuera de la base de datos de cuadro de mensajes. Para obtener más información acerca del diseño de arquitectura y aplicación de BizTalk, consulte [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] ayuda.  
  
 Hereda el modelo de aplicaciones de A4SWIFT el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] modelo de aplicación y al que se agregan componentes de SWIFT específicos para facilitar las soluciones basadas en SWIFT en [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]. En la lista siguiente se describe estos componentes específicos de A4SWIFT:  
  
-   **Componentes de tiempo de ejecución.** SWIFT desensamblador en la canalización de recepción, el ensamblador SWIFT en la canalización de envío, la orquestación de reparación de mensajes y nuevo envío y la orquestación de conciliación de respuesta de FIN.  
  
-   **Materiales de desarrollo.** Esquemas SWIFT, reglas, orquestaciones y proyectos de ejemplo que desea incluir en soluciones de cliente y se implementan en el tiempo de ejecución para la ejecución.  
  
 Esta sección describe el tiempo de ejecución de A4SWIFT en detalle.  
  
 Esta sección contiene:  
  
-   [Desensamblador SWIFT](../../adapters-and-accelerators/accelerator-swift/swift-disassembler.md)  
  
-   [Ensamblador SWIFT](../../adapters-and-accelerators/accelerator-swift/swift-assembler.md)  
  
-   [Enviando mensajes a través de ubicaciones de recepción y formularios de InfoPath](../../adapters-and-accelerators/accelerator-swift/submitting-messages-through-receive-locations-and-infopath-forms.md)  
  
-   [Motor de validación de mensajes](../../adapters-and-accelerators/accelerator-swift/message-validation-engine.md)