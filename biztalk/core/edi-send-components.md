---
title: Componentes de envío EDI | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fce270db-a573-48b3-be15-0178a5b7785b
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c5520a0c1dd0a6ef7e42818314a9f87733aebcb8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239932"
---
# <a name="edi-send-components"></a>Componentes de envío de EDI
La canalización y los componentes de canalización descritos en este tema procesan los mensajes EDI que no son mensajes EDI o AS2. Para obtener información sobre el envío de EDI y AS2 o mensajes que no sean EDI o AS2, vea [componentes de envío de AS2](../core/as2-send-components.md). Tenga en cuenta que los componentes de envío de AS2 realizan procesamiento de EDI además del de AS2.  
  
## <a name="edi-send-pipeline"></a>Canalización de envío EDI  
 La mayor parte del procesamiento de envío de EDI se realiza en la siguiente canalización EDISend. Esta canalización se instala en `Microsoft.BizTalk.Edi.EdiPipelines.dll`, en [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)].  
  
 **Canalización EDISend**  
  
 Esta canalización genera y envía mensajes EDI. No procesa mensajes EDI con codificación AS2 recibidos a través de HTTP. El procesamiento de los mensajes EDI con codificación AS2 se realiza mediante una canalización AS2. Las canalizaciones de envío AS2 utilizan los mismos componentes para procesar mensajes EDI que utilizan las canalizaciones EDI.  
  
> [!NOTE]
>  La ejecución de la canalización EDISend desde una orquestación no está admitida.  
  
> [!NOTE]
>  La canalización AS2EDISend genera y envía los mensajes EDI a través de transporte AS2. Para obtener más información, consulte [componentes de envío de AS2](../core/as2-send-components.md).  
  
 La canalización consta del componente de canalización del ensamblador EDI:  
  
## <a name="edi-send-pipeline-component"></a>Componente de la canalización de envío EDI  
 La canalización EDISend usa el componente de canalización del ensamblador EDI. Este componente se instala en `Microsoft.BizTalk.Edi.PipelineComponents.dll` en [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]componentes de canalización\\.  
  
 El ensamblador EDI realiza más procesamiento de intercambios con codificación EDI en la canalización EDISend. Para obtener información acerca de cómo el ensamblador EDI procesa mensajes EDI, vea [cómo funciona el de ensamblador de EDI](../core/how-the-edi-assembler-works.md).