---
title: Procesos públicos | Documentos de Microsoft
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
ms.openlocfilehash: 6634a5d5871deac48fad1defbd79fae8f5f384ad
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22210028"
---
# <a name="public-processes"></a>Procesos públicos
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] implementa procesos empresariales que implican la integración con socios comerciales como procesos públicos. Implementa los procesos empresariales internos de una organización como procesos privados. Uso de procesos públicos y privados aísla control (en el proceso público) RosettaNet Implementation Framework (RNIF) desde el procesamiento de contenido de servicio y la integración de back-end (en el proceso privado).  
  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]implementa procesos públicos como orquestaciones de BizTalk de larga duración. Una orquestación de proceso público se ejecuta en el lado del iniciador y otra, en el lado del servicio de respuesta. El [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] programa de instalación proporciona versiones de iniciador y el contestador orquestaciones de proceso público para RNIF 1.1 y RNIF 2.01.  
  
 Estas orquestaciones de proceso público implementan todos los procesos RNIF. Los procesos públicos ocultan la complejidad de RNIF del resto de los componentes. Además de aplicar el flujo de mensajes compatible con RNIF, el proceso público también determina la configuración de seguimiento predeterminada y proporciona información de estado de proceso en tiempo de ejecución. No se procesa el contenido del servicio de un mensaje. Esto hace en el proceso privado.  
  
 Cada acuerdo de socio comercial hace referencia a un único proceso público para iniciar o responder a las acciones del proceso de interfaz de socio (PIP). Sin embargo, los procesos públicos son independientes del PIP.  
  
 Las especificaciones de RosettaNet dictan el diseño del proceso público. Se recomienda que no modifique un proceso público. La orquestación de proceso público es una versión y firmados. Si modifica un proceso público, ya no será compatible con RNIF.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Iniciador de proceso público](../../adapters-and-accelerators/accelerator-rosettanet/initiator-public-process.md)  
  
-   [Proceso público de servicio de respuesta](../../adapters-and-accelerators/accelerator-rosettanet/responder-public-process.md)