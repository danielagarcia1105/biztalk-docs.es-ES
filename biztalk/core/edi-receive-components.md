---
title: Componentes de recepción EDI | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1d3b82e8-1168-4c2c-bf1a-886b43ff8108
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b5ffe09d7096e27111fc2db5cc2eff33b2d2713e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970077"
---
# <a name="edi-receive-components"></a>Componentes de recepción de EDI
La canalización y los componentes de canalización descritos en este tema procesan los mensajes EDI que no son mensajes EDI o AS2. Para obtener información acerca del procesamiento de EDI o AS2 recibidos o mensajes que no sean EDI o AS2, vea [componentes de recepción AS2](../core/as2-receive-components.md). Tenga en cuenta que los componentes de recepción de AS2 realizan procesamiento de EDI además del de AS2.  
  
## <a name="edi-receive-pipeline"></a>Canalización de recepción EDI  
 El procesamiento de recepción EDI se realiza en la canalización de recepción EDI. Esta canalización se instala en Microsoft.BizTalk.Edi.EdiPipelines.dll, en [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]. Esta canalización procesa los mensajes EDI recibidos a través de cualquier transporte. No procesa mensajes EDI con codificación AS2 recibidos a través de HTTP. El procesamiento de los mensajes EDI de codificación A2 se realiza mediante canalizaciones AS2. Las canalizaciones de recepción AS2 utilizan los mismos componentes para procesar mensajes EDI que utilizan las canalizaciones EDI.  
  
> [!NOTE]
>  Puede producirse un problema de seguridad si crea una ubicación de recepción que utilice la canalización EDIReceive y tenga un tipo de transporte HTTP. La canalización EdiReceive no generará una confirmación HTTP “200 OK”. Si no se devuelve una confirmación EDI, la conexión no se terminará correctamente pero permanecerá abierta. La conexión agotará el tiempo cuando el período de tiempo de espera se haya agotado.  
  
 La canalización EDIReceive se compone de los siguientes componentes de canalización:  
  
-   Desensamblador EDI  
  
-   BatchMarker.  
  
## <a name="edi-receive-pipeline-components"></a>Componentes de canalización recepción EDI  
 La canalización EDIReceive utiliza los siguientes componentes de canalización. Estos componentes se instalan en Microsoft.BizTalk.Edi.PipelineComponents.dll en [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]componentes de canalización\\.  
  
### <a name="edi-disassembler"></a>Desensamblador EDI  
 El desensamblador EDI realiza más procesamiento de intercambios con codificación EDI recibidos en la canalización EDIReceive. Para obtener información acerca de cómo el Desensamblador EDI procesa los mensajes EDI, vea [cómo funciona el de desensamblador de EDI](../core/how-the-edi-disassembler-works.md).  
  
### <a name="batchmarker"></a>BatchMarker  
 El componente de canalización BatchMarker prepara un intercambio para procesar lotes mediante la promoción de las propiedades de contexto BatchId, ToBeBatched y ToBeRouted que se necesitan para procesar un intercambio por lotes. La forma en la que el componente BatchMarker establece estas propiedades depende del número de acuerdos de socios comerciales que se suscribe al elemento por lotes.  
  
- Si solo se suscribe un acuerdo al elemento por lotes, el componente BatchMarker establece la propiedad de contexto ToBeBatched en True para que la orquestación de procesamiento por lotes recoja el elemento por lotes.  
  
- Si más de un acuerdo se suscribe a un elemento por lotes, el componente BatchMarker establece la propiedad de contexto ToBeRouted en True para que la orquestación de enrutamiento recoja el elemento por lotes. También establece la propiedad de contexto BatchIds en una lista delimitada por espacios de identificadores de proceso por lotes. La orquestación de enrutamiento realizará entonces una copia del elemento por lotes por cada identificador de proceso por lotes y establecerá la propiedad ToBeBatched en True en cada copia del elemento por lotes de modo que la orquestación de procesamiento por lotes pueda recoger todas las copias.  
  
  El componente BatchMarker se incluye en la última fase (resolución de acuerdo entre socios comerciales) de la canalización EDIReceive. Todas las canalizaciones que procesarán mensajes EDI deben incluir el componente de canalización BatchMarker.  
  
> [!NOTE]
>  El componente BatchMarker puede incluirse en un componente de recepción que no incluya el desensamblador EDI para realizar la resolución de acuerdos entre socios comerciales sin analizar el mensaje EDI.  
  
 Puede usar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y el componente BatchMarker para procesar por lotes mensajes que no sean EDI. Para obtener más información, vea la sección "Procesamiento de EDI que no son mensajes en el componente de BatchMarker" de [ensamblar un intercambio de EDI por lotes](../core/assembling-a-batched-edi-interchange.md).  
  
## <a name="see-also"></a>Vea también  
 [Cómo recibe BizTalk Server los mensajes EDI](../core/how-biztalk-server-receives-edi-messages.md)