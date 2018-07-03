---
title: Los procesos públicos | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- public processes, orchestrations
- business processes, public processes
- public processes, trading partners
- BTARN, public processes
- orchestrations, public-process orchestrations
- public processes
- trading partners, public processes
- public processes, about public processes
ms.assetid: 5ccc7449-5741-4d49-beb6-567bcd93f679
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2f9d0288defa0705c7e12f102011edbf9ee7e90d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36984725"
---
# <a name="public-processes"></a>Procesos públicos
Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] implementa procesos empresariales que implican la integración con socios comerciales como procesos públicos. Implementa los procesos empresariales internos de una organización como procesos privados. Los procesos públicos y privados aíslan el control (en el proceso público) RosettaNet Implementation Framework (RNIF) desde el procesamiento de contenido de servicio y la integración de back-end (en proceso privado).  
  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] implementa procesos públicos como orquestaciones de BizTalk de larga ejecución. Una orquestación de proceso público se ejecuta en el lado del iniciador y otra, en el lado del servicio de respuesta. El [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] programa de instalación proporciona versiones del iniciador y Respondedor orquestaciones de proceso público para RNIF 1.1 y RNIF 2.01.  
  
 Estas orquestaciones de proceso público implementan todos los procesos RNIF. Los procesos públicos ocultan la complejidad de RNIF del resto de los componentes. Además de aplicar el flujo de mensajes compatible con RNIF, el proceso público también determina la configuración de seguimiento predeterminada y proporciona información de estado de proceso en tiempo de ejecución. No se procesa el contenido del servicio de un mensaje. Proceso privado para ello.  
  
 Cada acuerdo de socio comercial hace referencia a un único proceso público para iniciar o responder a las acciones del proceso de interfaz de socio (PIP). Sin embargo, los procesos públicos son independientes de PIP.  
  
 Las especificaciones de RosettaNet dictan el diseño del proceso público. Se recomienda que no modifique un proceso público. La orquestación de proceso público está firmado y con control de versiones. Si modifica un proceso público, ya no será compatible con RNIF.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Proceso público del iniciador](../../adapters-and-accelerators/accelerator-rosettanet/initiator-public-process.md)  
  
-   [Proceso público del respondedor](../../adapters-and-accelerators/accelerator-rosettanet/responder-public-process.md)