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
ms.openlocfilehash: f95ed755dcc709084d52c6fb8b207e9bbd9e866d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="batching-outgoing-edi-messages"></a>Procesar por lotes mensajes EDI salientes
Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] procesará por lotes los conjuntos de transacciones EDI si se ha habilitado el procesamiento por lotes del acuerdo asociado con el socio comercial que lo recibirá. Las propiedades EDI de un acuerdo le permiten hacer lo siguiente:  
  
-   Definir varios lotes salientes  
  
-   Definir el intercambio  
  
-   Definir los grupos del intercambio  
  
-   Definir los criterios de lanzamiento del procesamiento por lotes  
  
-   Definir los criterios de activación del procesamiento por lotes.  
  
 Las funcionalidades EDI y AS2 de Microsoft [!INCLUDE[prague](../includes/prague-md.md)] permiten realizar el siguiente procesamiento de intercambios de EDI:  
  
-   Los intercambios de EDI pueden incluir confirmaciones y/o conjuntos de transacciones.  
  
-   La canalización de recepción de EDI puede dividir un intercambio en conjuntos de transacciones para su posterior procesamiento por [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], o bien puede conservar el intercambio pasándolo a través de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en su forma recibida.  
  
-   La orquestación de enrutamiento de EDI permite que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] procese por lotes un único conjunto de transacciones en más de un intercambio saliente.  
  
-   La orquestación de procesamiento por lotes de EDI ensambla los conjuntos de transacciones XML en un intercambio EDI y valida y entrega el intercambio de acuerdo con las propiedades EDI del acuerdo.  
  
 Los lotes de EDI, llamados intercambios, contienen grupos de mensajes y, a su vez, los grupos de mensajes contienen mensajes individuales. Los lotes salientes pueden incluir varios grupos, pero solo un grupo por tipo de documento. Un grupo puede contener varios conjuntos de transacciones, pero cada uno debe tener el mismo tipo de documento. Los sobres de los mensajes se utilizan para envolver conjuntos de transacciones individuales, grupos individuales y el intercambio completo.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Configurar un lote saliente](../core/configuring-an-outgoing-batch.md)  
  
-   [Ensamblar un intercambio EDI por lotes](../core/assembling-a-batched-edi-interchange.md)  
  
-   [Enviar un intercambio por lotes conservado](../core/sending-a-preserved-batch-interchange.md)