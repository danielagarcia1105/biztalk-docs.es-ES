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
ms.openlocfilehash: 853b77e24359d6a833d526fc07166384ea946887
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="privateinitiator-sample"></a>Ejemplo de PrivateInitiator
El ejemplo PrivateInitiator.odx contiene el código para el proceso de iniciador privada instalado [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® BizTalk Server. Se trata de un proceso privado genérico que envía y recibe mensajes de contenido del servicio RNIF del valor predeterminado SQL basado en el adaptador de envío y puertos de recepción.  
  
 De forma predeterminada, el [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] programa de instalación instala el ejemplo en \< *unidad*\>: \Program archivos\\ [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk \<versión\> Acelerador para RosettaNet\SDK\PrivateInitiator.  
  
## <a name="sample-contents"></a>Contenido del ejemplo  
 El proceso privada de iniciador es el proceso empresarial que es interno al iniciador. El proceso privado proporciona integración de back-end entre el proceso público de iniciador y el programa de línea de negocio de back-end. El proceso privado de iniciador se comunica con el proceso público para iniciar mensajes.  
  
 El proceso privado iniciador es único para cada implementación. Puede personalizar el ejemplo PrivateInitiator.odx según sus necesidades. Debe tener cuidado de que se no afecta negativamente al funcionamiento del proceso iniciador pública.  
  
 Para obtener más información, incluida una descripción del flujo de mensajes, vea [proceso iniciador privada](../../adapters-and-accelerators/accelerator-rosettanet/initiator-private-process.md).  
  
## <a name="see-also"></a>Vea también  
 [Ejemplos de orquestaciones](../../adapters-and-accelerators/accelerator-rosettanet/orchestration-samples.md)   
 [Procesos privados](../../adapters-and-accelerators/accelerator-rosettanet/private-processes.md)