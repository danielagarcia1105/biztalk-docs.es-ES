---
title: Acelerador de BizTalk para SWIFT en tiempo de ejecución | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2fc0e7a7cb00e16263e537e24abcc144e5c7d0a4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966125"
---
# <a name="biztalk-accelerator-for-swift-runtime"></a>Acelerador de BizTalk para SWIFT en tiempo de ejecución
Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] proporciona la funcionalidad de dos formas: materiales de desarrollo y los componentes de tiempo de ejecución. Materiales de desarrollo incluyen esquemas XSD, las reglas de validación y las directivas y código de ejemplo. Componentes de tiempo de ejecución incluyen el Desensamblador SWIFT personalizado, el ensamblador de SWIFT personalizado, la reparación de mensajes y nuevo envío orquestación (MrsrRepair.odx) y la orquestación de conciliación de respuestas de FIN (FrrMain.odx). Para obtener más información sobre la reparación de mensajes y nuevo envío, consulte [reparación de mensajes y nuevo envío](../../adapters-and-accelerators/accelerator-swift/message-repair-and-new-submission.md). Para obtener más información sobre FRR, consulte [conciliación de respuestas de FIN](../../adapters-and-accelerators/accelerator-swift/fin-response-reconciliation.md).  

 En la siguiente ilustración muestra la arquitectura de alto nivel del sistema de [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)].  

 ![](../../adapters-and-accelerators/accelerator-swift/media/a4swiftsystemarchitecture-end-to-end.gif "A4SWIFTSystemArchitecture_End_to_End")  

 La figura siguiente ilustra cómo fluyen los mensajes entre A4SWIFT y una aplicación de back-end y el uso de A4SWIFT [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] formularios en MRSR de sitio de reparación de mensajes y nuevo envío.  

 ![](../../adapters-and-accelerators/accelerator-swift/media/a4swiftsystemarchitecture-interfaceswithbackendapplications.gif "A4SWIFTSystemArchitecture_InterfaceswithBackEndApplications")  

 La ilustración siguiente muestra cómo fluyen los mensajes entre A4SWIFT y la red SWIFT.  

 ![](../../adapters-and-accelerators/accelerator-swift/media/a4swiftsystemarchitecture-interfaceswiththeswiftnetwork.gif "A4SWIFTSystemArchitecture_InterfaceswiththeSWIFTNetwork")  

 Puede definir todos los componentes de A4SWIFT como implementaciones específicas de vertical de los componentes de aplicación de BizTalk Server. Aceleradores de BizTalk proporcionan una funcionalidad en tiempo de ejecución y desarrollo para acelerar el desarrollo de aplicaciones de BizTalk específicos verticales en la parte superior de [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]. Por lo tanto, todos los componentes de A4SWIFT (desarrollo o en tiempo de ejecución) acatar y caben en la arquitectura de aplicación de BizTalk Server. A4SWIFT instala componentes en tiempo de ejecución en el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] en tiempo de ejecución como componentes personalizados. Tras el desarrollo materiales se compilan e implementan, A4SWIFT y [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] en tiempo de ejecución usarlos para proporcionar funcionalidad de mensajería y la automatización de SWIFT.  

 La siguiente ilustración muestra la topología de alto nivel de aplicación de BizTalk Server.  

 ![](../../adapters-and-accelerators/accelerator-swift/media/fsa-intro1.gif "FSA_Intro1")  

 El [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] modelo de aplicación utiliza la base de datos de cuadro de mensajes y el patrón de publicación-suscripción que rige el flujo de mensajes dentro y fuera de la base de datos de cuadro de mensajes. Para obtener más información sobre el diseño de arquitectura y la aplicación de BizTalk, consulte la Ayuda de BizTalk Server.  

 El modelo de aplicación de A4SWIFT hereda el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] modelo de aplicación y le agrega componentes específicos de SWIFT para facilitar la soluciones relacionadas con SWIFT en [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]. En la lista siguiente se describe estos componentes de A4SWIFT específicos:  

- **Componentes en tiempo de ejecución.** Desensamblador de SWIFT en la canalización de recepción, el ensamblador de SWIFT en la canalización de envío, la reparación de mensajes y nuevo envío de orquestación y la orquestación de conciliación de respuestas de FIN.  

- **Materiales de desarrollo.** Esquemas de SWIFT, reglas, las orquestaciones y los proyectos de ejemplo se incluyen en las soluciones de clientes e implemente en el tiempo de ejecución para la ejecución.  

  En esta sección se describe el tiempo de ejecución de A4SWIFT en detalle.  

  Esta sección contiene:  

- [Desensamblador de SWIFT](../../adapters-and-accelerators/accelerator-swift/swift-disassembler.md)  

- [Ensamblador de SWIFT](../../adapters-and-accelerators/accelerator-swift/swift-assembler.md)  

- [Envío de mensajes a través de ubicaciones de recepción y formularios de InfoPath](../../adapters-and-accelerators/accelerator-swift/submitting-messages-through-receive-locations-and-infopath-forms.md)  

- [Motor de validación de mensajes](../../adapters-and-accelerators/accelerator-swift/message-validation-engine.md)
