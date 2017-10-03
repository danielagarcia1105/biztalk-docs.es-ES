---
title: "La canalización de recepción | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cd8f03aa-f5c3-49e7-946b-c8c91fe3abc7
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7461ce357b3fa9cb6216dfce6381876100bb4287
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="receive-pipeline"></a>Canalización de recepción
Este ejemplo proporciona un [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] canalización de recepción que puede personalizar para la aplicación.  
  
## <a name="demonstrates"></a>Demostraciones  
 Este ejemplo muestra cómo procesar un mensaje entrante de RNIF en el equivalente mensaje de XML mediante la canalización de recepción de BTARN (PipelineReceive.btp). PipelineReceive.btp se encuentra en  *\<unidad >*: \Program BizTalk \<versión > Accelerator for RosettaNet\SDK\RNPipelines. Incluye las etapas siguientes:  
  
-   ReceiveMessageNonRepudiate  
  
-   RNMimeDecoder (preprocesador y descodificador MIME)  
  
-   RNDAsm (desensamblador XML)  
  
-   RNPartyRes (componente de resolución de entidades)  
  
-   MessageUpdater  
  
 Para obtener más información acerca de los componentes de esta canalización y el flujo de mensajes en esta canalización, consulte [canalización de recepción de BTARN](../../adapters-and-accelerators/accelerator-rosettanet/btarn-receive-pipeline.md).  
  
## <a name="see-also"></a>Vea también  
 [Ejemplos de canalizaciones](../../adapters-and-accelerators/accelerator-rosettanet/pipeline-samples.md)   
 [Canalización de recepción de BTARN](../../adapters-and-accelerators/accelerator-rosettanet/btarn-receive-pipeline.md)