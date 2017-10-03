---
title: "Probar la solución | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- testing solutions
- private process tutorial, testing solutions
ms.assetid: 90faf959-bac6-4695-8cb7-ecabe52baf1a
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4692035aed17f8432eb2bb515fa75df61be8047f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="testing-the-solution"></a>Probar la solución
En esta sección, probará la solución completa. Utilice la herramienta de LOBWebApplication creada en la solución de Fabrikam para enviar solicitudes PIP de 3A2 a la aplicación de LOB de Contoso. La orquestación de Contoso privada que ha creado, a continuación, envía una solicitud de precio y disponibilidad de según 3A2 de Contoso al sistema ERP mediante el adaptador SQL para [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)]. Cuando se recibe la respuesta del sistema ERP, la orquestación llama el motor de reglas de negocios para exigir la emergencia debe directiva empresarial que ha creado.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Crear un precio y una solicitud de disponibilidad con el ejemplo de Fabrikam](../../adapters-and-accelerators/accelerator-rosettanet/creating-a-price-and-availability-request-with-the-fabrikam-sample.md)