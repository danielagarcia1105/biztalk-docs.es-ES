---
title: Ejemplo PrivateInitiator | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4f176566-2a71-487d-84c1-5e7767701e8b
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 55d33b164033cdd3b966ed1f0e77dd551cd56076
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="privateinitiator-sample"></a>Ejemplo de PrivateInitiator
El ejemplo PrivateInitiator.odx contiene el código para el proceso de iniciador privada instalado por [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)]. Se trata de un proceso privado genérico que envía y recibe mensajes de contenido del servicio RNIF del valor predeterminado SQL basado en el adaptador de envío y puertos de recepción.  
  
 De forma predeterminada, el [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] programa de instalación instala el ejemplo en \< *unidad*>: \Program archivos\\ [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk \<versión > Accelerator for RosettaNet\SDK\ PrivateInitiator.  
  
## <a name="sample-contents"></a>Contenido del ejemplo  
 El proceso privada de iniciador es el proceso empresarial que es interno al iniciador. El proceso privado proporciona integración de back-end entre el proceso público de iniciador y el programa de línea de negocio de back-end. El proceso privado de iniciador se comunica con el proceso público para iniciar mensajes.  
  
 El proceso privado iniciador es único para cada implementación. Puede personalizar el ejemplo PrivateInitiator.odx según sus necesidades. Debe tener cuidado de que se no afecta negativamente al funcionamiento del proceso iniciador pública.  
  
 Para obtener más información, incluida una descripción del flujo de mensajes, vea [proceso iniciador privada](../../adapters-and-accelerators/accelerator-rosettanet/initiator-private-process.md).  
  
## <a name="see-also"></a>Vea también  
 [Ejemplos de orquestaciones](../../adapters-and-accelerators/accelerator-rosettanet/orchestration-samples.md)   
 [Procesos privados](../../adapters-and-accelerators/accelerator-rosettanet/private-processes.md)