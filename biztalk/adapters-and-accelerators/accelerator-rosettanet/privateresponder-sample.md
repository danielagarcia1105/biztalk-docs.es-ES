---
title: Ejemplo de PrivateResponder | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3137fadd-9582-4cc6-acfb-c44aca636950
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3de3428aa9971ba62b682494cd94c6bb74bcab53
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22206948"
---
# <a name="privateresponder-sample"></a>Ejemplo de PrivateResponder
El ejemplo PrivateResponder.odx contiene el código para el proceso de servicio de respuesta privado instalado por [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]. Este proceso privada genérica envía y recibe mensajes de contenido del servicio RNIF del valor predeterminado SQL basado en el adaptador de envío y puertos de recepción.  
  
 De forma predeterminada, el [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] programa de instalación instala el ejemplo en \< *unidad*>: \Program archivos\\ [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk \<versión > Accelerator for RosettaNet\SDK\ PrivateResponder.  
  
## <a name="sample-contents"></a>Contenido del ejemplo  
 El proceso privada del servicio de respuesta es el proceso empresarial que es interno para el servicio de respuesta. El proceso privado proporciona integración de back-end entre el proceso público de servicio de respuesta y el programa de línea de negocio de back-end. El proceso privado Respondedor se comunica con el proceso público para responder a mensajes.  
  
 El proceso privada del servicio de respuesta es único para cada implementación. Puede personalizar el ejemplo PrivateResponder.odx según sus necesidades. Debe tener cuidado de que se no afecta negativamente al funcionamiento del proceso de servicio de respuesta pública.  
  
 Para obtener más información, incluida una descripción del flujo de mensajes, vea [proceso privado de servicio de respuesta](../../adapters-and-accelerators/accelerator-rosettanet/responder-private-process.md).  
  
## <a name="see-also"></a>Vea también  
 [Ejemplos de orquestaciones](../../adapters-and-accelerators/accelerator-rosettanet/orchestration-samples.md)   
 [Procesos privados](../../adapters-and-accelerators/accelerator-rosettanet/private-processes.md)