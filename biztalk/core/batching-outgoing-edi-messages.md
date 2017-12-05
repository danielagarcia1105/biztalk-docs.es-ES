---
title: Procesamiento por lotes mensajes EDI salientes | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 93a2bd68-4974-4927-938a-8eaf8f007566
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 852b85e0de23e01e39891adba56053683d18a9b8
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="batching-outgoing-edi-messages"></a>Procesar por lotes mensajes EDI salientes
Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] procesará por lotes los conjuntos de transacciones EDI si se ha habilitado el procesamiento por lotes del acuerdo asociado con el socio comercial que lo recibirá. Las propiedades EDI de un acuerdo le permiten hacer lo siguiente:  
  
-   Definir varios lotes salientes  
  
-   Definir el intercambio  
  
-   Definir los grupos del intercambio  
  
-   Definir los criterios de lanzamiento del procesamiento por lotes  
  
-   Definir los criterios de activación del procesamiento por lotes.  
  
 Microsoft BizTalk Server EDI y AS2 permite el procesamiento de intercambios EDI siguiente:  
  
-   Los intercambios de EDI pueden incluir confirmaciones y/o conjuntos de transacciones.  
  
-   La canalización de recepción de EDI puede dividir un intercambio en conjuntos de transacciones para su posterior procesamiento por [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], o bien puede conservar el intercambio pasándolo a través de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en su forma recibida.  
  
-   La orquestación de enrutamiento de EDI permite que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] procese por lotes un único conjunto de transacciones en más de un intercambio saliente.  
  
-   La orquestación de procesamiento por lotes de EDI ensambla los conjuntos de transacciones XML en un intercambio EDI y valida y entrega el intercambio de acuerdo con las propiedades EDI del acuerdo.  
  
 Los lotes de EDI, llamados intercambios, contienen grupos de mensajes y, a su vez, los grupos de mensajes contienen mensajes individuales. Los lotes salientes pueden incluir varios grupos, pero solo un grupo por tipo de documento. Un grupo puede contener varios conjuntos de transacciones, pero cada uno debe tener el mismo tipo de documento. Los sobres de los mensajes se utilizan para envolver conjuntos de transacciones individuales, grupos individuales y el intercambio completo.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Configuración de un lote de salida](../core/configuring-an-outgoing-batch.md)  
  
-   [Ensamblar un intercambio EDI por lotes](../core/assembling-a-batched-edi-interchange.md)  
  
-   [Envío de intercambios por lotes conservados](../core/sending-a-preserved-batch-interchange.md)