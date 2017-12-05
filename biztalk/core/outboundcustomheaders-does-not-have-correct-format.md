---
title: OutboundCustomHeaders no tiene el formato correcto | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6097762b-01c9-48b8-8cee-ccd6b11d28d4
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: df751526661ddef455be45c4258c331c940fdd47
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="outboundcustomheaders-does-not-have-correct-format"></a>OutboundCustomHeaders no tiene el formato correcto
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|Identificador del evento|0|  
|Origen del evento|0|  
|Componente|0|  
|Nombre simbólico|0|  
|Texto del mensaje|OutboundCustomHeaders no tiene un formato correcto.|  
  
## <a name="explanation"></a>Explicación  
 El valor de WCF. InboundHeaders o WCF. OutboundCustomHeaders no tiene el formato siguiente: \<encabezados\>...\</headers\>.  
  
## <a name="user-action"></a>Acción del usuario  
 Ajustar los valores de propiedad con \<encabezados\> elemento.  
  
 Para obtener más información, vea el recurso siguiente en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:  
  
-   [Uso de encabezados SOAP en mensajes WCF con componentes de canalización](../core/using-soap-headers-in-wcf-messages-with-pipeline-components.md)