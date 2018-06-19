---
title: Directiva empresarial de BTARN de ejemplo | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: db932c17-8e8f-4f7a-b165-d1d7d749cdb6
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c85cbb7894f0d8bd1b61b7e7856865b49fd33859
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25960626"
---
# <a name="sample-btarn-business-policy"></a>Directiva empresarial de BTARN de ejemplo
Este ejemplo es el código XML asociado con un [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] directiva de reglas de negocios.  
  
 El archivo de ejemplo es samplebtarnpolicy.XML, en \< *unidad*\>: \Program archivos\\ [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk \<versión\> Acelerador para RosettaNet\SDK\ PIPAutomation\3A4.  
  
## <a name="demonstrates"></a>Demostraciones  
 Este código muestra una directiva de reglas de negocio con la siguiente regla:  
  
 SI (AccountNumber en el mensaje del pedido de compra entrante 3A4 = "111111111") y (MonetaryAmount del pedido < 500), ENTONCES enviar automáticamente un mensaje de respuesta  
  
## <a name="see-also"></a>Vea también  
 [Orquestación del respondedor privado 3A4 mediante una regla de negocio](../../adapters-and-accelerators/accelerator-rosettanet/3a4-private-responder-orchestration-using-a-business-rule.md)